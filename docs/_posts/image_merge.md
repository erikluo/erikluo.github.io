## 图片拼接
使用场景： 两张身份证图片纵向拼接后打印

### 方式一： ImageMagick
```
# 安装
sudo apt install imagemagick

# 横向拼接
convert 01.jpg 02.jpg +append 11.jpg

## 纵向拼接
convert 03.jpg 04.jpg -append 33.jpg
```

### 方式二： FFMpeg
```
# 垂直拼接
ffmpeg -i cat.jpg -i dog.jpg -filter_complex vstack vout.jpg

# 水平拼接
ffmpeg -i cat.jpg -i dog.jpg -filter_complex hstack hout.jpg

# 部分拼接
# 其中[0:v]和[1:v]分别表示第一张图片和第二张图片的画面。crop=960:1920:0:0表示截取大小为960:1920的区域，后面的0:0表示从坐标0:0点(左上角)开始截取，[img1]和[img2]是临时命名的截取后的图片。hstack表示水平拼接。
ffmpeg -i cat.jpg -i dog.jpg -filter_complex "[0:v]crop=960:1920:0:0[img1];[1:v]crop=960:1920:0:0[img2];[img1][img2]hstack" phoutput.jpg

```
