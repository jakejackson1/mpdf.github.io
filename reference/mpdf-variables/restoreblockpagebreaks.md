---
layout: page
title: restoreBlockPagebreaks
parent_title: mPDF Variables
permalink: /reference/mpdf-variables/restoreblockpagebreaks.html
---

<div id="bpmbook" class="bpmbook" style="direction:ltr;">
<div class="topic_user_field">
<div id="U0">
<p>(mPDF &gt;= 2.3&nbsp; &lt;= 6.0)</p>
<h2>Description</h2>

<div class="alert alert-info" role="alert">boolean <b>restoreBlockPageBreaks</b></div>
<p>Specifies whether or not to restore open HTML block elements after a forced pagebreak. When a pagebreak is forced by <a href="/reference/mpdf-functions/addpage.html">AddPage()</a> or &lt;<a href="/reference/html-control-tags/pagebreak.html">pagebreak</a>&gt;, mPDF by default will close any HTML block elements, expecting the HTML code to start afresh after the pagebreak. If this value is set to <span class="smallblock">TRUE</span> mPDF will attempt to carry over any CSS style values for the current block elements and continue after the pagebreak.</p>

<div class="alert alert-info" role="alert"><b>Note:</b> This variable was removed in mPDF 6.0&nbsp; See <a href="/paging/page-breaks.html">Page Breaks</a> for more information</div>
<h2>Values</h2>
<p class="manual_param_dt"><span class="parameter">restoreBlockPageBreaks</span> = <span class="smallblock">TRUE</span>|<span class="smallblock"><i>FALSE</i></span></p>
<p class="manual_param_dd"><b>Values</b>

<span class="smallblock">TRUE</span>: Restore block element properties after a pagebreak

<span class="smallblock"><i>FALSE</i></span>: <span class="smallblock">DEFAULT</span> Do not restore block elements after a pagebreak

Values of 1 or 0 can also be used</p>
<h2>Changelog</h2>
<table class="bpmTopic"> <thead>
<tr> <th>Version</th> <th>Description</th> </tr>
</thead> <tbody>
<tr>
<td>2.3</td>
<td>The variable was added.</td>
</tr>
</tbody> </table>
<h2>Examples</h2>

{% highlight php %}
Example #1
{% endhighlight %}

{% highlight php %}
<?php

<?php

$mpdf=new mPDF();

$mpdf->restoreBlockPageBreaks = true;

$mpdf->WriteHTML('<div class="firstlevel"><div class="secondlevel"><p>Hallo World</p>');

$mpdf->AddPage();

$mpdf->WriteHTML('<p>Hallo World</p></div></div>');

?>
{% endhighlight %}

<h2>See Also</h2>
<ul>
<li class="manual_boxlist"><a href="/reference/mpdf-functions/setwatermarktext.html">WriteHTML()</a> - Write HTML code to the document</li>
<li class="manual_boxlist">&lt;<a href="/reference/html-control-tags/formfeed.html">formfeed</a>&gt; - Equivalent to pagebreak with <span class="parameter">restoreBlockPageBreaks</span> set to <span class="smallblock">TRUE</span> </li>
</ul>
</div>
</div>
