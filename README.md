# etype

Extra types for TypeScript.

Most of the time we can be sure that the type of a variable is `int`. However, there is no `int` type in TypeScript, so we have to write code with comment like this:

```ts
/** age is int */
const age: number;
```

Is there a better way? Of course! We can define a type alias like this:

```ts
type int = number;

const age: int;
```

In this way, although we can not limit the type of value of age, it makes the code more readable.

Based on this idea, we provides some extra types for TypeScript.

## Usage

Install:

```bash
npm install etype --save-dev
```

Import in your ts files:

```ts
import type { int } from 'etype';

const age: int;
```

## Types

| Type          | Description                                                                                              | Example                                                    | Real Type                 |
| ------------- | -------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------- | ------------------------- |
| `int`         | 32-bit signed two's complement integer, which has a minimum value of -2^31 and a maximum value of 2^31-1 | `0`, `1`, `2`, `-1`, `-2147483648`, `2147483647`           | `number`                  |
| `float`       | Single-precision 32-bit IEEE 754 floating point                                                          | `0.1`, `-1.23`                                             | `number`                  |
| `IntString`   | Int-like-string                                                                                          | `"100"`, `"-1"`                                            | `string`                  |
| `FloatString` | Float-like-string                                                                                        | `"1.00"`, `"-0.1"`                                         | `string`                  |
| `DataString`  | Data-like-string which can be converted to Date object by `new Date(foo)`                                | `"Mon, 19 Oct 2020 13:09:21 GMT"`, `"2020-09-10 17:28:35"` | `string`                  |
| `JSONString`  | JSON-string which can be converted to json object by `JSON.parse(foo)`                                   | `"{\"hello\":\"world\"}"`                                  | `string`                  |
| `BooleanInt`  | Use int to represent a boolean                                                                           | `0`, `1`                                                   | `0 \| 1`                  |
| `AnyFunction` | Represent to any function                                                                                | /                                                          | `(...args: any[]) => any` |
