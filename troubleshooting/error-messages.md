---
layout: page
title: Error messages
parent_title: Troubleshooting
permalink: /troubleshooting/error-messages.html
---

<div id="bpmbook" class="bpmbook" style="direction:ltr;">
<div class="topic_user_field">
<div id="U0">
<p><b>"Output has already been sent from the script - PDF file generation aborted."</b></p>
<p>If you see this message it means that the script has sent output to the browser before starting to generate the PDF file.</p>
<p>Most likely causes are:</p>
<ul>
<li>a PHP error message - this should be displayed in your browser giving details of the problem</li>
<li>inadvertent whitespace in you PHP script files e.g. leaving space before or after the PHP tags &lt;?php&nbsp;&nbsp; ?&gt;</li>
<li>you are using object_buffering to generate content for your PDF file - see below</li>
</ul>
<p>If no error message appears, try setting:</p>

{% highlight php %}
<?php

$mpdf->debug = true;
{% endhighlight %}

<h3>Object buffering</h3>
<p>In order to catch error messages and prevent them being included in a PDF file (which will be corrupted), mPDF 2.5 introduced a method to detect whether there had been any output from the script prior to generating the PDF file in Output(). This includes checking for ob_get_contents() - a PHP function to check if there is any output in the object-buffer.</p>
<p>If you use object_buffering in the process of preparing the text for mPDF, this will falsely trigger the error message. If this is the case, add the following to your script to prevent it:</p>

{% highlight php %}
<?php

$mpdf->allow_output_buffering = true;
{% endhighlight %}

</div>
</div>
