---
description: SIKE
---

# $

you need to know something about jquery? in 2019? No you don't!

```javascript
const $ = (id) => {
    const el = document.getElementById(id);
    return el ? el : document.querySelectorAll(id);
}
```
