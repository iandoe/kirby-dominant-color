Extract an Image's dominant color - Kirby CMS Panel
===========================

![Screenshot](https://github.com/iandoe/kirby-dominant-color/raw/master/preview.jpg)

Simple kirby panel hook that will extract the most dominant color for a given image and store it in the file's metadata on the `color` field as an hex value eg: `#fefefe`.

This is useful for example when lazyloading images, Google uses the same technique in Google Images.

The hook will fire for any image you `upload` or `replace` in the panel.

## Installation

```
git submodule add git@github.com:iandoe/kirby-dominant-color.git site/plugins/dominantcolor
```

then run composer in the resulting directory

```
cd site/plugins/dominantcolor/
composer install
```

## Diplaying the value in the panel field

Combined with https://github.com/ian-cox/Kirby-Color-Picker
You can have the extracted color displayed in the panel when looking at the image your blueprint's file fields :

```
files:
  fields:
    color:
      label: Dominant Color
      type: color
```

## Using the value

The value will be available on the `image` object like such :

```
<?php $page->image('myimage.jpg')->color() ?>
```

## License

MIT

## Credits

All credits goes to @thephpleague for the actual color extracting process in PHP
https://github.com/thephpleague/color-extractor
