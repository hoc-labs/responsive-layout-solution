# Responsive Layout

## Exercise 01 - Percentages vs Fixed-width 

### Percentages allow content to be responsive
By default, a web page is responsive. A block element will fill 100% of its parent element and text will wrap. Setting fixed widths creates problems for responsive design.

* View index.html in the browser with the responsive view enabled in the dev tools and see how the parent and child elements respond to changes in the width.
* Add the following styles to the **parent** element.
`
{
  width:900px;
  margin:0 auto;
}
`
and view the page again. As you can see, the fixed-width is causing horizontal scrolling to activate.

![](https://raw.githubusercontent.com/hoc-labs/images/main/responsive-scrolling.png)

* Change the width to be 80% and observe again. Now the parent element is responsive to the change in the size of the overall window.
   Add the following styles to the **child** element.
`
{
  width:750px;
}
`. As you can see, the child element will overflow the parent element when the width exceeds the available window width.
* The default behavior is for the content to overflow so that information is not lost, but it requires scrolling to see it.
* Add some text from [loremipsum.io](https://loremipsum.io/) to the child element to observe the overflowing text.

![](https://raw.githubusercontent.com/hoc-labs/images/main/responsive-overflow.PNG)

* add the following style `{ overflow:hidden}` to the child element and observe what happens. We now have lost the ability to see the text, and this is not what we want.
* remove the width and the overflow properties on the child and observe that the default behavior is for the content of the child to fill 100% of the parent element so there is no need to set a fixed-width on a child element.

If you set a percentage on a child element that is less than 100%, then that percentage will be relative to the parent element.

### Percentages are Relative to Parent Element Width

* add `width:50%` to the child element and view again. Now you can see that the child content will always fill 50% of the parent element's width.

### Problems with fixed heights
Setting a fixed-height causes the same issue as setting a fixed width. Notice as you decrease the width of the container, the content will overflow in the vertical direction.

If you need more vertical space, you should use padding.

### Limiting max width of content
Having text spread all the way across the screen is not desirable. It is hard to read. In order to still have the content be responsive, but also limit the width of the content, you can specify the max-width property.

* Add `max-width:750px` on the child element and observe what effect this has on the content relative to the overall width.

## Challenge 1
Modify challenge1.html/css files to meet the following conditions:
* Limit the total width of the intro-content to about half of it's parent's width.
* Stop the text from overflowing out the bottom at small screen widths.

## Challenge 2
Modify challenge2.html/css files to meet the following conditions:
* Keep the text inside .intro-content in the same place, but have the background extend from one side of the viewport to the other, no matter how wide or narrow the browser is.
* Limit the maximum width of the text in the bottom area.

![](https://raw.githubusercontent.com/hoc-labs/images/main/responsive-challenge2.png)

















