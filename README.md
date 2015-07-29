# phpsvg
Edit and create SVG documents using Object-Oriented PHP

License: [GPL v3](http://www.gnu.org/licenses/gpl.html)

Automatically exported from code.google.com/p/phpsvg


## Version 0.8 Released

Changelog:
* Better code documentation
* Better error control
* Support for export images using Inkscape it's add exporting formats to png,ps,eps,pdf,plain-svg. Support windows Inkscape.
* Add inkscape as a fallback when imagemagic is not present. Each one will try to use other if fail.
* Support for humanreadable xml or not.
* Add a simple example.
* Removed some warnings and notices.
* Show and hide functions.
* Remove Element function.
* Support PHP 5.4 and PHP Strict mode.
* dded simple pixel art to vector example.
* Corrected the SVGText bug reported by users.
* Added support for SVGGroup and SVGClip, used to make the graph animation. 

## Features
Edit and create SVG Documents using Object Oriented PHP.
* Open and edit SVG and SVGZ (GZipped)
* Generate thumbnails or export to PNG, JPG, GIF,PS,EPS,PDF
* Support embebed or linked images.
* Use php features: SimpleXMLElement, GZip, Gd, Imagemagick.
* Can use inkscape to export some image formats.
* Well documented.

## Example use
```
<?php
require_once "svglib.php";

$svg = SVGDocument::getInstance( 'resource/apple.svg' ); //open to edit
//$svg = SVGDocument::getInstance( ); //default read to use

$rect = #create a new rect with, x and y position, id, width and heigth, and the style
$rect = SVGRect::getInstance( 0, 5, 'myRect', 228, 185, new SVGStyle( array( 'fill'   => 'red', 'stroke' => 'blue' ) ) );
$svg->addShape( $rect );

$text = SVGText::getInstance( 22, 50, 'myText', 'This is a text', $style );

$svg->asXML('output/output.svg'); //output to svg file
$svg->export('output/output.png'); //export as png
$svg->export('output/thumb32x32.png',32,32); //export thumbnail
$svg->output(); //echo with header to browser
?>
```
 
(Not working any more: Working examples in http://phpsvg.nostaljia.eng.br/)
