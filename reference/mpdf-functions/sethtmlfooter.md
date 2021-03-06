---
layout: page
title: SetHTMLFooter()
parent_title: mPDF functions
permalink: /reference/mpdf-functions/sethtmlfooter.html
modification_time: 2015-08-05T12:01:03+00:00
---

(mPDF >= 1.2)

SetHTMLFooter – Sets an HTML page footer

# Description

void **SetHTMLFooter** ( string <span class="parameter">$html</span> [, string <span class="parameter">$side</span> ])

Set an HTML page footer.

# Parameters

<span class="parameter">$header</span>

This parameter specifies the content of the page footer as a string of valid HTML code.

<span class="smallblock">DEFAULT</span>: <span class="smallblock">BLANK</span>

<span class="parameter">$side</span>

Specify whether to set the footer for <span class="smallblock">ODD</span> or <span class="smallblock">EVEN</span> pages in a <span class="smallblock">DOUBLE-SIDED</span> document.

<span class="smallblock">DEFAULT</span>: 'O'

**Values** (case-sensitive)

O - set the footer for <span class="smallblock">ODD</span> pages

E - set the footer for <span class="smallblock">EVEN</span> pages

<span class="smallblock">BLANK</span> - set the footer for <span class="smallblock">ODD</span> pages

<div class="alert alert-info" role="alert">**Note:** Important Difference - <a href="{{ "/reference/mpdf-functions/setheader.html" | prepend: site.baseurl }}">SetHeader()</a> and <a href="{{ "/reference/mpdf-functions/setfooter.html" | prepend: site.baseurl }}">SetFooter()</a> called without specifying a <span class="parameter">$side</span> sets both <span class="smallblock">ODD</span> &amp; <span class="smallblock">EVEN</span> headers/footers; **SetHTMLHeader()** and <a href="{{ "/reference/mpdf-functions/sethtmlfooter.html" | prepend: site.baseurl }}">SetHTMLFooter()</a> without a <span class="parameter">$side</span> - set <span class="smallblock">ODD</span> page header/footer only as default</div>

# Changelog

<table class="table"> <thead>
<tr> <th>Version</th><th>Description</th> </tr>
</thead> <tbody>
<tr>
<td>1.2</td>
<td>The function was added.</td>
</tr>
</tbody> </table>

# Examples

For examples and further information please see:

<ul>
<li class="manual_boxlist"><a href="{{ "/headers-footers/headers-footers.html" | prepend: site.baseurl }}">Headers &amp; Footers</a></li>
<li class="manual_boxlist"><a href="{{ "/headers-footers/method-2.html" | prepend: site.baseurl }}">Headers &amp; Footers - Method 2</a></li>
</ul>

# See Also

<ul>
<li class="manual_boxlist"><a href="{{ "/reference/mpdf-functions/sethtmlfooter.html" | prepend: site.baseurl }}">SetHTMLHeader()</a></li>
</ul>

