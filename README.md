# WorldWideWeb-style
> See the web as TimBL intended it!

This is a light CSS reproduction of the stylesheet in Tim Berners-Lee's WorldWideWeb/Nexus 2.02 that you can implement on your own pages.

![screenshot](screenshot.png)

## Installation

* Copy the files in the <code>code</code> directory into your web directory
* Link the stylesheet in your HTML code:

`<link rel="stylesheet" type="text/css" href="styles.css">`

## Options

* Retro fonts (taken from the actual NeXTStep font files) can be turned on or off; the font files are included in the code directory. (Credit to the [WorldWideWeb Rebuild](https://worldwideweb.cern.ch/typography/) team.)
* Likewise, TimBL's original horizontal rule image file is used for `hr` elements, but if you turn that off, you'll get the modern equivalent (a CSS-computed gradient) instead.

## How

The stylesheet was built using the pixel values in `default.style` in `Nexus.app`. They're hard-coded for a 610px-wide body (the default width of a Nexus browser window) but converted to percentages for smaller screen widths.

See the original style document [here](default.style).
