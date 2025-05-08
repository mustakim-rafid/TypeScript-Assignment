# *`Blog - 1`*

# 💡 Difference between `any`, `unknown`, and `never` types in TypeScript

> Learn `any`, `unknown` and `never` types like never before and understand why and when these types are used.
---
## 🧠 Introduction

The types `any`, `unknown`, and `never` are some of the most confusing concepts in TypeScript. These types may initially seem similar, but there are key differences between them. Once you understand these differences, you'll know exactly when to use each type effectively. Let's break them down one by one.

---

## 1️ `any` type

`any` is like - you can do whatever you want. It means "I don't know what the type is". Using `any` type is like entering JavaScript again. When you give a variable `any` type, it doesn't mind when you change the variable, from number to string or string to boolean, whatever you do. Behaves exactly like JS. 

##### 🔸 Example -

```js
let a: any = 23;
a = "hi"  // it doesn't mind
console.log(a.toString()) 
a = true  // it doesn't mind
```
---

## 2️ `unknown` type

`unknown` type is like - be careful what you do. It means "I don't know what the type is but don't use untill I cheak". Initially it acts like `any` type but when you try to call any method on that variable or function, you have to recheck the type. `unknown` says stop before using any method. After checking the type by condition, you can call the methods.
##### 🔸 Example -
```ts
let a: unknown = 23;
a = "hi" // you can do this but 
console.log(a.toString()) // ❌ can't do this. shows error. Instead
if(typeof a === "string") { 
    console.log(a.toString()) // ✅ correct way
}
```
---

## 3️ `never` type

`never` type is like - I will never return. It means "this will never return anything from a function". We set never return type when we know that this function will never return anything. When we set a function where it throws error or there is an infinite loop or somthing impossible happend in a function, we typically use `never`' return type. These are some of the use cases of `never`.
##### 🔸 Example - 
```ts
function ApiError(msg: string): never {
    throw new Error(msg);
}
```
---
## 📌 Key Differences:-

| Type       | Differences
|------------|------------------------------------
|`any`       | Anything goes like JS
|`unknown`   | Unknown type, must be checked first
|`never`     | Should never happen / never returns

---
## 🎯 Conclusion

I hope this blog will help you understand the core concepts of `any`, `unknown` and `never` types. I tried to make it as simple as possible. Now you know why and when to use these types. Now let's get back to code and built something amazing with TypeScript.

Thanks 🎉. 

---
---

# *`Blog - 2`*


# Examples of using Union `|` and Intersection `&` types in TypeScript

> A beginner-friendly guide to understand **union** and **intersection** types.

---

## 📖 Introduction

We already know about '**or**' `||` and '**and**' `&&` operator. Union and intersection type is almost similar accordingly. When we want to declare any one type from multiple type options given by us, we use **union** type and the symbol is `|`. Again when we want to add separately declared types into one, we use **intersection** type. It is similar like **extends** keyword when dealing with **interface**. The **intersection** symbol is `&`.

---

##### 🧠 Examples of using `Union` and `Intersection` types are given below - 

## 🔸 Union `|` type Example

```ts
type Developer = "Junior Developer" | "Senior Developer" // union type

const developer1: {
    name: string;
    salary: number;
    position: Developer;
    gender: "male" | "female"; // union type
    bloodGroup: "A+" | "O+" | "B+" | "OB+" | "A-" // union type
} = {
    name: "Harry",
    salary: 70000,
    position: "Senior Developer",
    gender: "male",
    bloodGroup: "B+"
}
```

---

## 🔸 Intersection `&` type Example

```ts
type FrontendDeveloper = {
    skills: string[];
    isReactExpert: boolean;
}

type BackendDeveloper = {
    skills: string[];
    isNodejsExpert: boolean;
    isDatabaseExpert: boolean;
    isPythonExpert: boolean;
}

type FullstackDeveloper = FrontendDeveloper & BackendDeveloper; // intersection type

const person1: FullstackDeveloper = {
    skills: ["Html", "Css", "React", "Python", "Sql"],
    isReactExpert: true,
    isNodejsExpert: false,
    isDatabaseExpert: true,
    isPythonExpert: true
}
```
---
## 🎯 Conclusion 

This is a beginner friendly blog of union `|` and interface `&` types with easy to understand examples. This blog explains when and how to use union and intersection types in TypeScript. I hope this small blog helps you understand the fundamental concepts of union and intersection types.

Thanks 🎉.