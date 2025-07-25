---
title: Bitwise XOR assignment (^=)
slug: Web/JavaScript/Reference/Operators/Bitwise_XOR_assignment
page-type: javascript-operator
browser-compat: javascript.operators.bitwise_xor_assignment
sidebar: jssidebar
---

The **bitwise XOR assignment (`^=`)** operator performs [bitwise XOR](/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_XOR) on the two operands and assigns the result to the left operand.

{{InteractiveExample("JavaScript Demo: Bitwise XOR assignment (^=) operator", "shorter")}}

```js interactive-example
let a = 5; // 00000000000000000000000000000101
a ^= 3; // 00000000000000000000000000000011

console.log(a); // 00000000000000000000000000000110
// Expected output: 6
```

## Syntax

```js-nolint
x ^= y
```

## Description

`x ^= y` is equivalent to `x = x ^ y`, except that the expression `x` is only evaluated once.

## Examples

### Using bitwise XOR assignment

```js
let a = 5; // (00000000000000000000000000000101)
a ^= 3; // (00000000000000000000000000000011)

console.log(a); // 6 (00000000000000000000000000000110)

let b = 5; // (00000000000000000000000000000101)
b ^= 0; // (00000000000000000000000000000000)

console.log(b); // 5 (00000000000000000000000000000101)

let c = 5n;
c ^= 3n;
console.log(c); // 6n
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- [Assignment operators in the JS guide](/en-US/docs/Web/JavaScript/Guide/Expressions_and_operators#assignment_operators)
- [Bitwise XOR (`^`)](/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_XOR)
