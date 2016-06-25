#KanjiVG to Animation
By Zachary Read
https://www.jlect.com


##Description

This Python 3 script will convert kanjiVG's SVG files into animations that reveal the stroke order of different kanji. All animations are done in accordance to the SVG animation standard, which is not supported by Internet Explorer. JavaScript is used only to provide the pause, play and reset features.

##License
Creative Commons Attribution-ShareAlike 3.0 Unported (CC BY-SA 3.0)

http://creativecommons.org/licenses/by-sa/3.0/

##Prerequisites

* kanjiVG :  https://github.com/KanjiVG/kanjivg (CC BY-SA 3.0) [replace the /kanji/ folder with the /kanji/ folder provided by kanjiVG]
* svg.path:  https://pypi.python.org/pypi/svg.path [place in /path/ subfolder]

##Usage

If needed, edit the /kanji/ directory in the Python file with whatever folder contains the kanjiVG files, then update the /converted/ directory to indicate where the converted files should be placed.

Please note that svg.path is very resource-intensive and very slow, so this script could take an extremely long time to parse the thousand svg files.

##Similar projects:

* https://github.com/mbilbille/dmak
* https://github.com/Kimtaro/kanjivg2svg
