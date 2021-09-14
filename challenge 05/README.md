# Media Queries

This challenge is only going to focus on creating the media queries for the two sections below the nav bar. We'll tackle the nav bar in the next challenge.

Because we already built this site with desktop in mind first, we'll target our media queries for when the width is less than desktop width.

```css
@media (max-width:600px) {
   
}
```
**What breakpoint width value should you use?**

Play around with the page in the dev tools responsive view and see when the content starts to *fail*, meaning that it no longer looks good. Try to find a breakpoint across the entire page from top to bottom where you could shift to a new layout.

**What elements need to shift at the break point? (ignore navbar for now)**
- On both the top and the bottom, the content should stack instead of be in a row.
- Think about how you can do this. A single style is all that needs to be changed.
- Once the content is stacking, take a look again. Now there are some issues with the width of the content. How can you fix that?

## `<meta viewport>`
There is a meta setting that is very important for responsive layout. The viewport meta value specifies that the device width is equal to the viewport. If it is not set, then the browser will just shrink the content to fit instead of apply the media queries.

[MDN meta viewport reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Viewport_meta_tag)

```markup
<head>
    ...
    <meta name="viewport" 
      content="width=device-width, 
      initial-scale=1.0">
</head>
```

Experiment to see what happens when you comment out that meta tag in your html file.