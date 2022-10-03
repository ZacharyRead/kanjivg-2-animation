
# KanjiVG to Animation

By Zachary Read  
https://www.jlect.com

## Description

This Python 3 script will convert kanjiVG's SVG files into animations that reveal the stroke order of different kanji. All animations are done in accordance to the SVG animation standard, which is not supported by Internet Explorer. JavaScript is used only to provide the pause, play and reset features.

## License
Creative Commons Attribution-ShareAlike 3.0 Unported (CC BY-SA 3.0)

http://creativecommons.org/licenses/by-sa/3.0/

## Prerequisites

* kanjiVG :  https://github.com/KanjiVG/kanjivg (CC BY-SA 3.0) [replace the /kanji/ folder with the /kanji/ folder provided by kanjiVG]
* svg.path:  https://pypi.python.org/pypi/svg.path

## Install and run steps

For Ubuntu:
```sh
# Install PIP (Package Installer for Python)
sudo apt install python3-pip

# Install svg.path parsing library for Python
pip install svg.path

# Clone relevant repositories
git clone https://github.com/KanjiVG/kanjivg.git
git clone https://github.com/ZacharyRead/kanjivg-2-animation.git

# Copy files over
cp ./kanjivg/kanji/*.svg ./kanjivg-2-animation/kanji/

# Change directory and run Python script to create animated SVGs
cd ./kanjivg-2-animation
python3 ./kanjivg2animation.py
```

Please note that svg.path is very resource-intensive and very slow, so this script could take an extremely long time to parse the thousand svg files. Don't be surprised if takes upwards of an hour.

## Adding the SVG files to your website

You can easily add the SVG files to any page using basic HTML:

```html
<img
  src="/converted/<FILENAME>-jlect.svg"
  alt="Animated kanji character"
  height="100"
  width="100" />
```

If you're using PHP, the [utf8_to_unicode function described in this article](http://web.archive.org/web/20130414004049/http://www.randomchaos.com/documents/?source=php_and_unicode) can be used to call the files. See example below:

```php
<?php
$kanji = '食';
$kanji_to_unicode = utf8_to_unicode($kanji);
echo '<img src="/converted/' . $kanji_to_unicode . '-jlect.svg" alt="Animated kanji character" height="100" width="100" />';
```

## Notes

You can edit the file `kanjivg2animation.py` to change the source directory (`/kanji/`) or the destination directory (`/converted/`) as needed.

## Similar projects

* https://github.com/mbilbille/dmak
* https://github.com/Kimtaro/kanjivg2svg
