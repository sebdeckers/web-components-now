# Web Components Now!
*A guide to using Web Components in a modern web application.*

## What are Web Components?
Web Components is a group of experimental technologies.

### Custom Elements
Create your own tags as ES6 classes. Offers lifecycle management and a standard way to interop with other components, simply as HTML elements.

```html
<bike-gallery category="naked" brand="KTM">
  <h1>Duchess</h1>
</bike-gallery>
```

```js
class BikeGallery extends HTMLElement {
  createdCallback () {
    // do stuff
  }
}
document.registerElement('bike-gallery', BikeGallery)
```

**Opinion:** Useful when distributing components or re-using 3rd party components. Feels good combined with EventTarget (`addEventListener`/`removeEventListener`/`dispatchEvent`).

### HTML Imports
Native dependency management. Still topic of debate among browser vendors.

**Opinion:** Not really necessary when using ES6 modules (`import`/`export`), as custom elements can only be registered through the JavaScript API `document.registerElement`.

### HTML Templates
Inert HTML content that can be used to embed content without actually rendering it.

**Opinion:** Lacks useful features like data binding or logic (e.g. iteration, conditionals). Haven't found this useful so far.

### Shadow DOM
Encapsulation of HTML, JavaScript, and CSS. Like an IFRAME within HTML elements.

**Opinion:** Simplifies CSS selectors; no more need for BEM/SMACSS/etc. :relieved: Allows nesting of custom elements.

## A Reasonable Stack
I'd like to use a DSL like Jade for HTML templating, and PostCSS for CSS. Swapping these out for alternative templating engines or processors should not be too difficult.
