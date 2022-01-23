---
title: "{{ replace .Name "_" " " | title }}"
date: {{ .Date }}
# weight: 1
# aliases: ["/first"]
tags: ["computer science", "movies", "baking", "cooking", "misc"]
author: "Akshat Harit"
showToc: true
TocOpen: false
draft: true
hidemeta: false
comments: true
description: "DESC TEXT"
canonicalURL: "https://akshat-harit.github.io/posts/{{.Name}}/"
disableShare: false
disableHLJS: true
hideSummary: false
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShareButtons: ["reddit", "ycombinator", "facebook"]

cover:
    image: "<image path/url>" # image path/url
    alt: "{{ replace .Name "_" " " | title }}"
    caption: "{{ replace .Name "_" " " | title }}"
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page
editPost:
    URL: "https://github.com/akshat-harit/akshat-harit.github.io/content"
    Text: "Suggest Changes" # edit text
    appendFilePath: true # to append file path to Edit link
---