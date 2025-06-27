📘 1. Interface vs Type — What’s the Difference?

In TypeScript, we use both interface and type to define the structure of objects. While they are often similar, there are some key differences.

✅ Interface :
Used to define object structures.
Can be extended using extends.
Can be declared multiple times and will merge.

interface Person {
  name: string;
  age: number;
}

interface Person {
  gender: string;
}

// ✅ Now Person includes name, age, and gender


✅ Type : 
Can define primitive, union, and intersection types.
Cannot be merged.

type ID = number | string;
type Employee = {
  name: string;
  id: ID;
};

📌 When to Use What?
Use Case
Recommended
Need to merge declarations
interface
Using primitives/unions/etc.
type


🔑 2. What is keyof and Why Use It?
keyof is a TypeScript keyword that returns the keys of a type as a union of string literals.

🧚 Example:
interface User {
  id: number;
  name: string;
  email: string;
}
type UserKeys = keyof User;
// Result: "id" | "name" | "email"

Now we can create a type-safe accessor function:
function getValue<T, K extends keyof T>(obj: T, key: K): T[K] {
  return obj[key];
}
const user = { id: 1, name: "Alice", email: "a@example.com" };
const name = getValue(user, "name"); // ✅ Safe access


✅ Benefits of keyof:
Enables type-safe property access
Compile-time error for incorrect keys
Improves readability and IntelliSense support
