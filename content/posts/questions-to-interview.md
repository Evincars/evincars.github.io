+++
date = '2025-01-22T01:06:08+01:00'
draft = false
title = 'Questions to Interview'
categories = ['interview', 'js', 'angular']
+++

General questions:
* **[don't use] What is the most popular JS engine?** *(Google's V8)*
* **[don't use] How JS gets executed? | Why JS doesn't use compiler?** *()*
* **[don't use] Is JS single-threaded or multi-threaded language? Why?** *(Single-threaded; because of historical reasons - it was only a scripting language for browser. Aim was simplicity.)*
* **How is it possible that multiple requests doesn't block the main thread?** *(because of EventLoop)*
* **Is JS object oriented? How is inheritance handled?** *(heavily object-oriented; prototype inheritance - one object has ref to another obj (its prototype), and so on until last obj has null ref)*
* **What is the Event Loop? How does it works?** *()*
* **[don't use - not JS related] What is serialization/deserialisation in JS?** *(converting a data structure, such as object or array, into a format that can be easily stored; JSON.stringify)*
* **What is the 'hoisting' in JS?** *(a = 0; var a; i kdyz je deklarace na konci tak interpret to hodi na zacatek a je to OK)*
* **[theory topic] What is the 'memoizing' in JS?** *(For same f-ction input, you'll get same output. The inputs are cached. Used to increase the efficiency of function by storing the previous values that function has already been calculated). *
* **For what is 'Symbol' used?** *(mostly for creation unique keys for objects)*
* What returns this code: ``1 && 2`` (2), ``0 && 2`` (0), ``1 || 2`` (1), ``0 || 2`` (2)
* +[code] micro/macro tasks

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


**[Use with caution]** What is the difference between these two codes?
```
async loadCourseV1(): Promise<Course[]> {
  const response = await fetch('/courses');
  return response.json();
}
async loadCoursesV2(): Course[] {
  const response = await fetch('/courses2');
  return await response.json();
}
```
**Answer**: between error handling, 'return await' if will have try...catch will be catched immedietaly.

---
## Adam's interview questions:
* General:
    1. I have a long heavy calculations code but I cannot block main thread, but I need that code. What can I use (**answer:** Web Workers. It'll run the code in another, paralell thread - to use multiple CPU cores simultaneously. WW don't have access to DOM.)
* Angular related:
    1. My app is slow/laggy. What will you do to improve the performance? (**answer:**, changeDetections, reduce the amount of DOM nodes ideally) 
    2. If I want to pass the data from parent component to child and vise-versa, how can I achieve this? (**answer:** input(), output(), service, store, ...)
    2. What is a Dependency Injection and how does it work? (**answer:** I'm using an abstraction in my class and I don't care how does it work. Somebody needs to provide me the dependency. + deps are singletons which are handled Angular Provider)

---
## My custom questions:
* you need to share data between two browser tabs with the same app. How yould you do that? (localStorage)
* have you used dome UI library? (angular material)
* My app is slow/laggy. What will you do to improve the performance? (changeDetections, reduce the amount 
of DOM nodes ideally)
* You have memory leaks, what could be problem? (e.g. unsubscriptions) how would you effectivelly unsubscribe subscription?
* Dependency Injection, what's that? (LogService. I am using info, error, but provider takes care of what instance he'll deliver)
* How can you make dependency optional? (@Optional)
* // laggy component, which has in interpollation method calling, translations
* what is the tree-shaking? (unused modules will not be included in the bundle during the build process.)
* signals - computed, effect, linkedSignal
* what are the advantages of using signals? (control change detection, reactivity)
* are you using some state mgmt? -> Do you know raising star SignalStore?
* what's the difference between Promise and Observable? (promise - it'll be resolved once, obs - stream)
* can you name me your favourite RxJS operators?
* how would you set common coding rules for all devs? - e.g. all private props starts with '_'. Code is inconsitent, you want to effectivally check that (ESLInt rules, you can prevent circular deps because of rules in relations between libs)