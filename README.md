# Liquid Styleguide
Liquid is a main language to develop frontend for Shopify. Although it is quite simple to
learn, inconsistent coding style results in nightmares for us to read it.

I have been trying to search for a coding style for Liquid but at the time, there is not
any. So I make this one and hope this help.

This is a styleguide for Liquid initially based on my personal taste. Please feel free to
add anything if you want to.

Since Liquid mostly consists of Javascript, CSS/SCSS and HTML code, most of this
styleguide inherits those styleguides from GitHub.
## Liquid
* Use `2 spaces` indentation (i.e. soft tabs).
* A space after `{{`, `{%` and before `}}`, `%}`:
```
{{ so_nice }}
{% this_one_too %}

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

* Try to place Javascript codes in `.js` files. Ideally include one `.js` file in each
page and that `.js` file contains all necessary Javascript codes for that page.

* Similar to CSS codes. Try to place all CSS codes in `.css` files or `.scss.liquid` files.


## Javascript


## SCSS/CSS


## HTML

