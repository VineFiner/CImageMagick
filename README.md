# CImageMagick

A description of this package.

### 安装包管理工具

- MacOS

```
brew install pkg-config
```
- Linux

```
apt-get install pkg-config
```
### 安装 ImageMagick

- MacOS

```
brew install imagemagick
```

- Linux

```
sudo apt-get install imagemagick
```

### 配置包管理工具

```
For pkg-config to find imagemagick@6 you may need to set:
export PKG_CONFIG_PATH="/usr/local/opt/imagemagick@7/lib/pkgconfig"
```
- or

```
➜ echo 'export PKG_CONFIG_PATH="/usr/local/opt/imagemagick@7/lib/pkgconfig:$PKG_CONFIG_PATH"' >> ~/.zshrc
```

### 包查看器

```
pkg-config --list-all | grep -i ImageMagick
```

## To find the header file path for ImageMagick:

```
➜  CImageMagick pkg-config --cflags-only-I MagickWand
-I/usr/local/Cellar/imagemagick/7.1.0-8/include/ImageMagick-7
```

## And the linker flags:

```
➜  CImageMagick pkg-config --libs MagickWand
-L/usr/local/Cellar/imagemagick/7.1.0-8/lib -lMagickWand-7.Q16HDRI -lMagickCore-7.Q16HDRI
```

## Other link

```
 ➜  CImageMagickDemo pkg-config --cflags-only-other ImageMagick
 -Xpreprocessor -fopenmp -DMAGICKCORE_HDRI_ENABLE=1 -DMAGICKCORE_QUANTUM_DEPTH=16
```

## Run

```
swift run \
     -Xswiftc -I/usr/local/Cellar/imagemagick/7.1.0-28/include/ImageMagick-7 \
     -Xlinker -L/usr/local/Cellar/imagemagick/7.1.0-28/lib \
     -Xlinker -lMagickWand-7.Q16HDRI \
     -Xlinker -lMagickCore-7.Q16HDRI \
     -Xcc -DMAGICKCORE_HDRI_ENABLE=1 \
     -Xcc -DMAGICKCORE_QUANTUM_DEPTH=16 
```
