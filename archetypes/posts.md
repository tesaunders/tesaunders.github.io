---
title: "{{ replace .Name "-" " " | title }}"
date: {{ .Date }}
tags: ["first"]
author: "Tom Saunders"
draft: false
hidemeta: false
comments: false
cover:
    image: "<image path/url>" # image path/url
    alt: "<alt text>" # alt text
    caption: "<text>" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page
---