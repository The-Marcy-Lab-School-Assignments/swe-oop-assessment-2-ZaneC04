# Section 2 — Short Response

Write your responses directly in this file. Follow markdown formatting guidelines. Check the rubric.md file to see how your short responses will be graded. 

As a quick guide, check the following before submitting:
- [] Answered all parts of every question
- [] No typos or grammar mistakes (use grammarly!)
- [] Accurately uses relevant technical terminology
- [] Uses markdown to enhance readability (preview in VS Code with Command/Control + Shift + V)
- [] Responses are concise and easy to comprehend

---

## Question 1

In your own words, explain what does _encapsulation_ refer to? Why is this concept beneficial when programming? 

Provide a code snippet to illustrate _encapsulation_.

## Response 1
**Encapsulation** is an important foundation in object-oriented programming that refers to when **both data and functionality are stored together in an interface** or object, rather than separately in a program. This is beneficial as it allows our code to adhere to the concept of separation of concerns in OOP, and enables programmers to hide data that would otherwise be accessible and could be modified to make programs less predictable. Here is an example of this:

```js
const personMaker = (name, age) => {
    const person = {
        name,
        age,
        introduce() {
            return `My name is ${name} and I'm ${age} years old.`
        }
    }
    return person;
};
const Zane = personMaker("Zane", 19)
console.log(Zane.introduce()) // My name is Zane and I'm 19 years old.
```
As shown in this example, both the data of the `name` and `age` parameters are stored in an object along with the functionality of the method `introduce()`.

## Question 2

Explain what the `this` keyword is. Why is the `this` keyword useful?

In the code snippet below, what does `this` refer to?

```js
class Counter {
	constructor() {
		this.count = 0;
	}
  increment() {
    this.count++;
  }
}

const counterA = new Counter();
const counterB = new Counter();

counterA.increment();
counterA.increment();
counterA.increment();

counterB.increment();

console.log(counterA.count);
console.log(counterB.count);
```

## Response 2
The `this` keyword directly refers to the object that `this` is invoking the method on. Its value is determined by the function invoking it, as using `this` on a property inside of an object will refer to that object's property. This is useful because it allows methods and functions to access the properties and methods of the object `this` is referring to, which allows for code that can be reused. In the above example, `this` is referencing the property of `count` or `[Counter instance name].count`. Since `this` is pointing to the instance, the same functionality will be used for each instance of the `Counter` class, making the code for incrementing `count` reusable.  

## Question 3

In your own words, explain what **polymorphism** means in OOP. Provide an example in code that demonstrates polymorphism.

## Response 3
Polymorphism is a foundation in OOP that refers to the same method name having different implementation across classes or objects. This is beneficial as it allows programmers to reuse functionality that was previously declared, but modify it to fit better with separate parts in a program. An example of this is below:

```js
class Dog {
    constructor(name) {
        this.name = name
    }
    noise() {
        return `${this.name} the dog barks!`
    }
}

class Cat {
    constructor(name) {
        this.name = name
    }
    noise() {
        return `${this.name} the cat meows!`
    }
}
const Fido = new Dog('Fido')
const Tom = new Cat("Tom")
console.log(Fido.noise()) // Fido the dog barks!
console.log(Tom.noise()) // Tom the cat meows!
```
This example shows polymorphism as both `Dog` and `Cat` have the `noise()` method, but return a different output. 
## Question 4

You're building a game where players can raise different digital pets: Cats, Dogs, and Birds. All pets have have a `name`, `energy` level, and `happiness` level and can all `sleep`. Cats have the ability to `hunt`, dogs have the ability to `chase`, and birds have the ability to `fly`.

**Part A:** Describe in words how you would use inheritance to organize these classes.

**Part B:** Explain one advantage of using inheritance here instead of creating three completely separate classes.

## Response 4
I would use inheritance in this example by using the `extends` keyword to make Cats, Dogs and Birds all subclasses of a `Pet` superclass as shown below. 
 ```js
 class Pet {
    energy = 0
    happiness = 100
    constructor(name) {
        this.name = name
    }
    sleep() {
        energy = 100
        return `${this.name} sleeps and has energy restored to full!`
    }
}
 ```
 Using a superclass here is beneficial as it prevents the need to rewrite code. For example, since the `energy`, `happiness` and `name` properties are already declared, the subclasses would not need a `constructor(name)` or rewriting the `energy` and `happiness` properties.


