---
title: 05. Further resources
author: Mateus Harrington
date: '2022-05-17'
slug: 05-further-resources
categories:
  - R
tags:
  - R Markdown
summary: 'A list of resources for further learning'
weight: 6
coverImage: ./img/i_love_markdown.png
coverCaption: "Image credit: [Unsplash](https://unsplash.com/photos/ItFTJoh1A8c)"
coverMeta: out
coverSize: partial
thumbnailImage: ./img/i_love_markdown.jpg
thumbnailImagePosition: left
---

# Markdown

If you want some great documentation on Markdown, see the excellent [Markdown guide here](https://www.markdownguide.org/getting-started/).
There are also several free online editors you can use to play around with Markdown, [Dillinger](https://dillinger.io/) is one of best.

# Quarto

[Quarto](https://quarto.org/) is the next generation of R Markdown, being made by some of same developers.
The Quarto website has some really nice documentation, so I'd recommend checking it out.

The intention appears to be to move away from a dependence on R itself, and make the framework more language agnostic.
The main differences I've noticed thus far and small [changes to YAML keys](https://quarto.org/docs/computations/r.html#output-formats), a [different chunk option style](https://quarto.org/docs/computations/r.html#chunk-options) (though it appears to be backwards compatible) and a neat [Div and Span](https://quarto.org/docs/authoring/markdown-basics.html#divs-and-spans) system for controlling some more fancy formatting options in a universal manner.

The developers currently seem to intend on maintaining R Markdown, but will likely only be adding any new features to Quarto moving forward.

I like what I've seen from my initial experimentation, and I'd probably suggest newcomers may wish to just focus on Quarto rather than R Markdown itself.

It should be noted that Quarto is pretty young, and some functionality possible in R Markdown isn't functional in Quarto yet (a good example [here](https://github.com/quarto-dev/quarto-cli/issues/1959)), but the devs seem to working well to get to full feature parity in the nearish future.

The recent RStudio conf had a nice workshop on Quarto that was recorded:

  - [Quarto workshop video](https://www.youtube.com/watch?v=yvi5uXQMvu4)

# Zotero

Here are a couple of guides to setting up Zotero to play nicely with R Markdown:

- A written guide [here](https://gsverhoeven.github.io/post/zotero-rmarkdown-csl/)
- Another [here](https://www.anthonyschmidt.co/post/2021-10-25-a-zotero-workflow-for-r/)
