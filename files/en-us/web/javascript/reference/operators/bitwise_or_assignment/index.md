---
title: Bitwise OR assignment (|=)
slug: Web/JavaScript/Reference/Operators/Bitwise_OR_assignment
page-type: javascript-operator
browser-compat: javascript.operators.bitwise_or_assignment
sidebar: jssidebar
---

The **bitwise OR assignment (`|=`)** operator performs [bitwise OR](/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_OR) on the two operands and assigns the result to the left operand.

{{InteractiveExample("JavaScript Demo: Bitwise OR assignment (|=) operator", "shorter")}}

```js interactive-example
let a = 5; // 00000000000000000000000000000101
a |= 3; // 00000000000000000000000000000011

console.log(a); // 00000000000000000000000000000111
// Expected output: 7
```

## Syntax

```js-nolint
x |= y
```

## Description

`x |= y` is equivalent to `x = x | y`, except that the expression `x` is only evaluated once.

## Examples

### Using bitwise OR assignment

```js
let a = 5;
a |= 2; // 7
// 5: 00000000000000000000000000000101
// 2: 00000000000000000000000000000010
// -----------------------------------
// 7: 00000000000000000000000000000111

let b = 5n;
b |= 2n; // 7n
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- [Assignment operators in the JS guide](/en-US/docs/Web/JavaScript/Guide/Expressions_and_operators#assignment_operators)
- [Bitwise OR (`|`)](/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_OR)
- [Logical OR assignment (`||=`)](/en-US/docs/Web/JavaScript/Reference/Operators/Logical_OR_assignment)
