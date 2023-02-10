---
layout: post
title:  "Iterating over lists in Bridgetown Frontmatter"
date:   2023-02-09
categories: updates
blurb: "A solution for using ERB to display lists of frontmatter items"
---

While building this site using Bridgetown, I bumped into an issue.

&nbsp;

I wanted to create lists in the frontmatter of each item in a collection. For my "projects" collection, I wanted a list of tags. And then in the HTML, I wanted to iterate over each tag and display it as a badge.

&nbsp;

I tried a couple different ways to fix this but nothing was working, until I found a solution.

&nbsp;

My frontmatter looks like this:

```
tags:
- elixir
- GIS
- mapping
```

&nbsp;

And in my view I have:
```
 for tag in project.data.tags
   tag
 end
```

&nbsp;

It seems simple but I couldn't find this in the docs anywhere so I wanted to share. Hope it helps!
