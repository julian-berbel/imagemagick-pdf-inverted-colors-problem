## Related Info

StackOverflow post: https://stackoverflow.com/questions/76434449/imagemagic-converting-pdf-file-together-with-png-results-in-negated-colors

ImageMagick version:
```
Version: ImageMagick 7.1.1-8 Q16-HDRI x86_64 21129 https://imagemagick.org
Copyright: (C) 1999 ImageMagick Studio LLC
License: https://imagemagick.org/script/license.php
Features: Cipher DPC HDRI Modules
Delegates (built-in): bzlib cairo fontconfig freetype gslib heic jng jpeg jxl lcms ltdl lzma png ps rsvg tiff webp x xml zlib
Compiler: gcc (12.2)
```

GhostScript version:
```
10.01.1
```

Ran on alpine version:
```
NAME="Alpine Linux"
ID=alpine
VERSION_ID=3.18.0
PRETTY_NAME="Alpine Linux v3.18"
HOME_URL="https://alpinelinux.org/"
BUG_REPORT_URL="https://gitlab.alpinelinux.org/alpine/aports/-/issues"
```

### Commands used to generate files

```bash
magick convert -density 300 -colorspace CMYK -resize 1024 -quality 90 input.pdf output.png
magick convert input.png output.png -resize 3299x -append expected_result.png
```

```bash
magick convert \
input.png \
\( -density 300 -colorspace CMYK -resize 1024 -quality 90 input.pdf \) \
-resize 3299x -append \
actual_result.png
```
