# More Flex

![](https://raw.githubusercontent.com/hoc-labs/images/main/responsive-flex-challenge2-spec.png)

## Requirements
* add the image to the top row using flex.
* make sure that the image does not stretch from its original proportions.
* the image should line up with
   the sidebar in the section
   below
* modify the bottom row to meet the new design layout.

### Flex Children

The child elements attempt to fill the available space, but it is not always predictable. 

In the image below, the two child elements are taking up equal widths.

```markup
<div class="hero">
        <div class="container row">
            <div class="hero__text">
                <h1>Responsive layouts don’t have to be a struggle</h1>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam.</p>
                <a href="#" class="btn">I want to learn</a>
            </div>
            <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam.</p>
        </div>
    </div>
```

![](https://raw.githubusercontent.com/hoc-labs/images/main/responsive-img-2.png)

### Images Stretch to Fill Available Space
But there can be issues when an image is one of the child elements, as the image will stretch to fill the available area.

In the markup below, I have removed the paragraph text on the left and added an image on the right. Because the height of the image is greater than the content on the left, the image is displaying at its default size, which is what we want.

```markup
 <div class="hero">
        <div class="container row">
            <div class="hero__text">
                <h1>Responsive layouts don’t have to be a struggle</h1>
                <a href="#" class="btn">I want to learn</a>
            </div>
            <img src="img/hero-img.jpg" alt="">
        </div>
    </div> 
```

![](https://raw.githubusercontent.com/hoc-labs/images/main/responsive-img-3.png)

But, if I add back in the paragraph on the left, the image on the right now stretches to fill the height of the container, and is out of proportion.

![](https://raw.githubusercontent.com/hoc-labs/images/main/responsive-img-1.png)

And becomes more stretched as the width is reduced.

![](https://raw.githubusercontent.com/hoc-labs/images/main/responsive-img-4.png)

### Wrapping img elements in a div
To solve this problem, you can wrap the img element in a `<div>` element. Then the `<div>` element will stretch, but the img element will not stretch within the parent div element.

```markup
    <div class="hero">
        <div class="container row">
            <div class="hero__text">
                <h1>Responsive layouts don’t have to be a struggle</h1>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam.</p>
                <a href="#" class="btn">I want to learn</a>
            </div>
            <div class="hero__img"><img src="img/hero-img.jpg" alt=""></div>
        </div>
    </div> 
   ```
Setting a border with a color is a very useful technique to observe what is happening. I have set the border of the parent `<div>` of the img element to red so you can see that the `<div>` is resizing, but not the contained `<img>` element.


![](https://raw.githubusercontent.com/hoc-labs/images/main/responsive-img-5.png)


![](https://raw.githubusercontent.com/hoc-labs/images/main/responsive-img-6.png)

### Solving Flex Child spacing

You can use the sibling CSS selector to select every pair of child elements.

First, add the col class selector to each of the child elements.

```css
.col + .col {
   margin-left:30px;
}
```

### Image max-width

Now that the img element is honoring its true size, we still need to deal with when that size is wider than the available space.

Here is what happens when that is the case.

![](https://raw.githubusercontent.com/hoc-labs/images/main/responsive-img-7.png)

To prevent that, we need to set the max-width CSS property on the img so that it will never be wider than its parent element.

``` css
img {
   max-width:100%;
}
```

With that change, the image will resize to fill its parent element.

![](https://raw.githubusercontent.com/hoc-labs/images/main/responsive-img-8.png)


