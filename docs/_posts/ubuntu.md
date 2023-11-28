#ubuntu

## apt
查看安装包安装了哪些文件
```
# 查看vim包安装了哪些文件，如果安装包没有安装，那么是查询不到的。
dpkg -L vim
```

## 输入法
ubuntu 22上默认的iBus输入法感觉不是很好用， 于是切换成fcitx
参考：[Linux下安装中文输入法总结](https://developer.aliyun.com/article/1135729)

卸载iBus
```
sudo apt purge ibus*
sudo apt autoremove
```

安装fcitx
```
sudo apt install fcitx-googlepinyin
# [可选] 如果需要自定义词库，可安装fcitx-tools 
sudo apt install fcitx-tools
```
