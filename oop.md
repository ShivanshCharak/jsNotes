## Javascript does not have classes
In JavaScript, the concept of classes was introduced in ECMAScript 2015 (also known as ES6). However, it's important to note that JavaScript's classes are syntactic sugar over its existing prototype-based inheritance system.

The class syntax provides a more convenient and readable way to define constructor functions and prototypes, making object-oriented programming patterns more accessible for developers who are familiar with class-based languages. Under the hood, JavaScript's classes still utilize prototypes.
## OOP
- Colections of properties and methods
- toLowercase,toUpperCase isa object in itself

## Parts of oop
- Object literal-: collection of functions and datatypes,
- constructor functions,
- prototypes,
- classes,
- Instances(new,this)

## 4 Pillars
Certainly! Below is an example of a Markdown file that explains the four pillars of Object-Oriented Programming (OOP).

```markdown
# Four Pillars of Object-Oriented Programming (OOP)

## 1. Encapsulation

Encapsulation is the bundling of data (attributes) and the methods that operate on the data into a single unit, known as a class. It involves restricting access to some of the object's components and only allowing external access through a well-defined interface.

### Example:

```javascript
class Circle {
  constructor(radius) {
    this.radius = radius;
  }

  getArea() {
    return Math.PI * this.radius * this.radius;
  }
}

const myCircle = new Circle(5);
console.log(myCircle.getArea()); // Accessing method through encapsulation
```

## 2. Abstraction

Abstraction involves simplifying complex systems by modeling classes based on the essential properties and behaviors they share. It hides the unnecessary details of an object and only shows the relevant features.

### Example:

```javascript
// Abstract class representing a Shape
class Shape {
  constructor() {
    if (new.target === Shape) {
      throw new Error('Abstract class cannot be instantiated.');
    }
  }

  getArea() {
    throw new Error('Method getArea() must be implemented by subclasses.');
  }
}

// Concrete class implementing Shape
class Circle extends Shape {
  constructor(radius) {
    super();
    this.radius = radius;
  }

  getArea() {
    return Math.PI * this.radius * this.radius;
  }
}
```

## 3. Inheritance

Inheritance allows a new class (subclass/derived class) to inherit properties and behaviors from an existing class (base class/parent class). It promotes code reusability and helps in creating a hierarchy of classes.

### Example:

```javascript
// Base class
class Animal {
  constructor(name) {
    this.name = name;
  }

  speak() {
    console.log(`${this.name} makes a sound.`);
  }
}

// Subclass inheriting from Animal
class Dog extends Animal {
  constructor(name, breed) {
    super(name);
    this.breed = breed;
  }

  bark() {
    console.log(`${this.name} barks loudly.`);
  }
}

const myDog = new Dog('Buddy', 'Labrador');
myDog.speak(); // Inherited method
myDog.bark();  // Subclass-specific method
```

## 4. Polymorphism

Polymorphism allows objects to be treated as instances of their parent class, even when they are instances of a subclass. It enables code to work with objects of multiple types through a common interface.

### Example:

```javascript
// Polymorphic function
function makeSound(animal) {
  animal.speak();
}

const cat = new Animal('Whiskers');
const dog = new Dog('Buddy', 'Golden Retriever');

makeSound(cat); // Uses the speak method of Animal
makeSound(dog); // Uses the speak method of Dog, inherited from Animal
```

These pillars collectively form the foundation of Object-Oriented Programming and help in designing and structuring code in a way that is modular, reusable, and easier to understand.
## this Keyword

In JavaScript, the `this` keyword is a special identifier that refers to the current execution context or the object to which the current code is associated. The value of `this` is dynamically determined based on how a function is invoked.

## Global Context

In the global context, outside any function, `this` refers to the global object. In browser environments, this is typically the `window` object, and in Node.js, it is the `global` object.

```javascript
console.log(this); // refers to the global object
```

## Function Context

In a regular function, the value of `this` depends on how the function is called. If the function is invoked as a method of an object, `this` refers to that object.

```javascript
const obj = {
  method: function() {
    console.log(this); // refers to the object 'obj'
  }
};

obj.method();
```

## Arrow Functions

Arrow functions differ from regular functions in how they handle `this`. They do not have their own `this` binding and instead inherit the `this` value from the surrounding lexical scope.

```javascript
const arrowFunction = () => {
  console.log(this); // inherits 'this' from the enclosing scope
};

arrowFunction();
```

## Event Handlers

In event handlers, such as those used with the DOM, `this` typically refers to the DOM element that triggered the event.

```javascript
document.getElementById('myButton').addEventListener('click', function() {
  console.log(this); // refers to the button element
});
```

## Constructor Functions

When a function is used as a constructor with the `new` keyword, `this` refers to the newly created object.

```javascript
function Person(name) {
  this.name = name;
}

const person = new Person('John');
console.log(person.name); // 'John'
```

Understanding the behavior of `this` in various contexts is crucial for writing maintainable and error-free JavaScript code.

For more details and examples, refer to the [MDN Web Docs on `this`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this).
```
const promiseOne = new Promise()
new is the constructor function whih you can use to create a new instance or context of the class
``` javascript
function User(usern

You can copy and paste this content into a file with a `.md` extension (e.g., `this_keyword_guide.md`). Markdown files are commonly used for documentation and can be rendered as formatted text on platforms that support Markdown, such as GitHub, GitLab, or various Markdown editors.
