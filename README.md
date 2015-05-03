# Liquid Styleguide
Liquid is a main language to develop frontend for Shopify. Although it is quite simple,
inconsistent coding style sometimes makes reading it nightmares.

I have been trying to search for a coding style for Liquid but at the time, there is not
any. So I make this one and hope this help.

This is a styleguide for Liquid initially based on my personal taste. Please help me to improve it.

Since Liquid mostly consists of Javascript, CSS/SCSS and HTML and to avoid reinventing the wheel,
most of this styleguide inherits some well-known styleguides from GitHub (CSS, HTML)
and airbnb (Javascript).

## General

* Use `2 spaces` indentation (i.e. soft tabs).


* No trailing whitespace.


* End files with a single newline character.

## Liquid


* A space after `{{`, `{%` and before `}}`, `%}`:
```
# good
{{ so_nice }}
{% this_one_too %}

# bad
{{not_really}}
{%hmm_nah%}
```

* Spaces around `|`, `=`, ` == `, `!=`:
```
{{ shop.description | strip_html }}
{% assign beauty = 'coding_style' %}
{% if beauty == 'coding_style' and beauty != 'inconsistency' %}{% endif %}
```

* Indent one level in each `if`, `unless`, `for`, `paginate`:
```
{% paginate collection by 10 %}
  {% if true %}
    {% for product in collection.products %}
      Splendid!
    {% endfor %}
  {% endif %}
{% endpaginate %}
```

* Use `snake_case` for naming.


* Be careful when naming new variables because the scope of variables in Liquid is **global**.


* Try to put Javascript codes in `.js` files and place them in `assets` folder. Ideally include one `.js` file in each
page and that `.js` file contains all necessary Javascript codes for that page.


* Similar to CSS codes. Try to place all CSS codes in `.css` files or `.scss.liquid` files and place them in `assets` folder.

## HTML and SCSS/CSS

* Let's apply [GitHub's styleguide](http://primercss.io/guidelines/).


* For cleaner CSS codes, let's use SCSS by naming the CSS file as `style.scss.liquid` and include the file using `{{ 'style.scss.css' | asset_url | stylesheet_tag }}`. [More](https://ecommerce.shopify.com/c/ecommerce-design/t/you-can-now-use-scss-in-shopify-s-template-editor-133389).


* Let's try to apply [OOCSS](http://www.smashingmagazine.com/2011/12/12/an-introduction-to-object-oriented-css-oocss/).

## Javascript

* Let's apply the [styleguide from airbnb](https://github.com/airbnb/javascript). Following is the summary of the important ones:
* 
  * Use single quotes `''` for strings.
  * End files with a single newline character.
  * Use indentation when making long method chains. Use a leading dot, which emphasizes that the line is a method call, not a new statement.
  * Additional trailing comma:
  ```javascript
   // bad - git diff without trailing comma
  const hero = {
       firstName: 'Florence',
  -    lastName: 'Nightingale'
  +    lastName: 'Nightingale',
  +    inventorOf: ['coxcomb graph', 'mordern nursing'] // Notice: no comma here
  }
  
  // good - git diff with trailing comma
  const hero = {
       firstName: 'Florence',
       lastName: 'Nightingale',
  +    inventorOf: ['coxcomb chart', 'mordern nursing'], // Notice: trailing comma here
  }
  ```
  
  * Add semicolons after each statement.
  * Use camelCase when naming objects, functions, and instances.
  * Use PascalCase when naming constructors or classes.
  * Prefix jQuery object variables with a `$`:
  ```javascript
  // bad
  const sidebar = $('.sidebar');

  // good
  const $sidebar = $('.sidebar');
  ```
  
  * Cache jQuery lookups.
