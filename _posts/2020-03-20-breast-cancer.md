---
layout: post
title: Breast cancer classification with FAST.AI and Deep Learning
subtitle: 
# gh-repo: daattali/beautiful-jekyll
# gh-badge: [star, fork, follow]
tags: [Deep Learning]
comments: true
---

### Introduction

The most common type of cancer in women is Breast cancer, and the most common form of breast cancer is invasive ductal carcinoma (IDC). Precise identification and categorization of breast cancer subtypes is an important clinical task, and the use of automated methods can save time and reduce error. Curretly, the procedure used to diagnose breast cancer is time intensive and can miss small malignant regions. In order to diagnose cancer, a portion of tissue is inserted on a glass slide. Afterwards a pathologist tests this slide under a microscope. To eventually identify malignant regions, the pathologist has to scan large regions where there is no cancer visually.  


Since these glass slides can now be digitized, computer vision can be used to speed up the workflow of a pathologist and to provide help for diagnosis. In this tutorial, you will learn how to train a FAST.AI deep learning model to predict breast cancer in breast histology images.



### Dataset
The dataset was originally curated by [Janowczyk and Madabhushi](https://www.ncbi.nlm.nih.gov/pubmed/27563488) and [Roa et al.](https://www.ncbi.nlm.nih.gov/pubmed/27563488) but is available in public domain on [Kaggle’s website](https://www.kaggle.com/paultimothymooney/breast-histopathology-images). It is consisted of 162 whole mount slide images of Breast Cancer (BCa) specimens scanned at 40x. 


In general, slide images are huge (spatial dimensions). As a result, **277,524** patches of size 50 x 50 pixels were extracted, including:

* 78,786 IDC positive (i.e., indicating breast cancer was found in the patch)
* 198,738 IDC negative (i.e., no breast cancer)


# Each patch’s file name is of the format: uxXyYclassC.png — > example 10253idx5x1351y1101class0.png . Where u is the patient ID (10253idx5), X is the x-coordinate of where this patch was cropped from, Y is the y-coordinate of where this patch was cropped from, and C indicates the class where 0 is non-IDC and 1 is IDC.


### Inspiration





You can write regular [markdown](http://markdowntutorial.com/) here and Jekyll will automatically convert it to a nice webpage.  I strongly encourage you to [take 5 minutes to learn how to write in markdown](http://markdowntutorial.com/) - it'll teach you how to transform regular text into bold/italics/headings/tables/etc.

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

![Crepe](https://s3-media3.fl.yelpcdn.com/bphoto/cQ1Yoa75m2yUFFbY2xwuqw/348s.jpg){: .center-block :}

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
