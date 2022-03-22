# CImageMagick

A description of this package.

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
