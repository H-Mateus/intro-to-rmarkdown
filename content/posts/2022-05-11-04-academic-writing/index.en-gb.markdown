---
title: 04. Academic writing
author: Mateus Harrington
date: '2022-05-11'
slug: 04-academic-writing
categories:
  - R
tags:
  - R Markdown
summary: 'Considerations for academic writing, mainly how we can deal with references'
weight: 5
coverImage: ./img/academic_hat_bulbs.jpg
coverCaption: "Image credit: [Unsplash](https://unsplash.com/photos/ItFTJoh1A8c)"
coverMeta: out
coverSize: partial
thumbnailImage: ./img/academic.jpg
thumbnailImagePosition: left
bibliography: references.bib
csl: nature.csl
output:
  blogdown::html_page:
    toc: true
    number_sections: true
---

There are few additional aspects we have to think about for academic writing, this page covers the most important aspects of this.

Firstly, if you aren’t already using a [reference manager](https://en.wikipedia.org/wiki/Reference_management_software), then you really should be! Regardless of what you use for writing, a reference manager is a very useful way of building a collection of the papers you’ve read (or plan to read…), and allows you to easily insert citations into your writing. There are lots of software available, but I’d recommend [Zotero](https://www.zotero.org/) as it’s free and open-source (as all good software should be!) and it has a neat [browser plugin](https://www.zotero.org/download/) which makes adding references to Zotero relatively painless.

I provide links to some guides for setting up Zotero in the further resources page [here](../../../../2022/05/17/05-further-resources/).

Any decent reference manager should allow you to export your references as a `.bib` file though, and that’s all you need to do for this.

In terms of citation style, we can use the [Citation Style Language project](https://citationstyles.org/) to specify how our references should be structured. The [Zotero Style Repository](https://www.zotero.org/styles) is a good resource to find different journal styles. Just download the one you want and add the relevant key to the `YAML` header:

    csl: path/to/csl/file.csl

# Inserting citations

So once we have our `.bib` file from our reference manager we just need to insert the relevant citation keys into out document.

The syntax is to wrap the citation key/s in `[]` and seperate reference with a `;`. So an example would be:

`This study found x.[@ackerman2010; @afjehi-sadat2010]`

Which looks like this:

This study found x.<sup>1,2</sup>

Note that R Markdown will automatically insert a bibliography at the bottom of the document.

# Cross-references

We can easily reference figures and tables using the syntax `\@ref(tab:chuck-label-here)` for tables or `\@ref(fig:chuck-label-here)` for figures.
Note that numbered sections need to be enabled for the section cross-reference to display a number.

```` markdown
## Example cross-references {#example-section-label}

```{r cool-table, echo=FALSE}
knitr::kable(head(mtcars), caption = "Cool table")
```

Table \@ref(tab:cool-table) shows our awesome data.

```{r cool-figure, fig.cap='Cool figure', echo=FALSE}
plot(mtcars$mpg, mtcars$hp)
```

Figure \@ref(fig:cool-figure) shows our awesome data again.

See section \@ref(example-section-label) for more info on whatever.
````

Which looks like this:

## Example cross-references

|                   |  mpg | cyl | disp |  hp | drat |    wt |  qsec |  vs |  am | gear | carb |
|:------------------|-----:|----:|-----:|----:|-----:|------:|------:|----:|----:|-----:|-----:|
| Mazda RX4         | 21.0 |   6 |  160 | 110 | 3.90 | 2.620 | 16.46 |   0 |   1 |    4 |    4 |
| Mazda RX4 Wag     | 21.0 |   6 |  160 | 110 | 3.90 | 2.875 | 17.02 |   0 |   1 |    4 |    4 |
| Datsun 710        | 22.8 |   4 |  108 |  93 | 3.85 | 2.320 | 18.61 |   1 |   1 |    4 |    1 |
| Hornet 4 Drive    | 21.4 |   6 |  258 | 110 | 3.08 | 3.215 | 19.44 |   1 |   0 |    3 |    1 |
| Hornet Sportabout | 18.7 |   8 |  360 | 175 | 3.15 | 3.440 | 17.02 |   0 |   0 |    3 |    2 |
| Valiant           | 18.1 |   6 |  225 | 105 | 2.76 | 3.460 | 20.22 |   1 |   0 |    3 |    1 |

Table 1: Cool table

Table <a href="#tab:cool-table">1</a> shows our awesome data.

<div class="figure">

<img src="/posts/2022-05-11-04-academic-writing/index.en-gb_files/figure-html/cool-figure-1.png" alt="Cool figure" width="672" />
<p class="caption">
Figure 1: Cool figure
</p>

</div>

Figure <a href="#fig:cool-figure">1</a> shows our awesome data again.

See section <a href="#example-section-label">2.1</a> for more info on whatever.

# Collaboration

So collaboration with R Markdown can either be wonderful or a bit of a pain depending on who you’re working with.

Ideally, you’d use [Git](https://git-scm.com/) in combination with a Git repository hosting service like [GitHub](https://github.com/) or [GitLab](https://about.gitlab.com/), which would allow you to easily have an large number of people from different timezones easily working on the same document/s with a clear record of who has contributed what and when.

A great guide to using Git with R can be found [here](https://happygitwithr.com/)

Partically however, many academics won’t be familiar with Git and won’t want to learn (even though it isn’t that hard to get the basics…).
In these cases it’ll probably be easiest to compile to a Word doc and send your collaborators that to edit with tracked changes.
This will require you to incorporate their changes back into R Markdown though, so it can be a hassle unfortunately.

# References

<div id="refs" class="references csl-bib-body" line-spacing="2">

<div id="ref-ackerman2010" class="csl-entry">

<span class="csl-left-margin">1. </span><span class="csl-right-inline">Ackerman, P., Morrison, S. A., McDowell, S. & Vazquez, L. [Using the Spinal Cord Independence Measure III to measure functional recovery in a post-acute spinal cord injury program](https://doi.org/10.1038/sc.2009.140). *Spinal Cord* **48**, 380–387 (2010).</span>

</div>

<div id="ref-afjehi-sadat2010" class="csl-entry">

<span class="csl-left-margin">2. </span><span class="csl-right-inline">Afjehi-Sadat, L. *et al.* [Differential protein levels and post-translational modifications in spinal cord injury of the rat](https://doi.org/10.1021/pr901049a). *Journal of Proteome Research* **9**, 1591–1597 (2010).</span>

</div>

</div>
