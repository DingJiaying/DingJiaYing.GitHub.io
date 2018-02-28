---
layout: page
title: "Tags"
description: "哈哈，你找到了我的文章基因库"  
header-img: "img/semantic.jpg"  
---

{% assign sorted_categories = site.categories | sort %} {% for category in sorted_categories %}

### {{ category | first }}

1. {% for post in category.last %}

2. {{ post.date | date:"%Y-%m-%d" }} [{{ post.title }}](https://github.com/Demo-du/Demo-du.github.io/blob/master/pages/%7B%7B%20post.url%20%7D%7D)

3. {% endfor %}

{% endfor %}