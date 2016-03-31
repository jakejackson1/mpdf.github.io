---
layout: page
title: tocpagebreak
parent_title: HTML control tags
permalink: /reference/html-control-tags/tocpagebreak.html
---

<div id="bpmbook" class="bpmbook" style="direction:ltr;">
<div class="topic_user_field">
<div id="U0">
<p>(mPDF &gt;= 2.0)</p>
<p>tocpagebreak — Insert a table of contents</p>
<h2>Description</h2>

<div class="alert alert-info" role="alert">&lt;<b>tocpagebreak</b> [ <span class="parameter">paging</span> ] [ <span class="parameter">links</span> ] [ <span class="parameter">toc-orientation</span> ] [ <span class="parameter">toc-margin-left</span> ] [ <span class="parameter">toc-margin-right</span> ] [ <span class="parameter">toc-margin-top</span> ] [ <span class="parameter">toc-margin-bottom</span> ] [ <span class="parameter">toc-margin-header</span> ] [ <span class="parameter">toc-margin-footer</span> ] [ <span class="parameter">toc-odd-header-name</span> ] [ <span class="parameter">toc-even-header-name</span> ] [ <span class="parameter">toc-odd-footer-name</span> ] [ <span class="parameter">toc-even-footer-name</span> ] [ <span class="parameter">toc-odd-header-value</span> ] [ <span class="parameter">toc-even-header-value</span> ] [ <span class="parameter">toc-odd-footer-value</span> ] [ <span class="parameter">toc-even-footer-value</span> ] [ <span class="parameter">toc-preHTML</span> ] [ <span class="parameter">toc-postHTML</span> ] [ <span class="parameter">toc-bookmarkText</span> ] [ <span class="parameter">name</span> ] [ <span class="parameter">toc-page-selector</span> ] [ <span class="parameter">toc-sheet-size</span> ] [ <span class="parameter">toc-resetpagenum</span> ] [ <span class="parameter">toc-pagenumstyle</span> ] [ <span class="parameter">toc-suppress</span> ]

[&nbsp;<span class="parameter">orientation</span> ] [&nbsp;<span class="parameter">resetpagenum</span> ] [&nbsp;<span class="parameter">pagenumstyle</span> ] [&nbsp;<span class="parameter">suppress</span> ] 

[ <span class="parameter">margin-left</span> ] [ <span class="parameter">margin-right</span> ] [ <span class="parameter">margin-top</span> ] [ <span class="parameter">margin-bottom</span> ] [ <span class="parameter">margin-header</span> ] [ <span class="parameter">margin-footer</span> ]

[ <span class="parameter">odd-header-name</span> ] [ <span class="parameter">odd-header-value</span> ] [ <span class="parameter">even-header-name</span> ] [ <span class="parameter">even-header-value</span> ] [ <span class="parameter">odd-footer-name</span> ] [ <span class="parameter">odd-footer-value</span> ] [ <span class="parameter">even-footer-name</span> ] [ <span class="parameter">even-footer-value</span> ] [ <span class="parameter">page-selector</span> ] [ <span class="parameter">sheet-size</span> ] [ <span class="parameter">outdent</span> ] /&gt;</div>
<p>Add a new page to the document, marking the point at which a Table of Contents (<acronym title="Table of Contents">ToC</acronym>) will be inserted in the document at the end of writing. The numerous parameters specify both paging details for the continuing document, and for the <acronym title="Table of Contents">ToC</acronym> when it is generated.</p>

<div class="alert alert-info" role="alert"><b>Note:</b> From mPDF 5.7 the layout of a table of contents can be controlled using CSS. <span class="parameter">font</span> <span class="parameter">font-size</span> and <span class="parameter">indent</span> have become redundant.</div>

<div class="alert alert-info" role="alert"><b>Note:</b> When writing a <span class="smallblock">DOUBLE-SIDED</span> document, the <acronym title="Table of Contents">ToC</acronym> will always start on an <span class="smallblock">ODD</span> page. Therefore there is no option to specifiy the pagebreak <span class="parameter">type </span>as in &lt;<a href="/reference/html-control-tags/pagebreak.html">pagebreak</a>&gt; - using <b>&lt;tocpagebreak&gt;</b> will always continue the document on an <span class="smallblock">ODD</span> page.</div>

<div class="alert alert-info" role="alert"><b>Note:</b> Page numbering was suppressed in the <acronym title="Table of Contents">ToC</acronym> prior to mPDF v 6.0. From v6.0 onwards, you can specify the page numbering throughout the <acronym title="Table of Contents">ToC</acronym> .</div>

<div class="alert alert-info" role="alert"><b>Note:</b> The <acronym title="Table of Contents">ToC</acronym> is generated at the end of the document. Unless otherwise specified, the <acronym title="Table of Contents">ToC</acronym> will inherit the page margins, headers/footers and orientation of the last page written to the document.</div>

<div class="alert alert-info" role="alert"><b>Note:</b> From mPDF 2.3 you can include more than one <acronym title="Table of Contents">ToC</acronym> in the document using the attribute <span class="parameter">name</span>.</div>

<div class="alert alert-info" role="alert"><b>Note:</b> If <b>&lt;tocpagebreak&gt;</b> occurs at the start of a blank (<span class="smallblock">ODD</span>) page, no new page(s) will be added. This was added in mPDF 2.3 to allow a <acronym title="Table of Contents">ToC</acronym> to be placed on the first page, or to allow a <acronym title="Table of Contents">ToC</acronym> to follow another <acronym title="Table of Contents">ToC</acronym>. In this case, any properties for the continuing document are ignored. If you define several <acronym title="Table of Contents">ToC</acronym>s following immediately on from one another, set the properties in the first <acronym title="Table of Contents">ToC</acronym> you define (including the <span class="parameter">resetpagenum</span>).</div>
<h2>Attributes</h2>

<div class="alert alert-info" role="alert">The first set of attributes specify characteristics for the <acronym title="Table of Contents">ToC</acronym>, which is generated automatically at the end of the document when <a href="/reference/mpdf-functions/output.html">Output()</a> is called.</div>
<p><span class="parameter">paging</span> = 1|on|0|off</p>
<p class="manual_param_dd">Specify whether to show page numbers in the <acronym title="Table of Contents">ToC</acronym>.

<span class="smallblock">BLANK</span>&nbsp;or omitted uses a default value of <span class="smallblock">TRUE</span>.

<span class="smallblock">DEFAULT</span>: ON</p>
<p class="manual_param_dd"><b>Values</b> (case-insensitive)

ON <i>or</i> 1: show page numbers in the <acronym title="Table of Contents">ToC</acronym>.

OFF <i>or</i> 0: do not show page numbers in the <acronym title="Table of Contents">ToC</acronym>.</p>
<p class="manual_param_dt"><span class="parameter">links </span> = 1|on|0|off</p>
<p class="manual_param_dd">Specify whether to generate hyperlinks in the <acronym title="Table of Contents">ToC</acronym>.

<span class="smallblock">BLANK</span>&nbsp;or omitted uses a default value of <span class="smallblock">FALSE</span>.

<span class="smallblock">DEFAULT</span>: OFF</p>
<p class="manual_param_dd"><b>Values</b> (case-insensitive)

ON <i>or</i> 1: show hyperlinks in the <acronym title="Table of Contents">ToC</acronym>.

OFF <i>or</i> 0: do not show hyperlinks in the <acronym title="Table of Contents">ToC</acronym>.</p>
<p class="manual_param_dt"><span class="parameter">toc-orientation </span></p>
<p class="manual_param_dd">This attribute specifies the orientation of the <acronym title="Table of Contents">ToC</acronym> pages.

<span class="smallblock">BLANK</span> or omitted leaves the orientation unchanged i.e. at the end of the document (before the <acronym title="Table of Contents">ToC</acronym> is generated)</p>
<p class="manual_param_dd"><b>Values</b> (case-insensitive)

L <i>or</i> landscape: Landscape

P <i>or</i> portrait:&nbsp;Portrait</p>
<p class="manual_param_dt"><span class="parameter">toc-margin-left

toc-margin-right

</span><span class="parameter">toc-margin-top

toc-margin-bottom

</span><span class="parameter">toc-margin-header

toc-margin-footer</span></p>
<p class="manual_param_dd">Set the page margins for the <acronym title="Table of Contents">ToC</acronym>. 

Values can be specified using any valid CSS <span class="smallblock">LENGTH</span> e.g. px, pt, em, mm.

If you are writing a <span class="smallblock">DOUBLE-SIDED</span> document, the margin values will be used for <span class="smallblock">ODD</span> pages; left and right margins will be mirrored for <span class="smallblock">EVEN</span> pages.

<span class="smallblock">BLANK</span>&nbsp;or omitted leaves the current margin unchanged i.e. the margins current at the end of the document.

"0" (zero) will set the margin to zero.</p>
<p class="manual_param_dt"><span class="parameter">toc-odd-header-name

toc-even-header-name</span><span class="parameter">

toc-odd-footer-name

</span><span class="parameter">toc-even-footer-name</span></p>
<p class="manual_param_dd">Selects a header or footer by name to use for the <acronym title="Table of Contents">ToC</acronym>. The header/footer must already have been defined using <a href="/reference/mpdf-functions/defheaderbyname.html">defHeaderByName()</a>, <a href="/reference/mpdf-functions/deffooterbyname.html">defFooterByName()</a>, <a href="/reference/mpdf-functions/defhtmlheaderbyname.html">defHTMLHeaderByName()</a>, or <a href="/reference/mpdf-functions/defhtmlfooterbyname.html">defHTMLFooterByName()</a>.

If you are writing a <span class="smallblock">SINGLE-SIDED</span> document, the values for <span class="smallblock">ODD</span> will be used for all pages, and values for <span class="smallblock">EVEN</span> will be ignored.

<span class="smallblock">BLANK</span>&nbsp;or omitted leaves the header/footer unchanged. NB <span class="smallblock">BLANK</span> will not unset the header. Set <span class="parameter">toc-</span><span class="parameter">odd-header-value</span> to -1 to turn the header off.</p>

<div class="alert alert-info" role="alert"><b>Note:</b> You must add the prefix 'html_' before the name if it is a HTMLHeader.</div>
<p class="manual_param_dt"><span class="parameter">toc-odd-header-value</span><span class="parameter">

toc-even-header-value

toc-odd-footer-value</span><span class="parameter">

toc-even-footer-value</span></p>
<p class="manual_param_dd">Specify whether to show a header or footer in the <acronym title="Table of Contents">ToC</acronym>. The header/footer must already have been defined using <a href="/reference/mpdf-functions/defheaderbyname.html">defHeaderByName()</a>, <a href="/reference/mpdf-functions/deffooterbyname.html">defFooterByName()</a>, <a href="/reference/mpdf-functions/defhtmlheaderbyname.html">defHTMLHeaderByName()</a>, or <a href="/reference/mpdf-functions/defhtmlfooterbyname.html">defHTMLFooterByName()</a>.

If you are writing a <span class="smallblock">SINGLE-SIDED</span> document, the values for <span class="smallblock">ODD</span> will be used for all pages, and values for <span class="smallblock">EVEN</span> will be ignored.

<span class="smallblock">BLANK</span>&nbsp;or omitted or 0 leaves the header/footer state unchanged.</p>
<p class="manual_param_dd"><b>Values</b> (case-insensitive)

1 <i>or</i> on: Show the selected header/footer in the <acronym title="Table of Contents">ToC</acronym>. 

-1 <i>or</i> off: Hide the selected header/footer in the <acronym title="Table of Contents">ToC</acronym>.</p>
<p class="manual_param_dt"><span class="parameter">toc-preHTML</span></p>
<p class="manual_param_dd">Specify the HTML code to appear before the <acronym title="Table of Contents">ToC</acronym>.

The HTML code cannot contain any of the characters: &lt; &gt; &amp; ' <i>or</i> " and must use the appropriate HTML entities e.g. &lt;tocpagebreak toc-prehtml="&amp;lt;h1&amp;gt;Contents&amp;lt;/h1&amp;gt;"&gt;

It is recommended that you use htmlspecialchars('Your html code', ENT_QUOTES) for this.

<span class="smallblock">BLANK</span>&nbsp;or omitted will enter no text</p>
<p class="manual_param_dt"><span class="parameter">toc-postHTML</span></p>
<p class="manual_param_dd">Specify the HTML code to appear after the <acronym title="Table of Contents">ToC</acronym>.

The HTML code cannot contain any of the characters: &lt; &gt; &amp; ' <i>or</i> " and must use the appropriate HTML entities e.g. &lt;tocpagebreak toc-posthtml="&amp;lt;p&amp;gt;Comments after the Contents table&amp;lt;/p&amp;gt;"&gt;

It is recommended that you use htmlspecialchars('Your html code', ENT_QUOTES) for this.

<span class="smallblock">BLANK</span>&nbsp;or omitted will enter no text.</p>
<p class="manual_param_dt"><span class="parameter">toc-bookmarkText </span></p>
<p class="manual_param_dd">Specify the text as it will appear as a <span class="smallblock">BOOKMARK</span> for the <acronym title="Table of Contents">ToC</acronym>&nbsp; e.g. 'Content list'.

The text cannot contain any of the characters: &lt; &gt; &amp; ' <i>or</i> " and must use the appropriate HTML entities e.g. &lt;tocpagebreak toc-bookmarkText="Contents table &amp;gt;&amp;gt;"&gt;

It is recommended that you use htmlspecialchars('Your bookmark text', ENT_QUOTES) for this.

<span class="smallblock">BLANK</span>&nbsp;or omitted will not create a <span class="smallblock">BOOKMARK</span>.</p>
<p class="manual_param_dt"><span class="parameter">name</span></p>
<p class="manual_param_dd">Specify which <acronym title="Table of Contents">ToC</acronym> to include at this point, if using more than one <acronym title="Table of Contents">ToC</acronym> in the document. <span class="parameter">name</span> can be any alphanumeric characters (except just "0") and is case-insensitive.

<span class="smallblock">BLANK</span>&nbsp;or omitted or 0 uses the default <acronym title="Table of Contents">ToC</acronym>.</p>
<p><span class="parameter">toc-page-selector</span></p>
<p class="manual_param_dd">Select a named CSS @page for the <acronym title="Table of Contents">ToC</acronym>.

<span class="smallblock">BLANK</span>&nbsp;or omitted or leaves the CSS page unchanged.</p>
<p class="manual_param_dd">See <a href="/paging/using-page.html">Using @page</a> for more information</p>
<p>&nbsp;</p>
<p class="manual_param_dt"><span class="parameter">toc-sheet-size</span></p>
<p class="manual_param_dd"><span class="parameter">toc-sheet-size</span> can be specified either as a pre-defined page size, or as two <span class="smallblock">LENGTH</span> values separated by a space, representing width and height e.g. '210mm 297mm'. em, ex and % are not accepted. Note that this is different from the 'size' property of the page-box used with the CSS @page selector.

<span class="smallblock">DEFAULT</span>: <span class="smallblock">BLANK</span> - makes no change to the current sheet-size</p>
<p class="manual_param_dd"><b>Values</b> (case-insensitive)

A0 - A10, B0 - B10, C0 - C10

4A0, 2A0, RA0 - RA4, SRA0 - SRA4

Letter, Legal, Executive, Folio

Demy, Royal

A (Type A paperback 111x178mm)

B (Type B paperback 128x198mm)

&lt;<span class="smallblock">LENGTH</span>&gt;{2}</p>
<p class="manual_param_dd">All of the pre-defined values can be suffixed with "-L" to force a Landscape page orientation document e.g. "A4-L"</p>
<p class="manual_param_dt"><span class="parameter">toc-resetpagenum</span> = 1 - ∞</p>
<p class="manual_param_dd">Sets/resets the document page number to <span class="parameter">resetpagenum</span> starting on the <acronym title="Table of Contents">ToC</acronym>. (The value must be a positive integer).

<span class="smallblock">BLANK</span>&nbsp;or omitted or 0 leaves the preceding page number sequence&nbsp;unchanged.</p>
<p class="manual_param_dt"><span class="parameter">toc-pagenumstyle</span> = 1|A|a|I|i|[+ any value supported for list-style-type]</p>
<p class="manual_param_dd">Sets/resets the page numbering style to use in the <acronym title="Table of Contents">ToC</acronym> (values as for cf. <a href="/css-stylesheets/supported-css.html">lists</a>)

<span class="smallblock">BLANK</span>&nbsp;or omitted leaves the current&nbsp;page number&nbsp;style&nbsp;unchanged.</p>
<p class="manual_param_dd"><b>Values</b> (case-sensitive)

1: Decimal - 1,2,3,4...

A: Alpha uppercase - A,B,C,D...

a: Alpha lowercase - a,b,c,d...

I: Roman uppercase - I, II, III, IV...

i: Roman lowercase - i, ii, iii, iv...</p>
<p class="manual_param_dt"><span class="parameter">toc-suppress</span> = on|off|1|0</p>
<p class="manual_param_dd"><span class="parameter">suppress</span>=on will suppress document page numbers in the <acronym title="Table of Contents">ToC</acronym> 

<span class="smallblock">BLANK</span>&nbsp;or omitted leaves the current&nbsp;condition unchanged.</p>
<p class="manual_param_dd"><b>Values</b> (case-insensitive)

1 <i>or</i> on: Suppress (hide) page numbers in the <acronym title="Table of Contents">ToC</acronym>

0 <i>or</i> off: Show page numbers in the <acronym title="Table of Contents">ToC</acronym></p>

<div class="alert alert-info" role="alert">The rest of the attributes are defined exactly as for &lt;<a href="/reference/html-control-tags/pagebreak.html">pagebreak</a>&gt;. Note that these attributes define page numbering, margins, headers/footers for the document as it continues from this point on; in the final document this will be the part of the document immediately after the <acronym title="Table of Contents">ToC</acronym>.

Please refer to &lt;<a href="/reference/html-control-tags/pagebreak.html">pagebreak</a>&gt; for further details.</div>
<h2>Changelog</h2>
<table class="bpmTopic"> <thead>
<tr> <th>Version</th><th>Description</th> </tr>
</thead> <tbody>
<tr>
<td>2.0</td>
<td>Tag was added.</td>
</tr>
<tr>
<td>2.2</td>
<td>Default values for <span class="parameter">font-size</span>, <span class="parameter">paging</span> and <span class="parameter">links</span> were redefined.</td>
</tr>
<tr>
<td>2.3</td>
<td><span class="parameter">name</span> attribute was added.</td>
</tr>
<tr>
<td>3.0</td>
<td><span class="parameter">toc-bookmarkText</span> changed to decode htmlspecialchars</td>
</tr>
<tr>
<td>4.3</td>
<td>
<p>Parameters <span class="parameter">page-selector</span>, <span class="parameter">sheet-size</span>,</p>
<p><span class="parameter">toc-page-selector</span> and <span class="parameter">toc-sheet-size</span> were added</p>
</td>
</tr>
<tr>
<td>5.7</td>
<td>
<p><span class="parameter">outdent</span> parameter added</p>
<p><span class="parameter">font</span>, <span class="parameter">font-size</span> and <span class="parameter">indent</span> redundant</p>
</td>
</tr>
<tr>
<td>6.0</td>
<td>Parameters added:&nbsp; <span class="parameter">toc-resetpagenum</span> | <span class="parameter">toc-pagenumstyle</span> | <span class="parameter">toc-suppress</span> 

</td>
</tr>
</tbody> </table>
<h2>Examples</h2>

{% highlight php %}
Example #1
{% endhighlight %}

{% highlight php %}
<html>

<p>Text of introduction...</p>

<tocpagebreak />

<p><tocentry content="Chapter 1" />Text of main book...</p>

</html>
{% endhighlight %}

<h2>See Also</h2>
<ul>
<li class="manual_boxlist"><a href="/reference/mpdf-functions/addpage.html">&lt;tocentry</a>&gt;- Add an entry for Table of Contents</li>
<li class="manual_boxlist">&lt;<a href="/reference/html-control-tags/pagebreak.html">pagebreak</a>&gt; - Add a new page</li>
<li class="manual_boxlist"><a href="/reference/mpdf-functions/tocpagebreak.html">TOCpagebreak()</a> - PHP equivalent of &lt;<b>tocpagebreak</b>&gt;</li>
</ul>
</div>
</div>
