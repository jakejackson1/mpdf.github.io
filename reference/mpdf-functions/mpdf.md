---
layout: page
title: mPDF()
parent_title: mPDF functions
permalink: /reference/mpdf-functions/mpdf.html
modification_time: 2015-08-05T12:00:37+00:00
---

(mPDF >= 5.0)

mPDF – Initialise an instance of mPDF class

# Description

class **mPDF** ([ string <span class="parameter">$mode</span> [, mixed <span class="parameter">$format</span> [, float <span class="parameter">$default_font_size</span> [, string <span class="parameter">$default_font</span> [, float <span class="parameter">$margin_left</span> , float <span class="parameter">$margin_right</span> , float <span class="parameter">$margin_top</span> , float <span class="parameter">$margin_bottom</span> , float <span class="parameter">$margin_header</span> , float <span class="parameter">$margin_footer</span> [, string <span class="parameter">$orientation</span> ]]]]]])

Initialise an instance of mPDF class.

# Parameters

<span class="parameter">$mode</span>

This parameter specifies the mode of the new document.

<span class="smallblock">DEFAULT</span>: <span class="smallblock">BLANK</span>

**Codepage Values** (case-insensitive)

<span class="smallblock">BLANK</span>

"c"

"...-x"

"...-s" or "s"

"...+aCJK" or "+aCJK"

"...-aCJK" or "-aCJK"

where ... can be any string. Only language/country codes will have any effect, but other strings are parsed for backwards compatability (but have no effect).

Only some combinations make sense. See <a href="{{ "/fonts-languages/choosing-a-configuration-v5-x.html" | prepend: site.baseurl }}">Choosing a configuration</a> for more details.

**Country/Language code values** (case-insensitive)

Country/language codes are defined in <span class="filename">config_cp.php</span>

A country/language code can be passed as e.g. "en-GB" or "en_GB" or "en"***

***

<div class="alert alert-info" role="alert">**Note:** If the <span class="parameter">$mode</span> is set by passing a country/language string, this may also set: available fonts, text justification, and directionality <acronym title="Right-to-Left document, used for Hebrew and Arabic languages">RTL</acronym> (as determined by <span class="filename">config_cp.php</span>)</div>

<div class="alert alert-info" role="alert">**Note:** There is a useful list of language/country codes at: <a href="http://www.i18nguy.com/unicode/language-identifiers.html">http://www.i18nguy.com/unicode/language-identifiers.html</a></div>
<ul> </li>
</ul>

<span class="parameter">$format</span>

<ul> </li>
</ul>

<span class="parameter">$format</span> can be specified either as a pre-defined page size, or as an array of width and height in millimetres (see Example #2 below).

<span class="smallblock">DEFAULT</span>: "A4"

**Values** (case-insensitive)

A0 - A10, B0 - B10, C0 - C10

4A0, 2A0, RA0 - RA4, SRA0 - SRA4

Letter, Legal, Executive, Folio

Demy, Royal

A (Type A paperback 111x178mm)

B (Type B paperback 128x198mm)

Ledger, Tabloid*

All of the above values can be suffixed with "-L" to force a Landscape page orientation document e.g. "A4-L".

If <span class="parameter">$format</span> is defined as a string, the final <span class="parameter">$orientation</span> parameter will be ignored.

*Ledger and Tabloid are standard formats with the same page size but different orientation (Ledger is landscape, and Tabloid is portrait). mPDF treats these identically; if you wish to use Ledger, you should specify "Ledger-L" for landscape.

<span class="parameter">$default_font_size</span>

Sets the default document font size in ***points*** (pt)

<span class="smallblock">BLANK</span> or omitted or 0 uses the default value set in <span class="parameter">$defaultCSS</span>.

<span class="parameter">$default_font</span>

<ul> </li>
</ul>

Sets the default font-family for the new document.

<span class="smallblock">BLANK</span> or omitted uses default value set in <span class="parameter">$defaultCSS</span> unless <span class="parameter">$codepage</span> has been set to "win-1252". If <span class="parameter">$codepage</span>="win-1252", the appropriate core Adobe font will be set i.e. Helvetica, Times, or Courier.

<span class="parameter">$margin_left</span>

<span class="parameter">$margin_right</span>

<span class="parameter">$margin_top</span>

<span class="parameter">$margin_bottom</span>

<span class="parameter">$margin_header</span>

<span class="parameter">$margin_footer</span>

Sets the page margins for the new document.

All values should be specified as <span class="smallblock">LENGTH</span> in millimetres.

If you are creating a <span class="smallblock">DOUBLE-SIDED</span> document, the margin values specified will be used for <span class="smallblock">ODD</span> pages; left and right margins will be mirrored for <span class="smallblock">EVEN</span> pages.

<span class="smallblock">BLANK</span> or omitted uses the default values.

<span class="smallblock">DEFAULT</span> **Values**

<span class="parameter">$margin_left</span> 15

<span class="parameter">$margin_right</span> 15

<span class="parameter">$margin_top</span> 16

<span class="parameter">$margin_bottom</span> 16

<span class="parameter">$margin_header</span> 9

<span class="parameter">$margin_footer</span> 9

<span class="parameter">$orientation</span>

<ul> </li>
</ul>

This attribute specifies the default page orientation of the new document if <span class="parameter">$format</span> is defined as an array. This value will be ignored if <span class="parameter">$format</span> is a string value.

<span class="smallblock">DEFAULT</span>: "P"

**Values** (case-insensitive)

*P:* <span class="smallblock">DEFAULT</span> Portrait

L: Landscape

# Changelog

<table class="table"> <thead>
<tr> <th>Version</th><th>Description</th> </tr>
</thead> <tbody>
<tr>
<td>2.0</td>
<td>The <span class="parameter">$orientation</span> parameter was added.</td>
</tr>
<tr>
<td>5.0</td>
<td>The <span class="parameter">$mode</span> parameter renamed (from <span class="parameter">$codepage</span>), and recognised values changed</td>
</tr>
</tbody> </table>

# Examples

Example #1

{% highlight php %}
<?php

// Require composer autoload
require_once __DIR__ . '/vendor/autoload.php';

$mpdf = new mPDF();

$mpdf->WriteHTML('
Hallo World
');

$mpdf->Output('filename.pdf');

exit;

?>
{% endhighlight %}

Example #2

{% highlight php %}
<?php

// Define a new mPDF document using utf-8 fonts

$mpdf = new mPDF('utf-8');

// Define a new mPDF document using win-1252 fonts based on a language/country code

$mpdf = new mPDF('en-GB');

// Define a Landscape page size/format by name

$mpdf = new mPDF('utf-8', 'A4-L');

// Define a page size/format by array - page will be 190mm wide x 236mm height

$mpdf = new mPDF('utf-8', array(190,236));

// Define a page using all default values except "L" for Landscape orientation

$mpdf = new mPDF('','', 0, '', 15, 15, 16, 16, 9, 9, 'L');
{% endhighlight %}

# Notes

<div class="alert alert-info" role="alert">**Note:** <span class="smallblock">_MPDF_PATH</span> was required to be defined explicitly prior to mPDF 4.0 e.g. define('_MPDF_PATH','../'). From mPDF 4.0 the value should be automatically defined by the script itself when including the mpdf.php file.</div>

# See Also

<ul>
<li class="manual_boxlist"><a href="{{ "/reference/mpdf-functions/writehtml.html" | prepend: site.baseurl }}">WriteHTML()</a> - Write HTML to the document</li>
<li class="manual_boxlist"><a href="{{ "/reference/mpdf-functions/output.html" | prepend: site.baseurl }}">Output()</a> - Finalise and output the document</li>
</ul>
