---
description: writen mostly in javascript, other lang examples sometimes available
---

# utility functions

## uuidv4

```javascript
const uuidv4 = () => {
    return 'xxxxxxxx-xxxx-4xxx-yxxx-xxxxxxxxxxxx'.replace(/[xy]/g, (c) => {
        let r = Math.random() * 16 | 0; 
        let v = c == 'x' ? r : (r & 0x3 | 0x8);
        return v.toString(16);
    });
}
```

This isn't the best because it uses `Math.random()` which has its limitations, namely [not being cryptographically secure](../concepts/computer-science/prng/implementation-in-js-v8-engine.md).
