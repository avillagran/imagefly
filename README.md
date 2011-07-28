## kohana-3-imagefly

Forked from: http://code.google.com/p/kohana-3-imagefly/

## So whats this all about?

This is a Kohana 3 module for resizing and caching images directly in your HTML markup via the image src attribute.

## Installation
Just like any Kohana module, enable and go!

1. Add the imagefly folder to your Kohana 3 modules directory or
	$ git submodule add git@github.com:avillagran/imagefly.git modules/imagefly
	$ git submodule update --init
2. Enable in your bootstrap.php
3. Enable the Kohana 3 Image module (required for imagefly)

## bootstrap.php

	Kohana::modules(array(
    	'image'    => MODPATH.'image',
    	'imagefly' => MODPATH.'imagefly',
    ));

## Configuration
You know how it's done. Copy the config.php file to your application/config directory and edit to your liking.

- cache_expire: How long before the browser checks the server for a new version of the modified image (Default: 1 Week)
- cache_dir: Path to the image cache directory you would like to use (Default: 'media/imagecache/')
- mimic_sourcestructure: Mimic the source file filestructure within the cache_dir (Default: TRUE). Useful if you have lots of images and do not want to store them in one level.

## Usage
Here's what you can do with imagefly in you HTML markup.

You can see actual examples over at this blog post: http://www.frontieradvertising.com.au/voice/2011/03/02/kohana-3-image-resizing-module-imagefly/

### Resize to exactly 100px width and height cropping from the center

	<img src="/imagefly/w100-c/path/to/image.jpg" />
OR

	<img src="/imagefly/h100-c/path/to/image.jpg" />

### Resize to exactly 100px width and 150px height cropping from the center

	<img src="/imagefly/w100-h150-c/path/to/image.jpg" />

### Resize proportionally until width is 100 pixels

	<img src="/imagefly/w100/path/to/image.jpg" />

### Resize proportionally until height is 100 pixels

	<img src="/imagefly/h100/path/to/image.jpg" />

### Resize proportionally until either the width or height is 100 pixels

	<img src="/imagefly/w100-h100/path/to/image.jpg" />

## Notes
- Imagefly will not process images when the width and height prams are the same as the source
- Images are scaled up if the supplied width or height params are lager then the source width or height
- Don't forget to make your cache directory writable.

## Compatibility

Imagefly will work on the Kohana 3.0.x and 3.1.x branch.

