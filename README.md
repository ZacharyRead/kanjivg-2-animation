
# KanjiVG to Animation

By Zachary Read  
https://www.jlect.com

## Description

This Python 3 script will convert kanjiVG's SVG files into animations that reveal the stroke order of different kanji. All animations are done in accordance to the SVG animation standard, which is not supported by Internet Explorer. JavaScript is used only to provide the pause, play and reset features.

### Samples

![Sample 1 of animated kanji](examples/0589c-jlect.svg?raw=true "Sample 1 of animated kanji") 
![Sample 2 of animated kanji](examples/05766-jlect.svg?raw=true "Sample 2 of animated kanji") 
![Sample 3 of animated kanji](examples/05678-jlect.svg?raw=true "Sample 3 of animated kanji")

Note: Pause, play and restart features are integrated into the SVG files and rely on JavaScript.

## License
Creative Commons Attribution-ShareAlike 3.0 Unported (CC BY-SA 3.0)

http://creativecommons.org/licenses/by-sa/3.0/

## Dependencies

* KanjiVG :  https://github.com/KanjiVG/kanjivg (CC BY-SA 3.0)
* svg.path:  https://pypi.org/project/svg.path/

## Install and run steps

For Ubuntu:
```sh
# Install PIP (Package Installer for Python)
sudo apt install python3-pip

# Install svg.path parsing library for Python
pip install svg.path

# Clone repository. This will also clone the KanjiVG project into a subdirectory.
git clone https://github.com/ZacharyRead/kanjivg-2-animation.git

# Change directory and run Python script to create animated SVGs
cd ./kanjivg-2-animation
python3 ./kanjivg2animation.py
```

Please note that svg.path is very resource-intensive and very slow, so this script could take an extremely long time to parse the thousand svg files. Don't be surprised if it takes a couple hours.

## Adding the SVG files to your website

You can easily add the SVG files to any page using basic HTML:

```html
<img
  src="/converted/<FILENAME>-animated.svg"
  alt="Animated kanji character"
  height="100"
  width="100" />
```

If you're using PHP, the [utf8_to_unicode function described in this article](http://web.archive.org/web/20130414004049/http://www.randomchaos.com/documents/?source=php_and_unicode) can be used to call the files. See example below:

```php
<?php
$kanji = '食';
$kanji_to_unicode = utf8_to_unicode($kanji);
echo '<img src="/converted/' . $kanji_to_unicode . '-animated.svg" alt="Animated kanji character" height="100" width="100" />';
```

## Notes

You can edit the file `kanjivg2animation.py` to change the source directory (`/kanji/`) or the destination directory (`/converted/`) as needed.

## Similar projects

* https://github.com/mbilbille/dmak
* https://github.com/Kimtaro/kanjivg2svg
