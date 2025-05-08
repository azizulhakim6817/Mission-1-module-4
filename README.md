# Understanding Key TypeScript Concepts

## 1. What is the `keyof` keyword in TypeScript?

The `keyof` keyword is used to get the property names of a given type as a union of string literals. It allows developers to write safer and more flexible code by referencing property names directly from a type. This ensures better type checking and reduces errors from typos.

**Why it's useful:** It enables dynamic access to object properties while maintaining strong typing.

---

## 2. Union vs Intersection Types

- **Union types (`A | B`)** let a value be one of multiple types. It's helpful when a variable can be more than one type (e.g., `string | number`).
- **Intersection types (`A & B`)** combine multiple types into one, requiring the value to satisfy all included types.

**Why it's useful:** Unions provide flexibility, and intersections allow precise type compositions.

---


