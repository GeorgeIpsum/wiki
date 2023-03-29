# implementation in JS V8 engine

base algorithm:

```javascript
const MAX_RAND = Math.pow(2, 32);
let state = [seed(), seed()];

const mswc1616 = () => {
    let r0 = (18030 * (state[0] & 0xFFFF)) + (state[0] >>> 16) | 0;
    let r1 = (36969 * (state[1] & 0xFFFF)) + (state[1] >>> 16) | 0;
    state = [r0, r1];

    let x = ((r0 << 16) + (r1 & 0xFFFF)) | 0;
    if (x < 0) {
        x = x + MAX_RAND;
    }
    return x / MAX_RAND;
}
```

A rng using George Marsaglia's MWC algorithm:

* MWC stands for multiply-with-carry, a class of PRNGs that Marsaglia invented.
* MWCs are similar to linear congruential generators (LCGs), but MWCs can produce sequences with longer cycle lengths with about the same number of CPU cycles

The MWC used in the V8 PRNG is _not_ actually an MWC generator, but is 2 MWC sub generators.

Using the _multiply-and-floor_ method with `Math.random` (i.e. `Math.floor(Math.random() * CONSTANT)`) can cause issues with generating zero collision identifiers, since depending on the length of the result of MAF, only the first x bits of the first MWC sub generator are used.
