# PITHOS UI

---

## OLD PITHOS

* Code is not maintained
* Last feature 2013 (?)
* Mixed html + java
* Much effort to change something
* Old html (table design)

---

## NEW PITHOS 

> Pithos is a javascript web application taking advantage 
> of Pithos API inside a Django project

---

## NEW PITHOS

* Ember.js main js framework
* Ember data
* Foundation zurb for style
* Django (ask kpap why!)

---

## TECHNOLOGIES

* javascript, es6
* node js
* python
* sass

---

## FRAMEWORKS

* Ember
* qunit
* Django
* Foundation
* Ember data

---

## LIBRARIES

* handlebars
* underscore
* icon library: font awesome

---


## TOOLS

* compass
* npm
* bower
* ember cli
* Ember chrome inspector
* broccoli
* watchman
* js compiler: babel

---
<!-- .slide: data-background-class="ember" -->
## EMBER.JS

> A framework for creating ambitious web applications.


---
<!-- .slide: data-background-class="ember" -->

## EMBER.JS 

#### Core concepts

- Templates <!-- .element: class="fragment" data-fragment-index="1" -->
- Components <!-- .element: class="fragment" data-fragment-index="2" -->
- Controllers <!-- .element: class="fragment" data-fragment-index="3" -->
- Models <!-- .element: class="fragment" data-fragment-index="4" -->
- Routes <!-- .element: class="fragment" data-fragment-index="5" -->
- The router <!-- .element: class="fragment" data-fragment-index="6" -->

---
<!-- .slide: data-background-class="ember" -->

## EMBER.JS 

#### Templates

```handlebars
<div>
    <label>Name:</label>
    {{input type="text" value=name placeholder="Enter your name"}}
</div>
<div class="text">
    <h3>My name is {{name}} and I want to learn Ember!</h3>
</div>
```

---
<!-- .slide: data-background-class="ember" -->

## EMBER.JS 

#### Components

```javascript
App.GravatarImageComponent = Ember.Component.extend({
  size: 200,
  email: '',

  gravatarUrl: Ember.computed('email', 'size', function() {
    var email = this.get('email'),
        size = this.get('size');

    return 'http://www.gravatar.com/avatar/' + md5(email) + '?s=' + size;
  })
});
```

