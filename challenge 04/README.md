# Flex Navigation

## Build Navigation Bar
Initial requirements:
* Display the navigation in a single row using flex.
* Add spacing between all the items (use sibling CSS selector/margin-left)
* Expand the padding on the header.
* Align the left of the navbar with the main content.

![](https://raw.githubusercontent.com/hoc-labs/images/main/responsive-challenge6.png)

## Changes to the Nav Bar

### Push the Sign-in and Sign-up items to the right

![](https://raw.githubusercontent.com/hoc-labs/images/main/responsive-challenge6-2.png)

### There are a couple of solutions

**Option 1 - Create a style to push the last two items to the right**

By adding a style to the first item you want to push to the right and setting the margin-left of that style to auto, the browser will take up all of the available space for the left margin, thereby pushing everything to the right.

```markup
<li class="nav__item nav__item--push-right">
  <a href="#" class="nav__link">Sign In</a>
</li>
```

```css
.nav__item--push-right {
    margin-left: auto;
}
```

**Option 2 - Separate the child `<li>`> elements into two `<ul>` lists and have the parent `.nav` style set to flex, space-between, which pushes each child to the margins.**
```markup
<nav class="nav">
    <ul class="nav__list">
        <li class="nav__item"><a href="#" class="nav__link">Home</a></li>
        <li class="nav__item"><a href="#" class="nav__link">About</a></li>
        <li class="nav__item"><a href="#" class="nav__link">Contact</a></li>
    </ul>
    <ul class="nav__list">
        <li class="nav__item"><a href="#" class="nav__link">Sign In</a></li>
        <li class="nav__item">
          <a href="#" class="nav__link nav__link--button">Sign up</a>
        </li>
    </ul>
</nav>
```

```css
.nav {
    display:flex;
    justify-content: space-between;
}
```
## Add a logo

Place the logo before of the `<nav>` element and wrap the img in an `<a>` element. 

![](https://raw.githubusercontent.com/hoc-labs/images/main/responsive-challenge6-3.png)

You can see that the logo is not aligned vertically with the other navbar items.

![](https://raw.githubusercontent.com/hoc-labs/images/main/responsive-navbar-1.png)

To fix this, we can center the logo element by creating a flexbox for the single element.

```css
.logo {
    display:flex;
    justify-content: center;
    align-items: center;
    margin-right:20px;
    border: solid 3px blue;
}
```

![](https://raw.githubusercontent.com/hoc-labs/images/main/responsive-navbar-2.png)

## Center the primary nav items

```markup
<ul class="nav__list nav__list--primary">
```

```css
nav__list--primary {
  margin: 0 auto;
}
```

![](https://raw.githubusercontent.com/hoc-labs/images/main/responsive-challenge6-4.png)





