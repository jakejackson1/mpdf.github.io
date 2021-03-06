---
layout: page
title: ICCProfile
parent_title: mPDF Variables
permalink: /reference/mpdf-variables/iccprofile.html
modification_time: 2015-08-05T12:01:59+00:00
---

(mPDF >= 4.3)

ICCProfile – Specify ICC colour profile to use when creating PDF/A1-b or PDF/X-1a (mPDF >= 5.1) compliant documents

# Description

void **ICCProfile**

Specify ICC colour profile to use when creating PDF/A1-b or PDF/X-1a compliant documents. The file must exist in <span class="filename">/iccprofiles/</span> folder

Either a 3-colour RGB profile or a 4-colour CMYK profile should be used depending on other settings.

The default colorspace for a PDF/A1-b document is RGB. The default for a PDF/X-1a document is CMYK.

Specify the name without the <span class="filename">.icc</span> extension. sRGB_IEC61966-2-1 is used as the default file for PDF/A1-b documents if none is specified (a profile must be specified for PDF/X-1a)

# Values

<span class="parameter">$ICCProfile</span> =  <span class="smallblock">STRING</span>

Name of a valid ICC colour profile in the <span class="filename">/iccprofiles/</span> folder - without the <span class="filename">.icc</span> extension.

<span class="smallblock">DEFAULT</span>: <span class="smallblock">BLANK</span> <span class="smallblock"> </span>

# Changelog

<table class="table"> <thead>
<tr> <th>Version</th><th>Description</th> </tr>
</thead> <tbody>
<tr>
<td>4.3</td>
<td>Variable was added.</td>
</tr>
</tbody> </table>

# See Also

<ul>
<li class="manual_boxlist"><a href="{{ "/what-else-can-i-do/pdf-a1-b-compliance.html" | prepend: site.baseurl }}">PDF/A1-b compliance</a></li>
<li class="manual_boxlist"><a href="{{ "/what-else-can-i-do/pdf-x-1a-compliance.html" | prepend: site.baseurl }}">PDF/X-1a compliance</a></li>
<li class="manual_boxlist"><a href="{{ "/reference/mpdf-variables/pdfa.html" | prepend: site.baseurl }}">PDFA</a> - Create PDF/A1-b compliant document</li>
<li class="manual_boxlist"><a href="{{ "/reference/mpdf-variables/pdfx.html" | prepend: site.baseurl }}">PDFX</a> - Create PDF/X-1a compliant document</li>
<li class="manual_boxlist"><a href="{{ "/reference/mpdf-variables/pdfaauto.html" | prepend: site.baseurl }}">PDFAauto</a> - Specify whether to automatically fix issues to create PDF/A1-b compliant document</li>
<li class="manual_boxlist"><a href="{{ "/reference/mpdf-variables/pdfxauto.html" | prepend: site.baseurl }}">PDFXauto</a> - Specify whether to automatically fix issues to create PDF/X-1a compliant document</li>
<li class="manual_boxlist"><a href="{{ "/reference/mpdf-variables/restrictcolorspace.html" | prepend: site.baseurl }}">restrictColorSpace</a> - Specify whether to automatically limit the colorspaces used</li>
</ul>
