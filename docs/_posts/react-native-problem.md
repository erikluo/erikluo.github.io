## react-native 调试问题记录

* hermes-engine下载失败： Error installing hermes-engine
    - 解决办法：下载到本地，然后修改环境变量：export HERMES_ENGINE_TARBALL_PATH=/Users/xxx/Downloads/hermes-runtime-darwin-v0.70.6.tar.gz
    - [stackoverflow](https://github.com/facebook/react-native/issues/31505)