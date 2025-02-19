---
title: symbol-description
rule_type: suggestion
further_reading:
- https://www.ecma-international.org/ecma-262/6.0/#sec-symbol-description
---


The `Symbol` function may have an optional description:

```js
const foo = Symbol("some description");

const someString = "some description";
const bar = Symbol(someString);
```

Using `description` promotes easier debugging: when a symbol is logged the description is used:

```js
const foo = Symbol("some description");

> console.log(foo);
// Symbol(some description)
```

It may facilitate identifying symbols when one is observed during debugging.

## Rule Details

This rules requires a description when creating symbols.

## Examples

Examples of **incorrect** code for this rule:

::: incorrect

```js
/*eslint symbol-description: "error"*/

const foo = Symbol();
```

:::

Examples of **correct** code for this rule:

::: correct

```js
/*eslint symbol-description: "error"*/

const foo = Symbol("some description");

const someString = "some description";
const bar = Symbol(someString);
```

:::

## When Not To Use It

This rule should not be used in ES3/5 environments.
In addition, this rule can be safely turned off if you don't want to enforce presence of `description` when creating Symbols.
