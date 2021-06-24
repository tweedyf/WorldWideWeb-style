# WorldWideWeb-style
> See the web as TimBL intended it!

This is a light CSS reproduction of the stylesheet in Tim Berners-Lee's WorldWideWeb/Nexus 2.02 that you can implement on your own pages.

![screenshot](screenshot.png)

## Installation

* Copy the files from the <code>code</code> directory into your web directory
* Link the stylesheet in your HTML code:

`<link rel="stylesheet" type="text/css" href="styles.css">`

## Options

* Retro fonts (reproduced using the actual NeXTStep font files) can be turned on or off; the font files are included in the code directory. (Credit to the [WorldWideWeb Rebuild](https://worldwideweb.cern.ch/typography/) team.)
     * The fonts are Helvetica and [Olhfs](https://github.com/AlexHorovitz/Ohlfs-font-to-ttf-conversion)
* Likewise, TimBL's original horizontal rule image file is used for `hr` elements, but if you turn that off, you'll get the modern equivalent (a CSS-computed gradient) instead.

## How

The stylesheet was built using pixel values taken from `default.style` in `Nexus.app`. I've hard-coded them for a 610px-wide body (the default width of a Nexus browser window) but also converted to percentages for smaller screen widths.

See the original style document [here](default.style).

## Why

For retro fun! And because it's a really elegant stylesheet.

## Notes

* Ironically, pages styled with this stylesheet won't render correctly on WorldWideWeb: you'll get extra space in various places, including between headers and the first block of text. That's because for this CSS to work nicely, we need a starttag and endtag on all `p` elements, whereas WorldWideWeb was written for `p` as an empty element.
     * Here's a hack you can use though:
          * Use empty `p` elements anyway!
          * Wrap the first block of text after each `h` tag in `span` tags
          * Add the following extra styles to `styles.css`:
```css 
:is(h2, h3, h4, h5, h6) ~ span {
	margin-left: 90px;
	display: inline-block;
	}
@media (max-width: 610px) {
	:is(h2, h3, h4, h5, h6) ~ span {
		margin-left: 14.75%;
		}
}
```
* WorldWideWeb and other early browsers don't understand `br`, so the best way to put lines of text in a row without putting them in a list is to have `dt` elements without corresponding `dd` elements. You can do that here, but if you do, you'll need to add an empty `dt` before your first real one so that your text spans the container correctly. This is because of the CSS rule I've used to distinguish `dt`+`dd` pairs from singleton `dt` elements. I'm sorry!
