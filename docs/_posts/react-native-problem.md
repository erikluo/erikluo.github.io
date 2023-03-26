## react-native 调试问题记录

* hermes-engine下载失败： Error installing hermes-engine
    - 解决办法：下载到本地，然后修改环境变量：export HERMES_ENGINE_TARBALL_PATH=/Users/xxx/Downloads/hermes-runtime-darwin-v0.70.6.tar.gz
    - [stackoverflow](https://github.com/facebook/react-native/issues/31505)

* 在ScrollView中嵌入FlatList告警的问题
    - warning:VirtualizedLists should never be nested inside plain ScrollViews with the same orientation because it can break windowing and other functionality - use another VirtualizedList-backed container instead.
    - https://stackoverflow.com/questions/58243680/react-native-another-virtualizedlist-backed-container
    - https://blog.expo.dev/react-native-flatlist-made-easy-20fca51e0327

