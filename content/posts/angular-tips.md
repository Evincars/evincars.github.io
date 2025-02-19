+++
date = '2025-01-29T23:21:08+01:00'
draft = false
title = 'Angular Tips'
categories = ['angular']
+++

**:host-context()** – Ever wanted your Angular components to automatically adapt based on where they’re used? a CSS pseudo-class that lets your component adjust its styles based on its parent. 
 * Theme-aware components 🎨 → Change styles dynamically inside dark mode or high-contrast wrappers 
 * Context-sensitive layouts 📱 → Adapt header, buttons, or text styles based on parent components 
 * Cleaner code, fewer manual class bindings 🚀 → No need for extra props or [class] hacks!

```
/* Default header styles */
:host {
    display: block;
    font-size: 24px;
    font-weight: bold;
    background-color: white;
    color: black;
}

/* Header inside a Modal */
:host-context(app-modal) {
    background-color: darkblue;
    color: white;
    text-align: center;
}

/* Header inside a Card */
:host-context(app-card) {
    background-color: lightgray;
    color: black;
    padding: 12px;
    border-bottom: 2px solid #ccc;
}
```

### Difference between ElementRef and TemplateRef
``ElementRef`` is simply like ``document.getElementById('myId');``
Using ``ElementRef`` you are only able to do some decorations
``TemplateRef`` is an embedded template which you can use in ``ViewContainerRef.createEmbeddedView`` to create Embedded View.
``*ngFor`` is doing the same, it reads the element as a ``TemplateRef`` and injects mutiple times to create view with data
``TemplateRef`` cannot be used as an element for css decorations in .ts