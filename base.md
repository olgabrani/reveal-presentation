# PITHOS UI

---

## OLD PITHOS

* Last feature 2012
* Mixed html + java
* Code is not maintained
* Much effort to change something
* Old html markup (table design)

---

## NEW PITHOS 
(??)
> Pithos is a javascript web application taking advantage 
> of Pithos API inside a Django project

---

## NEW PITHOS

* Django (??)
* Ember.js
* Ember data
* Foundation

---

## TECHNOLOGIES

* JavaScript, ES6
* node.js
* Python
* sass

---

## FRAMEWORKS

* Ember.js
* Django
* Foundation Zurb
* Ember data
* Qunit

---

## LIBRARIES

* Handlebars
* Underscore
* Font Awesome

---


## TOOLS

* npm
* bower
* compass
* broccoli
* watchman
* Ember chrome inspector
* babel
* Ember cli

---
<!-- .slide: data-background-class="ember" -->
## EMBER.JS

> A Javascript MVC framework for creating ambitious web applications.


---
<!-- .slide: data-background-class="ember" -->

## EMBER.JS 

#### Core concepts

- Templates
- Component
- Controller
- Model
- Route
- The route

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

---

## Development needs

- compile
- watch
- install, manage and track packages/dependencies
- concat, minify
- precommit hooks
- check/ control coding style (jshint, k auto t sass)
- other tasks/script (destination/paste of output)
- asset pipeline (??)

---

## Difficulties

1. API not following conventions [http://jsonapi.org/format/](jsonapi format)
2. Objects vs human friendly folder structure
3. Error handling

---

## Difficulties

3. API not following conventions [http://jsonapi.org/format/](jsonapi format)


```javascript
// Ember way
var groups = this.store.find('groups');

// Pithos API way
ajaxSuccess: function(jqXHR, jsonPayload) {
        // get all headers as a string
        var headersStr = jqXHR.getAllResponseHeaders();
        var headers = headersStr.split('\n');

        // removes the colon and the uuids of the members of each group
        var re = (/X-Account-Group-\S*(?=:)/g);

        var groupHeader, groupName, groups=[];

        if(headersStr.indexOf('X-Account-Group-') > -1) {
            headers.forEach(function(h) {
                groupHeader = h.match(re);

                if(groupHeader) {
                    var group = {};

                    group.id = decodeURIComponent(groupHeader[0].replace('X-Account-Group-', '')).toLowerCase();
                    group.name = group.id;
                    var uuids = jqXHR.getResponseHeader(groupHeader[0]);

                    if(uuids === '~'){
                        return ;
                    }

                    if(uuids) {
                        group.users = uuids.split(',');
                    }
                    else {
                        group.users = [];
                    }

                    groups.push(group);
                }
            });

            jsonPayload.groups = groups;
        }

        return jsonPayload;
    },
```

---

## Ember-cli

> A tool for creating ember apps

```bash
# Installation
$ npm install -g ember-cli  

# Start a new project
$ ember new foo

# Run server
$ ember serve

# Generate new route
$ ember generate route bar
```


--- 

## Design

- Foundation zurb framework
- No designer 
- Concepts: UX principles, Simple intuitive design, error handling

---

## Pending issues

- Responsive Design (work on tablets and smartphones). (style+performance)
- Write tests
- Issues: https://github.com/olgabrani/synnefo/issues
- More user testing ( https://phab.dev.grnet.gr/T149 ) (open for review, your comments are valuable)

---

## FUTURE PLANS

- Handle files (video players, audio players).
- Various enhancements (github issues tagged with #enhancement).
- Node webkit (??)
- Global styleguide for GRNET projects

---

# Demo
