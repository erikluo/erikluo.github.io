## Tensorflow编译

### 编译生成so库文件
- bazel version: 5.1.1
- gcc version: 9.4.0
- protobuf version:  tensorflow/workspace2.bzl

```
tf_http_archive(
        name = "com_google_protobuf",
        patch_file = ["//third_party/protobuf:protobuf.patch"],
        sha256 = "f66073dee0bc159157b0bd7f502d7d1ee0bc76b3c1eac9836927511bdc4b3fc1",
        strip_prefix = "protobuf-3.21.9",
        system_build_file = "//third_party/systemlibs:protobuf.BUILD",
        system_link_files = {
            "//third_party/systemlibs:protobuf.bzl": "protobuf.bzl",
            "//third_party/systemlibs:protobuf_deps.bzl": "protobuf_deps.bzl",
        },
        urls = tf_mirror_urls("https://github.com/protocolbuffers/protobuf/archive/v3.21.9.zip"),
    )
```
  
```
curl -fLO https://releases.bazel.build/5.1.1/release/bazel-5.1.1-linux-x86_64 && chmod +x bazel-5.1.1-linux-x86_64 &&  mv  ./bazel-5.1.1-linux-x86_64 /usr/local/bin/bazel

git checkout v2.12.1
./configure
bazel build --local_ram_resources=4096  --cxxopt="-D_GLIBCXX_USE_CXX11_ABI=1" --config=opt   //tensorflow:libtensorflow.so
bazel build --local_ram_resources=4096  --cxxopt="-D_GLIBCXX_USE_CXX11_ABI=1" --config=opt   //tensorflow:libtensorflow_framwork.so

# --subcommands 参数可以编译时显示详细命令行信息
bazel build --local_ram_resources=4096 --subcommands  --cxxopt="-D_GLIBCXX_USE_CXX11_ABI=1" --config=opt   //tensorflow:libtensorflow.so
```

## protobuf编译
普通编译
```
./configure
make
```
hidden式编译(场景：一个程序的两个模块 A B，各使用了两个不同版本的pb库，直接静态链接会失败，此时可在一个模块中隐藏pb，且该模块必须使用动态库so)
例如需要在B中隐藏pb，可以在构建B.so 时链接如下方式生成的protobuf静态库文件。
```
./configure --with-pic --disable-shared --enable-static "CXXFLAGS=-fvisibility=hidden"
make V=1
```

普通pb编译参数
```
mv -f $depbase.Tpo $depbase.Plo
libtool: compile:  g++ -DHAVE_CONFIG_H -I. -I.. -pthread -DHAVE_PTHREAD=1 -DHAVE_ZLIB=1 -Wall -Wno-sign-compare -O2 -g -std=c++11 -DNDEBUG -MT google/protobuf/stubs/strutil.lo -MD -MP -MF google/protobuf/stubs/.deps/strutil.Tpo -c google/protobuf/stubs/strutil.cc  -fPIC -DPIC -o google/protobuf/stubs/.libs/strutil.o
libtool: compile:  g++ -DHAVE_CONFIG_H -I. -I.. -pthread -DHAVE_PTHREAD=1 -DHAVE_ZLIB=1 -Wall -Wno-sign-compare -O2 -g -std=c++11 -DNDEBUG -MT google/protobuf/stubs/strutil.lo -MD -MP -MF google/protobuf/stubs/.deps/strutil.Tpo -c google/protobuf/stubs/strutil.cc -o google/protobuf/stubs/strutil.o >/dev/null 2>&1
depbase=`echo google/protobuf/stubs/time.lo | sed 's|[^/]*$|.deps/&|;s|\.lo$||'`;\
/bin/sh ../libtool  --tag=CXX   --mode=compile g++ -DHAVE_CONFIG_H -I. -I..    -pthread -DHAVE_PTHREAD=1 -DHAVE_ZLIB=1 -Wall -Wno-sign-compare -O2 -g -std=c++11 -DNDEBUG -MT google/protobuf/stubs/time.lo -MD -MP -MF $depbase.Tpo -c -o google/protobuf/stubs/time.lo google/protobuf/stubs/time.cc &&\
mv -f $depbase.Tpo $depbase.Plo
libtool: compile:  g++ -DHAVE_CONFIG_H -I. -I.. -pthread -DHAVE_PTHREAD=1 -DHAVE_ZLIB=1 -Wall -Wno-sign-compare -O2 -g -std=c++11 -DNDEBUG -MT google/protobuf/stubs/time.lo -MD -MP -MF google/protobuf/stubs/.deps/time.Tpo -c google/protobuf/stubs/time.cc  -fPIC -DPIC -o google/protobuf/stubs/.libs/time.o
libtool: compile:  g++ -DHAVE_CONFIG_H -I. -I.. -pthread -DHAVE_PTHREAD=1 -DHAVE_ZLIB=1 -Wall -Wno-sign-compare -O2 -g -std=c++11 -DNDEBUG -MT google/protobuf/stubs/time.lo -MD -MP -MF google/protobuf/stubs/.deps/time.Tpo -c google/protobuf/stubs/time.cc -o google/protobuf/stubs/time.o >/dev/null 2>&1
```

隐藏pb编译参数
```
mv -f $depbase.Tpo $depbase.Plo
libtool: compile:  g++ -DHAVE_CONFIG_H -I. -I.. -pthread -DHAVE_PTHREAD=1 -DHAVE_ZLIB=1 -Wall -Wno-sign-compare -fvisibility=hidden -MT google/protobuf/stubs/strutil.lo -MD -MP -MF google/protobuf/stubs/.deps/strutil.Tpo -c google/protobuf/stubs/strutil.cc  -fPIC -DPIC -o google/protobuf/stubs/strutil.o
depbase=`echo google/protobuf/stubs/time.lo | sed 's|[^/]*$|.deps/&|;s|\.lo$||'`;\
/bin/sh ../libtool  --tag=CXX   --mode=compile g++ -DHAVE_CONFIG_H -I. -I..    -pthread -DHAVE_PTHREAD=1 -DHAVE_ZLIB=1 -Wall -Wno-sign-compare  -fvisibility=hidden -MT google/protobuf/stubs/time.lo -MD -MP -MF $depbase.Tpo -c -o google/protobuf/stubs/time.lo google/protobuf/stubs/time.cc &&\
mv -f $depbase.Tpo $depbase.Plo
libtool: compile:  g++ -DHAVE_CONFIG_H -I. -I.. -pthread -DHAVE_PTHREAD=1 -DHAVE_ZLIB=1 -Wall -Wno-sign-compare -fvisibility=hidden -MT google/protobuf/stubs/time.lo -MD -MP -MF google/protobuf/stubs/.deps/time.Tpo -c google/protobuf/stubs/time.cc  -fPIC -DPIC -o google/protobuf/stubs/time.o
```

对比可以看到， 在编译选项中多出了 -fvisibility=hidden 参数。

最终的生成物如下：
```
./src/.libs/libprotoc.a
./src/.libs/libprotobuf-lite.a
./src/.libs/libprotobuf.a
```
