# Flex Navigation

## Build Navigation Bar
* Get all the navigation items next to one another
* Add a space between all the items
* Expand the padding on the header
* Align the left part of the navbar with the other left content.

![](https://raw.githubusercontent.com/hoc-labs/images/main/responsive-challenge6.png)

## Push the Sign-in and Sign-up items to the right

![](https://raw.githubusercontent.com/hoc-labs/images/main/responsive-challenge6-2.png)

### There are a couple of solutions

**Create a style to push the last two items to the right**

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

**Create two child `<ul>` elements and have the parent `.nav` style set to flex, space-evenly**
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

To right-align the last item on the nav bar, we need to use the trick to add space to the left of each item.

```css 
.nav__item + .nav__item {
    margin-left:20px;
}
```

To confirm that this is working you can temporarily add a style, such as font-size:32px to see which elements are affected.

## Add a logo

The logo needs to be aligned in the vertical direction using align-items:center;

![](https://raw.githubusercontent.com/hoc-labs/images/main/responsive-challenge6-3.png)

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



