---
title: How to compare strings in twig
layout: post
author: Barco van Rhijn
category: twig
---
Twig supports several operators that are similar to the ones in PHP. But often there are simplified versions like

### PHP
```php
// Exact match
if ($x === $y) 
? echo true 
: echo false
;
```
### Twig
```twig
{% raw %}
{% if x is same as y %}
{% endraw %}
```