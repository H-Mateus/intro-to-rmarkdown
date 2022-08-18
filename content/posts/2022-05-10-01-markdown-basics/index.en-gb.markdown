---
title: 01. Rational and motivations
author: Mateus Harrington
date: '2022-05-10'
slug: rational-and-markdown-basics
categories:
  - R
tags:
  - R Markdown
summary: 'Why bother with Markdown in the first place?'
weight: 2
coverImage: ./img/i_love_markdown.png
coverMeta: out
coverSize: partial
thumbnailImage: ./img/i_love_markdown.jpg
thumbnailImagePosition: left
---

Personally, I find it easy to learn when I've a decent grasp as to why I should bother, and a bit of contextualising can help with this.
To that end, I'll outline a bit of history and hopefully convince you why writing in plain text carries significant advantages compared to something like Word.

I'll include a few simple formatting examples to illustrate, but feel free to skim the resources above and skip this page if you're already sufficiently convinced this is a thing worth leaning.

# Markup VS WYSIWYG paradigms

Markdown is an example of a [markup language](https://en.wikipedia.org/wiki/Markup_language).
A markup language is a set of rules for describing the format of a document within the document itself.
This is in contrast to a ["what you see is what you get" (WYSIWYG)](https://en.wikipedia.org/wiki/WYSIWYG) style of editing you'll likely be familiar with from Microsoft Word.

In the WYSIWYG paradigm, the application embeds the formating in the file format in an opaque manner which then necessitates software that can parse that particular file type to be able to view or edit the file.
If you're using a Windows PC, try opening a Word document in notepad and see what happens.
Notice how the file can really be viewed?
This is because notepad is primarily for viewing and editing plaintext files, and so it doesn't know how to read the Word file.

So in Word, you'd click a button to make the text bold, and you'd see the text change as you did this.
By contrast, in a markup language, you'd have to use some kind of text to denote that the it should be bold.
In Markdown we can do this by wrapping out text with two `*`, for example:

- so to get: **this text is bold** we can use `**this text is bold**`
- and for *italics* use a single `*`: *this text is in italics* = `*this text is in italics*`
- and to do both we unsurprisingly use three: ***this is bold and italicised*** = `***this is bold and italicised***`

# The advantages of plaintext

You may be thinking that this seems more complicated than just clicking a button, so what's the advantage doing things the plaintext way?

- **Versatility**. Markdown can be used for everything from notes, books, presentations, websites to academic papers
- **Portability**. No matter what device or operating system you are, or ever will use, you can be confident that you will be able to view and edit any plaintext document. There are literally hundreds of text editors you can choose from too, so you're sure to find one that suits your needs
- **Durability**. Ever wonder what you happen if Microsoft just up and decided you need to pay £10 every time you wanted to open a Word doc? What if you had to pay per edit? What if they just scraped the software and no longer supported it? If all the documents you'd created throughout your professional life with made in Microsoft Office, you'd be kinda screwed. Not so with plaintext. Since markup languages are just simple formatting rules, no one owns them, and no one can take them away from you, meaning your work is safe so long as computers exist 

# How do the outputs work?

So how can we make webpages or a pdf from Markdown?
Well let's think about webpages.
A webpage is just a [HTML](https://en.wikipedia.org/wiki/HTML) file, which stands for HyperText **Markup** Language.
Notice the familiar word in there?
html is just another markup language, and so it's relatively easy for a piece of software to translate between markup languages.

In html, to make text bold we wrap the text between a tag like so `<b> this is some bold text </b>`.
So a piece of software like [pandoc](https://pandoc.org/) can read in a Markdown file and translate the formatting to html, thus giving you a new file you can put up as a webpage (Figure <a href="#fig:pandoc-img">1</a>).
This is part of the reason why plaintext formats are so versatile.



<div class="figure">
<img src="pandoc.png" alt="An illustration of pandoc conversions" width="60%" />
<p class="caption">Figure 1: An illustration of pandoc conversions</p>
</div>

# What does R Markdown add?

All R Markdown adds is an extra layer prior to producing outputs.
Before pandoc is used, `knitr` runs through the document looking for any R code to evaluate (Figure <a href="#fig:rmarkdown-workflow">2</a>)
We can therefore include code chunks or in-line code to generate our plots, tables and stats, and have the results included in our output formats!



<div class="figure">
<img src="rmarkdown_workflow.png" alt="An illustration of the R Markdown compilation" width="60%" />
<p class="caption">Figure 2: An illustration of the R Markdown compilation</p>
</div>

