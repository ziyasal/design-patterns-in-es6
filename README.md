# Design Patterns and Idioms in ES6
A collection of design patterns and idioms in ES6

**Boilerplate forked from  [angular/atscript-playground](https://github.com/angular/atscript-playground)**

### Initial setup

```bash
# Clone the repo...
git clone https://github.com/ziyasal/design-patterns-in-es6.git
cd design-patterns-in-es6

# Then, you need to install all the dependencies...
npm install

# If you want to be able to use global commands `karma` and `gulp`...
npm install -g karma-cli gulp
```

```bash
# Do initial build, start a webserver and re-build on every file change...
gulp build serve watch
```
Open a browser and see the result.

Current Patterns
======================

| Pattern | Description |
|:-------:| ----------- |
| [abstract_factory](src/abstract_factory/abstractFactory.ats) | use a generic function with specific factories |
| [adapter](src/adapter/adapter.ats) | adapt one interface to another using a whitelist |
| 3-tier | data<->business logic<->presentation separation (strict relationships) |
| borg | a singleton with shared-state among instances |
| [bridge](src/bridge/bridge.ats) | a client-provider middleman to soften interface changes |
| [builder](src/builder/builder.ats) | call many little discrete methods rather than having a huge number of constructor parameters |
| catalog | general methods will call different specialized methods based on construction parameter |
| chain | apply a chain of successive handlers to try and process the data |
| [command](src/command/command.ats) | bundle a command and arguments to call later |
| [composite](src/composite/composite.ats) | encapsulate and provide access to a number of different objects |
| [decorator](src/decorator/decorator.ats) | wrap functionality with other functionality in order to affect outputs |
| [facade](src/facade/facade.ats) | use one class as an API to a number of others |
| [factory_method](src/factory_method/factorymethod.ats) | delegate a specialized function/method to create instances |
| flyweight | transparently reuse existing instances of objects with similar/identical state |
| graph_search | (graphing algorithms, not design patterns) |
| mediator | an object that knows how to connect other objects and act as a proxy |
| [memento](src/memento/memento.ats) | generate an opaque token that can be used to go back to a previous state |
| [mvc](src/mvc/mvc.ats) | model<->view<->controller (non-strict relationships) |
| [observer](src/observer/observer.ats) | provide a callback for notification of events/changes to data |
| pool | preinstantiate and maintain a group of instances of the same type |
| [prototype](src/prototype/prototype.ats) | use a factory and clones of a prototype for new instances (if instantiation is expensive) |
| [proxy](src/proxy/proxy.ats) | an object funnels operations to something else |
| [publish_subscribe](src/publish_subscribe/pubsub.ats) | a source syndicates events/data to 0+ registered listeners |
| state | logic is org'd into a discrete number of potential states and the next state that can be transitioned to |
| [strategy](src/strategy/strategy.ats) | selectable operations over the same data |
| [template](src/template/template.ats) | an object imposes a structure but takes pluggable components |
| [visitor](src/visitor/visitor.ats)| invoke a callback for all items of a collection |
| chaining_method | continue callback next object method |
| [iterator](src/iterator/iterator.ats) | Provide a way to access the elements of an aggregate object sequentially |


### What are all the pieces involved?

#### [Traceur]
Transpiles AtScript code into regular ES5 (today's JavaScript) so that it can be run in a current browser.

#### [RequireJS]
Traceur is configured to transpile AtScript modules into AMD syntax and we use RequireJS to load the code in the browser.

#### [Assert] library
When `typeAssertions: true` option is used, Traceur generates run-time type assertions such as `assert.type(x, Object)`. The assert library does the actual run-time check. Of course, you can use your own assert library.

The idea with type assertions is that you only use them during the development/testing and when deploying, you use `typeAssertions: false`.

#### [Karma]
Test runner that runs the tests in specified browsers, every time that you change a file.

#### [Gulp]
Task runner to make defining and running the tasks simpler.


[AtScript]: http://atscript.org
[Traceur]: https://github.com/google/traceur-compiler
[RequireJS]: http://requirejs.org
[Assert]: https://github.com/angular/assert
[Karma]: http://karma-runner.github.io/
[Gulp]: http://gulpjs.com
