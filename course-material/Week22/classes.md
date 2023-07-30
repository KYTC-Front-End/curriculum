# ES6 Intro

This is a quick intro to get up-to-speed with the new class syntax introduced in ES6. We'll also cover ES modules as they're kind of unavoidable in frontend now.

## Classes

### Syntax

The ES6 class syntax is an easier way to create object-oriented structures in JavaScript. Previously you had to rely on prototypical inheritance with constructor functions.

(If you're curious about inheritance and prototypes you could check out [MDN's guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain), but it's not strictly necessary to continue)

Here's an example:

```js
function Animal(species) {
  this.species = species;
}

Animal.prototype.getSpecies = function() {
  return this.species;
};

const tiger = new Animal('tiger');
tiger.getSpecies(); // tiger
```

Any new instance of `Animal` has access to whatever we put on its prototype.

This is kind of verbose and awkward (having to refer to the prototype all the time), so classes provide a new syntax for achieving the same result:

```js
class Animal {
  constructor(species) {
    this.species = species;
  }
  getSpecies() {
    return this.species;
  }
}

const tiger = new Animal('tiger');
tiger.getSpecies(); // tiger
```

The outcome here is the same. `getSpecies` is still on `Animal`'s prototype, but we used a nicer syntax to get there.

### Constructor

The `constructor` method is the equivalent of the defining function in the first example. It takes whatever arguments you call the class with when you instantiate it with the `new` keyword.

### Inheritance

Classes make it easy to inherit functionality from other classes. We can use the `extends` keyword to access properties on the base class:

```js
class Dog extends Animal {
  constructor(name) {
    super('dog');
    this.name = name;
  }
  getName() {
    return this.name;
  }
}

const spot = new Dog('Spot');
spot.getSpecies(); // dog
spot.getName(); // Spot
```

`super` refers to the base class you're extending. So `super('dog')` is like calling `new Animal('dog')`, only from within our new class.

