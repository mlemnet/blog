---
date: '{{ .Date }}'
draft: true
title: '{{ replace .File.ContentBaseName "-" " " | title }}'
description: ""
tags: []
categories: []
cover:
  image: ""
  caption: ""
  hidden: false
---

<!--
  Recommended post structure:
  content/posts/post-slug/
    index.md          <- this file
    images/           <- all photos/screenshots go here
      photo1.jpg
      screenshot.png

  Reference images in markdown: ![alt text](images/photo1.jpg)
-->
