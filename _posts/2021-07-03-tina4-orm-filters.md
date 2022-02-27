---
title: Using Filters in Tina4 ORM
layout: post
author: Barco van Rhijn
category: Tina4
---
A normal ORM call in Tina4PHP includes a where function which is similar to what you may see in Laravel. However, the syntax more closely matches SQL. But once you have a lot of where conditions this becomes quite a long unwieldy line.

To solve this and make the conditions a bit more flexible you can use a filter variable and extending it a little.

So now I can send in the slug and category into my function and create the conditions dynamically. This would be even more useful in this example once you want to send in an array of slugs or categories and create the where condition in your SQL

```php

public function getPosts(string $slug, string $categories)
{
    $posts = new $posts();

    $filter = [];
    $filter[] = ["condition" => "slug = '{$slug}'",
                 "type" => "and"];
    $filter[] = ["condition" => "category = 'Holidays'" ,
                 "type" => "or"];
    
    $filter = $this->buildFilter($filter);


    $posts->select("title,excerpt,slug,content")
        ->where($filter)
        ->asResult();
}
```

So here's how I've tackled the issue of building out the filter conditions. I create a long string and add the Condition specified in the $filter array (above code).

An important bit is that I don't add the condition when the $where variable is empty.
```php
public function buildFilter(array $filters)
{
    $where = "";
    
    foreach ($filters as $filter)
    {
        switch (true)
        {
            case ($filter["type"] == "and"):
                (empty($where))
                ? $where = $filter["condition"] //true don't add AND
                : $where .= "AND {$filter["condition"]}" //2nd value add the AND
                ;
            case ($filter["type"] == "or"):
                (empty($where))
                ? $where = $filter["condition"]
                : $where .= "AND {$filter["condition"]}"
                ;
        }
    }
    
    return $where;
}
```
That's all there is to it.