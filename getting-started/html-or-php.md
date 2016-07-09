---
layout: page
title: HTML or PHP?
parent_title: Getting Started
permalink: /getting-started/html-or-php.html
modification_time: 2015-08-05T11:59:25+00:00
---

Most of the functions of mPDF can be achieved two ways: using PHP commands, or using custom HTML tags. Use whichever suits your purpose better, and you can always combine a mxture of the two.

If you are new to mPDF, I would recommend using HTML/CSS for everything - you can test most things out in a browser this way as you are writing it.

Example:

Example #1

{% highlight php %}
<?php

$mpdf = new \Mpdf\Mpdf();

$mpdf->Bookmark('Start of the document');

$mpdf->WriteHTML('<div>Section 1 text</div>');

$mpdf->Output();

?>
{% endhighlight %}

Example #2

{% highlight php %}
<?php

$html = '<bookmark content="Start of the Document" /><div>Section 1 text</div>';

$mpdf = new \Mpdf\Mpdf();

$mpdf->WriteHTML($html);

$mpdf->Output();

?>
{% endhighlight %}

# Invalid HTML?

If you want to hide mPDF custom tags from a browser, enclose any mPDF code within:

{% highlight php %}
<!--mpdf  ..  anything you want to write ...  mpdf-->
{% endhighlight %}

mPDF will strip away the <span class="parameter">$&lt;!--mpdf</span> tag and any following spaces, and the <span class="parameter">$mpdf--&gt;</span> tag and any preceeding spaces, and process all enclosed code e.g.

{% highlight php %}
<!--mpdf  <htmlheader id="header1"><h2>Section 2</h2></htmlheader>  mpdf-->
{% endhighlight %}

# See Also

<a href="{{ "/what-else-can-i-do/capture-html-output.html" | prepend: site.baseurl }}">Capturing HTML</a>

