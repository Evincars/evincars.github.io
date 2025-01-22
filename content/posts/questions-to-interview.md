+++
date = '2025-01-22T01:06:08+01:00'
draft = false
title = 'Questions to Interview'
+++

General questions:
* What is the most popular JS engine?
* How JS gets executed? | Why JS doesn't use compiler?
* Is JS single-threaded or multi-threaded language? Why?
* How is it possible that multiple requests doesn't block the main loop?
* Is JS object oriented? How is inheritance handled?
* What is the Event Loop? How does it works?
* What is the 'hoisting' in JS
* What is the 'memoizing' in JS
* For what is 'Symbol' used *(mostly for creation unique keys for objects)*
* What returns this code: ``1 && 2``, ``0 && 2``
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

---
## Adam's interview questions:
* General:
    1. I have a computation task which hardly consumes performance, but I need it - maybe run on background?. What can I use (**answer:** Web Workers)
* Angular related:
    1. My app is slow/laggy. What will you do to improve the performance? (**answer:**, changeDetections, reduce the amount of DOM nodes ideally) 
    2. If I want to pass the data from parent component to child and vise-versa, how can I achieve this? (**answer:** input(), output())
    2. What is a Dependency Injection and how does it work? (**answer:** I'm using an abstraction in my class and I don't care how does it work. Somebody needs to provide me the dependency. + deps are singletons which are handled Angular Provider)