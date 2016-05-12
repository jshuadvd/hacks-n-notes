# Data Structures

## Bitwise operations

Bitwise operators are 32-bit, 0101 is actually 00000000000000000000000000000101, but the preceding zeroes can be neglected since they contain no meaningful information.

A bitmask is a sequence of bits that can manipulate and/or read flags.

```js
var mask = FLAG_A | FLAG_B | FLAG_D; // 0001 | 0010 | 1000 => 1011
```