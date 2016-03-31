---
layout: page
title: preparePreText()
parent_title: mPDF Utilities
permalink: /reference/mpdf-utilities/preparepretext.html
---

<div id="bpmbook" class="bpmbook" style="direction:ltr;">
<div class="topic_user_field">
<div id="U0">
<p>(htmltoolkit &gt;= 2.4)</p>
<p>PreparePreText – Prepares text to be output ignoring the HTML markup</p>
<h2>Description</h2>

<div class="alert alert-info" role="alert">string <b>preparePreText</b> ( string <span class="parameter">$text</span> [, string <span class="parameter">$formfeed</span> ])</div>
<p>Prepares text to be output ignoring the HTML markup. This is useful to output a large text file (e.g. a PHP script file) using <a href="/reference/mpdf-functions/writehtml.html">WriteHTML()</a>. This will surround the text with &lt;pre&gt; tags whilst preventing &lt;pre&gt;tags included in the text from being parsed. It also allows use of a text string marker (<span class="parameter">formfeed</span>) to be replaced by a formfeed in the output file.</p>

<div class="alert alert-info" role="alert"><b>Note:</b> Prior to mPDF 5.1 you should use the <span class="parameter">$mode </span>parameter of <a href="/reference/mpdf-functions/writehtml.html">WriteHTML()</a> as '2' to avoid parsing the text for style tags. See example below.</div>
<h2>Parameters</h2>
<p class="manual_param_dt"><span class="parameter">text</span></p>
<p class="manual_param_dd">This parameter specifies the text string to prepare.</p>
<p class="manual_param_dt"><span class="parameter">formfeed</span></p>
<p class="manual_param_dd"><span class="parameter">formfeed</span> specifies the string to be replaced by a formfeed in the output file.

<span class="smallblock">DEFAULT</span>: "//FF//"</p>
<h2>Return value</h2>
<p>Returns a text string.</p>
<h2>Changelog</h2>
<table class="bpmTopic"> <thead>
<tr> <th>Version</th><th>Description</th> </tr>
</thead> <tbody>
<tr>
<td>2.4</td>
<td>Function was added.</td>
</tr>
</tbody> </table>
<h2>Examples</h2>

{% highlight php %}
Example #1
{% endhighlight %}

{% highlight php %}
<?php

<?php

include("../mpdf.php");

$text = file_get_contents('scriptfile.php');

$text = preparePreText($text);

// Default spaces/tab in mPDF is 8 as specified by HTML spec.

// Notepad and other text editors use a value of 6

$mpdf->tabSpaces = 6;

// If 'scriptfile.php' is iso-8859-1 or win-1252 encoded, use

$mpdf->allow_charset_conversion=true;

$mpdf->charset_in='windows-1252';

$mpdf->WriteHTML($text, 2);

$mpdf->Output();

exit;

?>
{% endhighlight %}

<h2>See Also</h2>
<ul>
<li><a href="/reference/mpdf-functions/setdoctemplate.html">WriteHTML()</a> - Write HTML code to a PDF file</li>
<li><a href="/reference/mpdf-variables/tabspaces.html">tabSpaces</a> - Specifies the number of spaces to substitue for a <span class="smallblock">TAB</span> character</li>
<li><a href="/reference/mpdf-variables/allow-charset-conversion.html">allow_charset_conversion</a> - Parse the character set of any input text from the HTML, or allow setting of the value <span class="parameter">charset_in</span> </li>
<li><a href="/reference/mpdf-variables/charset-in.html">charset_in</a> - Define the character encoding of any input HTML</li>
</ul>
</div>
</div>
