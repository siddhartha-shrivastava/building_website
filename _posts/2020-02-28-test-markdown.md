---
layout: post
title: Data Warehouse vs. Data Lake
subtitle: How does one is different from other
gh-repo: daattali/beautiful-jekyll
gh-badge: [star, fork, follow]
tags: [test]
comments: true
---

In this post I will try to explain the difference between the commonly used term Data Warehouse and not so common term 'Data Lake' (Although Data Scientists/ ML Engineers are pretty familiar with it)

I strongly encourage you to [take 5 minutes to learn how to write in markdown](https://markdowntutorial.com/) - it'll teach you how to transform regular text into bold/italics/headings/tables/etc.

Big Data has been around for now almost a decade, but during last couple of years its importance has moved from being 'an advantage' to 'system critical' or business critical. In here, I will try my best to explain the difference between the two of them.


While I am currently working extensively with Medical datasets, which somebody took painful efforts to clean and curate, its often that, the data recieved by researchers is limited as it may not fullfill from one to many criteria, thus may not make to the database. 
While discussing it with my couple of friends, regarding the data lake, I found that most of the people think data lake is an advnaced version of data warehouse with enhanced capabilty and more functions can be executed, which infact is not the case.

**First and Foremost, definitions**

### Data Warehouse
According to [Wikipedia](https://en.wikipedia.org/wiki/Data_warehouse):

“In computing, a data warehouse (DW or DWH), also known as an enterprise data warehouse (EDW), is a system used for reporting and data analysis, and is considered a core component of business intelligence.”

Apart from this, for quick pointers, we can understand that:


It is highly transformed and structured.

Data is defined for usage before loading the data warehouse.

And since, the data is defined beforhand for its purpose of use, it represents a biased picture 
**what it mean is, curated data used for e.g hospitality industry may represent something differnet about their customers than the data stored by Transportation industry**



Data Lake
Pentaho CTO James Dixon has generally been credited with coining the term “data lake”. He describes a data mart (a subset of a data warehouse) as akin to a bottle of water…”cleansed, packaged and structured for easy consumption” while a data lake is more like a body of water in its natural state. Data flows from the streams (the source systems) to the lake. Users have access to the lake to examine, take samples or dive in.


This is also a fairly imprecise definition. Let's add a few specific properties of a data lake:

All data is loaded from source systems. No data is turned away.

Data is stored at the leaf level in an untransformed or nearly untransformed state.

Data is transformed and schema is applied to fulfill the needs of analysis.

Next, le





**Here is some bold text**

## Here is a secondary heading

Here's a useless table:

| Number | Next number | Previous number |
| :------ |:--- | :--- |
| Five | Six | Four |
| Ten | Eleven | Nine |
| Seven | Eight | Six |
| Two | Three | One |


How about a yummy crepe?

![Crepe](https://s3-media3.fl.yelpcdn.com/bphoto/cQ1Yoa75m2yUFFbY2xwuqw/348s.jpg)

It can also be centered!

![Crepe](https://s3-media3.fl.yelpcdn.com/bphoto/cQ1Yoa75m2yUFFbY2xwuqw/348s.jpg){: .mx-auto.d-block :}

Here's a code chunk:

~~~
var foo = function(x) {
  return(x + 5);
}
foo(3)
~~~

And here is the same code with syntax highlighting:

```javascript
var foo = function(x) {
  return(x + 5);
}
foo(3)
```

And here is the same code yet again but with line numbers:

{% highlight javascript linenos %}
var foo = function(x) {
  return(x + 5);
}
foo(3)
{% endhighlight %}

## Boxes
You can add notification, warning and error boxes like this:

### Notification

{: .box-note}
**Note:** This is a notification box.

### Warning

{: .box-warning}
**Warning:** This is a warning box.

### Error

{: .box-error}
**Error:** This is an error box.
