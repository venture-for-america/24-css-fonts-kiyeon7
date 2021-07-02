# CSS Fonts

## Overview

In this lesson we will do a quick review of CSS fonts from the video lecture in the prior lesson.

## What's Covered in This Lesson 

1. Review CSS Font Properties
2. Review Using Web Fonts

## Font Properties

There are many font properties you can adjust. As a developer there are so many things to remember. Over time you remember the things that you encounter regularly through daily use, but no developer knows everything. This makes it important to be comfortable searching for answers, reading documentation, and looking up the code you as you need it. In the case of CSS a good resource for properties is the Mozilla Devlopers Network CSS Property Reference (included in the resource links at the bottom of this lesson). However here are a few useful font properties and some of their possible values separated by `|` pipes.

`font-family: Arial, Helvetica, san-serif`

Font families are separated by commas allowing us fallback solutions. If the first font to the left doesn't load, the browser will try the next font to the right until a font loads or the browser falls back to a default font.

`font-size: 100% | 1em | 12pt | 16px`

Font sizing can be specified in many different measurements such as pixels, percents, and ems among others.

`font-style: normal | italic`

Font style can be set to normal or italic.

`font-weight: normal | bold`

Font weight specifies the thickness of text. You can provide a number 100 - 900 in hundreds only, or normal, bolder, or boldest.

`color: white | #FFF | rgba(255,255,255,1)`

Colors were discussed previously in detail, but it is one of my most used font properties. You can provide a value in color name, hex, rgb, rgba, hsl, or hsla. 

`font: bold 1em/2em Arial, sans-serif`

The short-hand property `font` allows you to specifiy font-weight, font-style, font-size/line-height, and font-family all in one place.

`text-align: left | center | right`

Text align does just what you're guessing it is. It aligns the text in any direction and you can also specify justified.

`text-decoration: none | overline | underline | line-through`

Text decoration is used mostly on links.

`text-indent: 1% | 1em | 12pt | 16px`

Text indents affect the first line of a paragraph.

`text-shadow: 3px 3px 10px #000`

Text shadow is a neat CSS3 property that allows you to provide in order: horizontal alignment, vertical alignment, feather, and shadow color. You can check browser support for this property at [caniuse.com](http://caniuse.com/).

`text-transform: none | uppercase | lowercase | capitalize`

Text transform converts the content text to whichever transform you specify.

`letter-spacing: normal | 1em | 12pt | 16px`

Letter spacing is the same as kerning; it is the space between characters.

`line-height: normal | 1em | 12pt | 16px`

Line height adjusts the space between lines of text.

`word-spacing: normal | 1em | 12pt | 16px`

Word spacing is the space between words. 

`word-wrap: normal | break-word`

Word wrap affects whether really long words will get hyphenated or not.

`white-space: normal | no-wrap`

White space affects whether a body of text within an element will wrap as it reaches the edge of the element's set width.

## Web Fonts

Web fonts are a great way to include fonts that are more specialized that may not be able to be loaded from your site visitor's computer. Below we will discuss @font-face, but first let's set up our local folder structure to include a special font. In your site project folder you would include a fonts folder and inside you would place any special fonts to include and eventually they would be uploaded to the webserver with your HTML and CSS pages.

```shell
my-website
├── css
│   └── style.css
├── fonts
│   ├── Avenir.eot
│   ├── Avenir.svg
│   ├── Avenir.ttf
│   └── Avenir.woff
└──index.html
```

Here we have placed our web font files in our fonts folder. You most likely will have only one file on your computer, but it is a good idea to convert your font into serveral different web font formats. This can be done using an online tool such as: [Web Font Generator](https://www.web-font-generator.com/) This is a great tool and you might want to bookmark this for future use. It allows you to upload your font from your computer and it will generate several web font formats such as: eot, svg, ttf, and woff. Different browsers prefer different formats hence why you might need 3 formats to ensure it will work in all browsers. Then in our CSS file at the top of our page we can link to this font as follows:

```css
@font-face {
  font-family: 'Avenir';
  src: url('../fonts/Avenir.eot?#iefix') format('embedded-opentype'),  url('../fonts/Avenir.woff') format('woff'), url('../fonts/Avenir.ttf')  format('truetype'), url('../fonts/Avenir.svg#Avenir') format('svg');
}

p {
  font-family: 'Avenir', Helvetica, sans-serif;
}
```

Inside the @font-face block surrounded by `{}` curly braces we label our font for future use using the `font-family` property. Then using the `src` property we point to the url location of our web font files and specify the format of each file type.

Then to use the font we simply reference the font name we set previously in the `font-family` property. So to apply to our `p` elements we simply set: ` p { font-family: 'Avenir', Helvetica, sans-serif; }`. Our font name, `'Avenir'`, is followed by fallback fonts `Helvetica` and `sans-serif` in case Avenir has any issue loading.

## Summary

- There are a wide range of font properties to adjust your text.
- We can load web fonts that might not be available on the site visitor's computer by telling our CSS to load them from our server instead.

## Resources

- [MDN - CSS Tutorials for Beginners](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Getting_started)
- [MDN - CSS Property Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference)
- [CSS3.info - Using Web Fonts](http://www.css3.info/preview/web-fonts-with-font-face/)
- [Web Font Generator](https://www.web-font-generator.com/)
- [CSS Performance & Organization, Best Practices](http://learn.shayhowe.com/advanced-html-css/performance-organization/)

<p class='util--hide'>View <a href='https://learn.co/lessons/css-fonts'>Fonts</a> on Learn.co and start learning to code for free.</p>
