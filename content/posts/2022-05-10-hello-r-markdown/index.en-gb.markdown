---
title: Hello R Markdown
author: Mateus Harrington
date: '2022-05-10'
slug: hello-r-markdown
categories:
  - R
tags:
  - R Markdown
keywords:
  - tech
summary: "R Markdown is a way of generating fully reproducible and dynamic documents, in which both text and code can be combined"
weight: 1
coverImage: ./img/rmarkdown_cover.jpg
coverMeta: out
coverSize: partial
thumbnailImage: ./img/rmarkdownoutputformats.png
thumbnailImagePosition: left
---



R Markdown is a way of generating fully reproducible and dynamic documents, in which both text and code can be combined. 
This means no more copying of results or images from other sources into a Word document, instead, these are generated from the document itself!

This is valuable for reducing the human errors that can emerge from copying data around (and save you lots of time!), and it makes it much clearer where the results are coming from, both of which greatly enhance reproducibility.
One can render a R Markdown file into HTML pages, or PDFs, or Word documents, slides or even whole websites!

This website is acutally make with R Markdown via a great little package called [`blogdown`](https://github.com/rstudio/blogdown)

This website houses the resources to accompany the session "Introduction to R Markdown", first presented at the [Researcher Summer school at Keele University 2022](https://www.keele.ac.uk/kiite/conferences/researchersummerschool/).
The session and this site aims to provide a gentle introduction to using R Markdown, with a focus on scientific writing.

# Some quick examples

Here's a quick preview of some R code and what the results can look like:


```r
summary(cars)
##      speed           dist       
##  Min.   : 4.0   Min.   :  2.00  
##  1st Qu.:12.0   1st Qu.: 26.00  
##  Median :15.0   Median : 36.00  
##  Mean   :15.4   Mean   : 42.98  
##  3rd Qu.:19.0   3rd Qu.: 56.00  
##  Max.   :25.0   Max.   :120.00
fit <- lm(dist ~ speed, data = cars)
fit
## 
## Call:
## lm(formula = dist ~ speed, data = cars)
## 
## Coefficients:
## (Intercept)        speed  
##     -17.579        3.932
```

# Including Plots

You can also embed plots. See Figure <a href="#fig:pie">1</a> for example:


```r
par(mar = c(0, 1, 0, 1))
pie(
  c(280, 60, 20),
  c('Sky', 'Sunny side of pyramid', 'Shady side of pyramid'),
  col = c('#0292D8', '#F7EA39', '#C4B632'),
  init.angle = -50, border = NA
)
```

<div class="figure">
<img src="/posts/2022-05-10-hello-r-markdown/index.en-gb_files/figure-html/pie-1.png" alt="A fancy pie chart." width="672" />
<p class="caption">Figure 1: A fancy pie chart.</p>
</div>
