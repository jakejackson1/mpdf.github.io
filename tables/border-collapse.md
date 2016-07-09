---
layout: page
title: Border collapse
parent_title: Tables
permalink: /tables/border-collapse.html
modification_time: 2015-08-05T11:59:45+00:00
---

In the border-collapse=collapse mode, the following rules determine which border style "wins" in case of a conflict 
(closely follows CSS 2.1 specifications i.e.  width &gt;&gt; CSS dominance (cell&gt;table) &gt;&gt; 
Top/Left &gt; Bottom/Right):

1. Borders with the 'border-style' of 'hidden' take precedence over all other conflicting borders. 
1. Narrow borders are discarded in favor of wider ones.
1. Styles are preferred in this order: 'double', 'solid', 'dashed', 'dotted', 'ridge', 'outset', 'groove', and the lowest: 'inset'.
1. If border styles differ only in color, then a style set on a cell wins over one on a table. 
1. When two elements of the same type conflict, then the one further to the left or top wins out.

Note that different browsers differ in the fine detail for complex cases.
