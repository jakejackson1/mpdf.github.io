---
layout: page
title: Blank screen
parent_title: Troubleshooting
permalink: /troubleshooting/blank-screen.html
modification_time: 2015-08-05T12:00:32+00:00
---

If you get nothing but a blank screen on your browser, it may be because there is a script error. Turn on debugging at the start of your script:

{% highlight php %}
<?php

// Require composer autoload
require_once __DIR__ . '/vendor/autoload.php';

$mpdf = new mPDF();

$mpdf->debug = true;

$mpdf->WriteHTML("Hallo World");

$mpdf->Output();

?>
{% endhighlight %}

See also <a href="{{ "/troubleshooting/known-issues.html" | prepend: site.baseurl }}">Known issues</a> and <a href="{{ "/troubleshooting/corrupt-pdf-file.html" | prepend: site.baseurl }}">Corrupt PDF file</a>.

<hr />

## localhost problems / Vista 64 bit

Since updating to Windows Vistax64bit for development, all files containing images or external stylesheets crashed or timeout.

See the useful thread at: <a href="http://www.wampserver.com/phorum/read.php?2,28291" target="_blank">http://www.wampserver.com/phorum/read.php?2,28291</a>

To generate images and retrieve external stylesheets, mPDF needs to access files using fopen() etc. Changing "localhost" to "127.0.0.1" resolved the problem.

<hr />

## Generating graphs with JPGraph

JPGraph outputs error messages as images generated by the script. If the error message is "out of memory" then you just get a blank screen. Try increasing your memory_limit.

