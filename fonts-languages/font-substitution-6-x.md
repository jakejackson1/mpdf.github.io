---
layout: page
title: Font substitution 6.x
parent_title: Fonts & Languages
permalink: /fonts-languages/font-substitution-6-x.html
modification_time: 2015-08-05T11:59:38+00:00
---

If a font or default font is declared in HTML or CSS, the font that is actually set is determined by:

## Standard use

If called in HTML/CSS the font-family name is converted to an mPDF font-family name (see <a href="{{ "/fonts-languages/font-names.html" | prepend: site.baseurl }}">Font names</a>) e.g.

{% highlight php %}

{% endhighlight %}

<p>The font requested (including style) is checked to see if it is available to mPDF: set by the array `$``available_unifonts`* :

<ol>
<li>If the font[style] exists - selected e.g. `trebuchetms['B']`</li>
<li>If the font[nostyle] exists - selected e.g. `trebuchetms['R']`</li>
<li>Looks up the font-family in the three arrays `sans_fonts, serif_fonts,` and `mono_fonts` defined in <span class="filename">mpdf_config.php</span> , in this case looking for '`trebuchetms`'. If found, substitutes a font of similar type (sans-serif, serif, or mono) - the first font in the `sans_fonts, serif_fonts,` or `mono_fonts` arrays is used.</li>
<li>If no font has yet been selected, the first font in the array `$``available_unifonts`* is selected</li>
</ol>

* The array  `$available_unifonts` is initially derived from `$this->fontdata` in the <span class="filename">config_fonts.php</span> file. (`trebuchetms['B']` will be converted to '`trebuchetmsB')`

## Core fonts

If core fonts only are specified by using `$mpdf = new mPDF('c')`, then all font requests will be substituted by Arial/Helvetica, Times or Courier i.e. the core PDF fonts. mPDF determines whether the requested font is a sans-serif, serif or monospace font (as above), and substitutes accordingly. 

## Character (font) substitution

If some circumstances, individual characters are replaced by glyphs from another font - see <a href="{{ "/fonts-languages/character-substitution.html" | prepend: site.baseurl }}">character (font) substitution</a>.

