# Where-Is-My-Bread 🍞

## Description

A non-invasive, lightweight, lightning fast, WordPress plugin adding URL based breadcrumb support. Where-Is-My-Bread is a plug-and-play plugin with no required configuration.

## Retrieve the crumbs.

```php
<?php

/**
 * Retrieve the crumbs.
 * 
 * @since 1.0.0
 *
 * @return Array Crumbs array.
 */
get_crumbs()
```

## Retrieve the bread, a formated crumbs list.

```php
<?php

/**
 * Retrieve the bread, a formated crumbs list.
 * 
 * @since 1.0.0
 * 
 * @param Array $ingredients[separator] The crumb's separator. Default to &gt;.
 * @param Array $ingredients[offset] Crumbs offset. Accept positive/negative Integer. Default to 0. Refer to array_slice. https://www.php.net/manual/en/function.array-slice.php.
 * @param Array $ingredients[length] Crumbs length. Accept positive/negative Integer. Default to null. Refer to array_slice. https://www.php.net/manual/en/function.array-slice.php.
 * 
 * @return Array Formated crumbs list.
 */
get_bread( array $ingredients = array() )
```

### HTML5 structure output

```php
<ol class="🍞 bread" itemscope="" itemtype="https://schema.org/BreadcrumbList">
    <li class="crumb" itemprop="itemListElement" itemscope="" itemtype="https://schema.org/ListItem">
        <a itemprop="item" href="http://example.com/where/">
            <span itemprop="name">Where</span>
        </a>
        <meta itemprop="position" content="1">
    </li>
    &gt;
    <li class="crumb" itemprop="itemListElement" itemscope="" itemtype="https://schema.org/ListItem">
        <a itemprop="item" href="http://example.com/where/is/">
            <span itemprop="name">Is</span>
        </a>
        <meta itemprop="position" content="2">
    </li>
    &gt;
    <li class="crumb" itemprop="itemListElement" itemscope="" itemtype="https://schema.org/ListItem">
        <a itemprop="item" href="http://example.com/where/is/my/">
            <span itemprop="name">My</span>
        </a>
        <meta itemprop="position" content="3">
    </li>         
    &gt;
    <li class="crumb" itemprop="itemListElement" itemscope="" itemtype="https://schema.org/ListItem">
        <a itemprop="item" href="http://example.com/where/is/my/bread/">
            <span itemprop="name">Bread</span>
        </a>
        <meta itemprop="position" content="4">
    </li>
</ol>
```

### Styling

By default Where-Is-My-Bread has no associated stylesheet, but has two associated css classes:

- The `<ol>` tag comes with the css class, `🍞` or `bread` *(fallback)*.
- Each `<li>` tag comes with the class, `crumb`.

### Minimal css boilerplate (Optional)

```
.🍞,
.bread {
  list-style-type: none;
  margin:0;
  padding:0;
}

.🍞 li,
.bread li {
  display:inline-block;
}

.🍞 li.crumb:last-child a,
.bread li.crumb:last-child a {
  text-decoration: none;
  pointer-events: none;
  color: inherit;
}
```
