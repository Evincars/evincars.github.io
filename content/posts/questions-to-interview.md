+++
date = '2025-01-22T01:06:08+01:00'
draft = false
title = 'Questions to Interview'
+++

General questions:
* **What is the most popular JS engine?** *(Google's V8)*
* **How JS gets executed? | Why JS doesn't use compiler?** *()*
* **Is JS single-threaded or multi-threaded language? Why?** *(Single-threaded; because of historical reasons - it was only a scripting language for browser. Aim was simplicity.)*
* **How is it possible that multiple requests doesn't block the main loop?** *(because of EventLoop)*
* **Is JS object oriented? How is inheritance handled?** *(heavily object-oriented; prototype inheritance - one object has ref to another obj (its prototype), and so on until last obj has null ref)*
* **What is the Event Loop? How does it works?** *()*
* **What is serialization/deserialisation in JS?** *(converting a data structure, such as object or array, into a format that can be easily stored; JSON.stringify)*
* **What is the 'hoisting' in JS?** *(a = 0; var a; i kdyz je deklarace na konci tak interpret to hodi na zacatek a je to OK)*
* **What is the 'memoizing' in JS?** *(used to increase the efficiency of function by storing the previous values that function has already been calculated)*
* **For what is 'Symbol' used?** *(mostly for creation unique keys for objects)*
* What returns this code: ``1 && 2`` (2), ``0 && 2`` (0), ``1 || 2`` (1), ``0 || 2`` (2)
* +[code] micro/macro tasks

What is the difference between these two codes?
```
async loadCourseV1(): Promise<Course[]> {
  const response = await fetch('/courses');
  return response.json();
}
async loadCoursesV2(): Promise<Course[]> {
  const response = await fetch('/courses2');
  return await response.json();
}
```
**Answer**: between error handling, 'return await' if will have try...catch will be catched immedietaly.

What will be the output of this code:
```
console.log(1);

setTimeout(() => console.log(2));

Promise.resolve().then(() => console.log(3));

Promise.resolve().then(() => setTimeout(() => console.log(4)));

Promise.resolve().then(() => console.log(5));

setTimeout(() => console.log(6));

console.log(7);
```
**Answer:** First micro-tasks -> 1 7 3 5 2 6 4

---
## Adam's interview questions:
* General:
    1. I have a long heavy calculations code but I cannot block main thread, but I need that code. What can I use (**answer:** Web Workers. It'll run the code in another, paralell thread - to use multiple CPU cores simultaneously. WW don't have access to DOM.)
* Angular related:
    1. My app is slow/laggy. What will you do to improve the performance? (**answer:**, changeDetections, reduce the amount of DOM nodes ideally) 
    2. If I want to pass the data from parent component to child and vise-versa, how can I achieve this? (**answer:** input(), output())
    2. What is a Dependency Injection and how does it work? (**answer:** I'm using an abstraction in my class and I don't care how does it work. Somebody needs to provide me the dependency. + deps are singletons which are handled Angular Provider)