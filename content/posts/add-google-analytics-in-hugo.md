---
title: "Add Google Analytics in Hugo"
date: "2019-01-16"
author: "hp.huang"
draft: false
categories: [hugo]
tags: [hugo,ga]
---

> This is an example for tracking the pageview of Hugo blog which theme is [hugo tale](https://themes.gohugo.io/tale-hugo/)

# Getting Started
1. add tracking code in `config.toml`
{{< highlight bash >}}
googleAnalytics = "UA-XXX-X"
{{< /highlight >}}

2. for home page, add Hugo's [interanl google analytics template](https://gohugo.io/templates/internal/#use-the-google-analytics-template) in `layouts/partials/index/introduction.html`
{{< highlight bash >}}
mkdir layouts && cd layouts
mkdir partials && cd partials
mkdir index && cd index
echo "{{ template \"_internal/google_analytics_async.html\" . }}" > introduction.html
{{< /highlight >}}

3. for post page, add Hugo's [interanl google analytics template](https://gohugo.io/templates/internal/#use-the-google-analytics-template) in `layouts/partials/single/header.html`

# Reference
- https://gohugo.io/templates/internal/#google-analytics