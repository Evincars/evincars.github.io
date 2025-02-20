+++
date = '2025-01-22T01:11:34+01:00'
draft = false
title = 'General Knowledge of Js and Angular'
categories = ['angular', 'css', 'js']
+++

A property assigned to a function like sayHi.counter = 0 does not define a local variable counter inside it. In other words, a property counter and a variable let counter are two unrelated things.
We can treat a function as an object, store properties in it, but that has no effect on its execution. Variables are not function properties and vice versa. These are just parallel worlds.

- takovy zaklad pro performance je co nejvic omezit change detekci a potom mit co nejmin nodes v domu

* **switchMap** - for any source item, completes the previous Observable and immediately creates the next one
* **mergeMap** - creates an Observable immediately for any source item, all previous Observables are kept alive. 
* **concatMap** - waits for the previous Observable to complete before creating the next one
* **exhaustMap** - source items are ignored while the previous Observable is not completed

1. we can apply many **attribute directives** to one host element. But can apply one structural directive to a host element.
2. A **structure directive** basically deals with manipulating the dom elements by typically adding or removing, or manipulating elements. But "attribute directives" are deal with changing the look and behavior of the DOM element

**display: block** means that the element is displayed as a block, as paragraphs and headers have always been. A block has some whitespace above and below it and tolerates no HTML elements next to it, except when ordered otherwise (by adding a float declaration to another element, for instance).

**display: inline** means that the element is displayed inline, inside the current block on the same line. Only when it's between two blocks does the element form an 'anonymous block', that however has the smallest possible width.

**display: contents** causes an element's children to appear as if they were direct children of the element's parent, ignoring the element itself. This can be useful when a wrapper element should be ignored when using CSS grid or similar layout techniques.


**linked signal** je jako computed + do nej muzes zapisovat

**JS Symbol** hlavni use-case je vytvorit unique Key pro propertu objektu. Kazdy Symbol je zaruka ze je unikatni. 

**ngAfterContentInit** : This is called after components external content has been initialized.
**ngAfterViewInit** : This is called after the component view and its child views has been initialized.

**Directives are applied at compile time**. So changing an element's properties/classes at runtime via the DOM API-s won't apply that directive dynamically.

---

- ``ElementRef`` is simply like ``document.getElementById('myId');``
- Using ``ElementRef`` you are only able to do some decorations
- ``TemplateRef`` is an embedded template which you can use in ``ViewContainerRef.createEmbeddedView`` to create Embedded View.
- ``*ngFor`` is doing the same, it reads the element as a ``TemplateRef`` and injects mutiple times to create view with data
- ``TemplateRef`` cannot be used as an element for css decorations in .ts
---
[https://redux.js.org/style-guide/#do-not-put-non-serializable-values-in-state-or-actions](https://redux.js.org/style-guide/#do-not-put-non-serializable-values-in-state-or-actions)

**Do Not Put Non-Serializable Values in State or Actions**
Avoid putting non-serializable values such as Promises, Symbols, Maps/Sets, functions, or class instances into the Redux store state or dispatched actions. This ensures that capabilities such as debugging via the Redux DevTools will work as expected. It also ensures that the UI will update as expected.
- if you would store your **state** in local-storage or into the URL and you'd refresh the page, you'd be fucked up
- use Array or Object instead only - ideally use ``withEntities``
---

**Design Patterns *(should know)***
----------------------------------------------
* Creational (Singleton, Builder, Factory)
* Structural (Facade, Adapter)
* Behavioral (Strategy, Observer)