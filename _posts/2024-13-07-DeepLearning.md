---
title:  "Crash Course in Deep Learning"
date:   2024-07-13 15:06:11
categories: brdf rendering raytracing
excerpt: "An article introducing the basics of deep learning"
tags: [machine learning, deep learning]
layout: default
comments: false
permalink: /blog/:title
---

# {{page.title}}
      
<time datetime="{{ page.date | date_to_xmlschema }}">
  <em>{{ page.date | date: "%b %-d, %Y" }}</em>
</time>                      
          
![]({{site.baseurl}}/images/DL.jpg)

## Downloads

<div style="display: inline;">
	<a href="{{site.baseurl}}/files/CrashCourseDL.pdf">
		<img src="../images/pdf_brdf.png" style="float:left;">
	</a>
</div>

<div style="display: inline; top: 20px; left: 10px; position: relative;">
PDF version of the article is available for <a href="{{site.baseurl}}/files/CrashCourseDL.pdf">download here</a>.<br />  
<span style="position: relative; top: 5px;">Code accompanying the article can be found in the <a href="https://github.com/boksajak/Dx12NN">Github repository</a></span>
</div>  

## Abstract

<div style="text-align: justify; font-style: italic;">
This article helps to understand and implement BRDFs commonly used in game engines, for use in both rasterization and 
emerging realtime raytracing. I hope it will help to overcome the steep learning curve of this complex topic, and to 
understand how to render different materials. Various optimizations and approximations are discussed, and code is 
shown for all relevant parts. Accompanying source code is a single file which can be compiled for both C++ and HLSL, 
and can be easily integrated into rendering applications.  
</div>
         
## Bibliography
```
@misc{2024_Boksansky_DeepLearning,
	title=			{Crash Course in Deep Learning},
	author=			{Jakub Boksansky},
	year=			{2024},
	month=			{July
	howpublished=	{\url{https://boksajak.github.io/blog/DeepLearning}}
}
```
