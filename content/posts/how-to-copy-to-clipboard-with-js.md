+++
title = "How to copy to clipboard with JS"
date = 2017-07-24
tags = ["javascript"]
categories = ["programming", "front-end"]
+++

## The Requirement

Add click-to-copy to a web page.

## The Solution

There are libraries that do this and one [particularly popular clipboard library](https://clipboardjs.com/) that everyone uses, but I discovered today that it's one of those javascript things that might be worth just doing rather than pulling in a library.

Yeah, this way has limitations, but if all you really need is plain click-to-copy functionality, you can do it with a few lines of javascript:

```javascript
export function copyToClipboard(val) {
  const tempInput = document.createElement('input');
  tempInput.value = val;
  document.body.appendChild(tempInput);
  tempInput.select();
  document.execCommand('copy');
  document.body.removeChild(tempInput);
}
```

There are limitations to this simple snippet so if click-to-copy is a key part of your app [look at clipboard.js](https://clipboardjs.com/), but if it's just a little nice-to-have extra thing or if you're already working with lots of libraries that make importing certain third-party packages difficult, this might be all you need.

Fewer libraries = less code = less maintenance, amiright?
