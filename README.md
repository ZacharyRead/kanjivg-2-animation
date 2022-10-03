
# KanjiVG to Animation

By Zachary Read  
https://www.jlect.com

## Description

This Python 3 script will convert kanjiVG's SVG files into animations that reveal the stroke order of different kanji. All animations are done in accordance to the SVG animation standard, which is not supported by Internet Explorer. JavaScript is used only to provide the pause, play and reset features.

Last tested on Ubuntu 22.04.1 LTS with Python 3.10.6 and svg.path 6.2.

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
git clone --recurse-submodules https://github.com/ZacharyRead/kanjivg-2-animation.git

# Change directory and run Python script to create animated SVGs
cd ./kanjivg-2-animation
python3 ./kanjivg2animation.py
```

Please note that svg.path is very resource-intensive and very slow. Don't be surprised if it takes a couple hours to process the 12,000+ files.

## Adding the SVG files to your website

You can easily add the SVG files to any HTML page by embedding them directly without any other tags. See the pseudo-code below.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <title>Page title</title>
</head>
<body>
  <h1>Page title</h1>
  <!-- Embed the SVG code directly here -->
  <svg id="kvg-04e73" class="kanjivg" width="106" height="126" xmlns="http://www.w3.org/2000/svg" (...)>
  (...)
  </svg>
</body>
</html>
```

If you're using PHP, the [utf8_to_unicode function described in this article](http://web.archive.org/web/20130414004049/http://www.randomchaos.com/documents/?source=php_and_unicode) can be used to call the files. See example below:

```php
<?php

$kanji = '食';
$kanji_to_unicode = str_replace('u', '0', utf8_to_unicode($kanji));
$k2a_directory = $_SERVER['DOCUMENT_ROOT'] . '/kanjivg-2-animation/converted/';
$k2a_file_path = $k2a_directory . $kanji_to_unicode . '-animated.svg';

if (file_exists($k2a_file_path)) {
  include($k2a_file_path);
}
```

> :warning: While you can use an image tag (as shown below) to reference the SVG files, you will lose the JavaScript functionality.

```html
<!-- Not recommended -->
<img
  src="/converted/<FILENAME>-animated.svg"
  alt="Animated kanji character"
  height="100"
  width="100" />
```

## CSS tips

To resize the SVG, you can use the CSS transform property as shown below. You may also want to use `transform-origin: 0% 50%;` (left) or `transform-origin: 100% 100%;` (right-floated) to adjust the position of the scaled element.

```css
.kanjivg {
  transform: scale(2);
}
```

To remove or change the border:

```css
/* Remove border entirely */
.kanjivg rect {
  stroke: none;
}

/* Change border color and thickness */
.kanjivg rect {
  stroke-width: 1;
  stroke: #777;
}
```

## Notes

You can edit the file `kanjivg2animation.py` to change the source directory (`./kanjivg/kanji/`) or the destination directory (`./converted/`) as needed.

## Similar projects

* https://github.com/mbilbille/dmak
* https://github.com/Kimtaro/kanjivg2svg
