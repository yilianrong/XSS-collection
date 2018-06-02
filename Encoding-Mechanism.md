# Encoding types - Decoding rules

Using some encoding tricks to bypass restrictions.

## Encoding

### HTML Entity Encoding

- Format: Starting with "&", ending with ";". e.g. "&" -> "&amp;amp;", "<" -> "&amp;lt;", ">" -> "&amp;gt;". 

> Ending without ";" is OK. e.g. "&" -> "&amp;amp", "<" -> "&amp;lt", ">" -> "&amp;gt".

### HTML Attribute Encoding

- Format: "&#(DDD)(xHH);". e.g. "(" -> "&amp;#40;" or "(" -> "&amp;#x28;", ")" -> "&amp;#41;" or ")" -> "&amp;#x29;" 

> Decimal HTML character references without trailing semicolons, padding up to 7 numeric characters total. e.g. "(" -> "&amp;#0000040", ")" -> "&amp;#0000041".

> Hexadecimal HTML character references withou trailing semicolons. e.g. "(" -> "&amp;#x28", ")" -> "&amp;#x29".

### URL Encoding

- Format: "%HH". e.g. "<" -> "%3C", ">" -> "%3E", "(" -> "%28", ")" -> "%29".

> URL encoding should only be used to encode parameter values, not the entire URL or path fragment of a URL.

### Javascript Encoding

- Format: "\OOO", padding up to 3 numeric characters total. e.g. "a" -> "\141".
- Format: "\xHH", padding up to 2 numeric characters total. e.g. "a" -> "\x61".
- Format: "\u00HH", padding up to 4 numeric characters total. e.g. "a" -> "\u0061".

## Decoding

### Steps for a browser decoding HTML

- The browser receives HTML content sent from the server and parses it from start.
- When encounter &lt;script&gt;&lt;/script&gt;, a javascript script parser is invoked to parse the javascript, then execute the script, and continue parsing the rest HTML content.
- For some events that need to be triggered to execute, the script parser only parse the script when the event is triggered. Before the event is triggered, it is a part of HTML.

```
<li onclick="openURL(show.php?username='%value%');">username</li>
```

First, user input "value" is a part of URL. Second, the URL is a part of Javascript executed when the event is triggred. Third, the Javascipt is a part of HTML. So, **decoding** steps are following: **HTML decoding -> Javascript decoding -> URL decoding**. Above all, **encoding** steps are following: **URL encoding -> Javascript encoding -> HTML encoding**.
