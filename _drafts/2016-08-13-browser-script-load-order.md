---
date: 2016-08-13 08:52:35 +0100
title: "Browser script loading priority"
draft: true
layout: post
---

JS loading in a browser can be weird/unpredictable/annoying. To that end, I have
created this, both as reference and partly in hope that by doing it, I'll
remember it once and for all!

The primary tricky one is as follows:

```js
<script>log('1. Sync inline script');</script>
<script>
(function(){
    var s = document.createElement('script');
    s.src = '/js/log-example.js';
	document.head.appendChild(s);
}());
</script>
<script>log('3. Sync inline script');</script>
```

If you inspect the source of this page, you'll see a hidden `iframe` with the
above in its `head`. `log` is a function exposed to the `iframe` which outputs
into the "Psuedo JS console" below. You'll see that the script call order is:

 1. Synchronous inline script
 2. "Synchronous" remote script
 3. Synchronous inline script

The interesting part as the actual load order, which can be seen in the
"console" below.

<script src="/js/window.log.js"></script>
<iframe id="iframe-container" src="/html/iframe-example.html"></iframe>
<div id="iframe-console"><pre>:: Pseudo JS console ::</pre></div>



<style>
	iframe#iframe-container { display: none; }
</style>
<!-- <style> -->
<!-- #iframe-container { -->
<!-- 	display: none; -->
<!-- } -->
<!-- #iframe-console { -->
<!-- 	border: 1px solid red; -->
<!-- 	width: 100%; -->
<!-- 	height: 100px; -->
<!-- } -->
<!-- </style> -->
