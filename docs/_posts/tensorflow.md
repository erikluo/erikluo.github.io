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
bazel build --local_ram_resources=4096  --cxxopt="-D_GLIBCXX_USE_CXX11_ABI=1" --config=opt   //tensorflow:libtensorflow_cc.so
```
