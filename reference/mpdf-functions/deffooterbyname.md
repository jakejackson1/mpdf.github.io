---
layout: page
title: DefFooterByName()
parent_title: mPDF functions
permalink: /reference/mpdf-functions/deffooterbyname.html
modification_time: 2015-08-05T12:00:45+00:00
---

(mPDF >= 2.0)

DefFooterByName – Define a page footer with a given name

# Description

void **DefFooterByName** ([ string <span class="parameter">$name</span> [, array <span class="parameter">$footer</span> ]])

Define a page footer with a given name. Named footers can be referenced and set later in the document e.g. <a href="{{ "/reference/mpdf-functions/setheaderbyname.html" | prepend: site.baseurl }}">SetFooterByName()</a>

<div class="alert alert-info" role="alert">**Note:** Do not name any header or footer starting with html_   This prefix is reserved to identify an <span class="smallblock">HTML</span> header/footer when passing its name in a reference.</div>

<div class="alert alert-info" role="alert">**Note:** This function/method was altered in mPDF 2.2 by capitalising the first letter of the name. As function/method names in PHP have hitherto been case-insensitive, this should not cause any problems, but it is recommended where possible to use the preferred spelling.</div>

# Parameters

<span class="parameter">$name</span>

User-defined name for the footer. If <span class="parameter">$name</span> = <span class="smallblock">BLANK</span> the name '_default' is used.<span class="smallblock">

</span>

<span class="parameter">$footer</span>

This parameter specifies the content of the page footer as an array.

<span class="smallblock">DEFAULT</span>: array()abov

**Values** in the array

<span class="parameter">$content</span>: <span class="smallblock">TEXT STRING</span>

<span class="parameter">$font-size</span>: <span class="smallblock">FLOAT</span> font size in **pts**

<span class="parameter">$font-style</span>: B|I|BI|<span class="smallblock">BLANK STRING</span>

<span class="parameter">$font-family</span>: Any available font-family

<span class="parameter">$color</span>: CSS '#RRGGBB' string

<span class="parameter">$line</span>: 0|1 - specify whether to draw a line above the footer

{% highlight php %}
$footer = array (

    'L' => array (

      'content' => '',

      'font-size' => 10,

      'font-style' => 'B',

      'font-family' => 'serif',

      'color'=>'#000000'

    ),

    'C' => array (

      'content' => '',

      'font-size' => 10,

      'font-style' => 'B',

      'font-family' => 'serif',

      'color'=>'#000000'

    ),

    'R' => array (

      'content' => 'My document',

      'font-size' => 10,

      'font-style' => 'B',

      'font-family' => 'serif',

      'color'=>'#000000'

    ),

    'line' => 1,

);
{% endhighlight %}

# Changelog

<table class="table"> <thead>
<tr> <th>Version</th><th>Description</th> </tr>
</thead> <tbody>
<tr>
<td>2.0</td>
<td>The function was added.</td>
</tr>
</tbody> </table>

# Examples

For examples and further information please see:

<ul>
<li class="manual_boxlist"><a href="{{ "/headers-footers/headers-footers.html" | prepend: site.baseurl }}">Headers &amp; Footers</a></li>
<li class="manual_boxlist"><a href="{{ "/headers-footers/method-1.html" | prepend: site.baseurl }}">Headers &amp; Footers - Method 3</a></li>
</ul>

# See Also

<ul>
<li class="manual_boxlist"><a href="{{ "/reference/mpdf-functions/defheaderbyname.html" | prepend: site.baseurl }}">DefHeaderByName()</a></li>
<li class="manual_boxlist">&lt;<a href="{{ "/reference/html-control-tags/pagefooter.html" | prepend: site.baseurl }}">pagefooter</a>&gt;</li>
<li class="manual_boxlist"><a href="{{ "/reference/mpdf-functions/setfooterbyname.html" | prepend: site.baseurl }}">SetFooterByName()</a></li>
<li class="manual_boxlist">&lt;<a href="{{ "/reference/html-control-tags/setpagefooter.html" | prepend: site.baseurl }}">setpagefooter</a>&gt;</li>
</ul>

