## Project 6

[Home](https://liv-edi.github.io/cit281/)

In this project we created three classes including a Shape class, Rectangle class, and Trinagle class. The Shape class was the bas class for the the Trinagle and Rectangle class which both inherited from the Shape class. The Shape class returned a perimeter value that the other two classes used to return an area value.

Technologies used for this project:
- VSCode
- Node.js

The purpose of this project was to gain experince creating/ working with classes with inheritance, with classes in general, debugging code, using generic code blocks to process data, writing/ executing server side Node.js code, working with static data, and using JS.

From doing this project I learned more about classes and the concept of inheritance. I also learned how to debug my code to make it simpler and also more effective.

```
class Shape {
    constructor(sides = []) {
        this.sides = sides;
    }
    perimeter = () => {let sum = 0;
        (this.sides.length >= 1) ? this.sides.reduce(function (previousValue, currentValue) {
                sum = previousValue + currentValue
                return previousValue + currentValue;
                }):sum = 0; return sum;};
    }
console.log(new Shape([5, 10]).perimeter());  // 15
console.log(new Shape([1, 2, 3, 4, 5]).perimeter()); // 15
console.log(new Shape().perimeter()); // 0
class Rectangle extends Shape {
    constructor(length = 0, width = 0) {
        super([length, width, length, width]);
        this.length = length;
        this.width = width;
    }
    area() {
        return (this.length * this.width);
    }
}
console.log(new Rectangle(4, 4).perimeter());  // 16
console.log(new Rectangle(4, 4).area());  // 16
console.log(new Rectangle(5, 5).perimeter()); // 20
console.log(new Rectangle(5, 5).area()); // 25
console.log(new Rectangle().perimeter()); // 0
console.log(new Rectangle().area()); // 0
class Triangle extends Shape {
    constructor(sideA = 0, sideB = 0, sideC = 0) {
        super([sideA, sideB, sideC]);
        this.sideA = sideA;
        this.sideB = sideB;
        this.sideC = sideC;
    }
    area() {
        const s = (this.sideA + this.sideB + this.sideC)/2;
        return Math.sqrt(s*(s-this.sideA)*(s-this.sideB)*(s-this.sideC));
    }
}
console.log(new Triangle(3, 4, 5).perimeter());  // 12
console.log(new Triangle(3, 4, 5).area());  // 6
console.log(new Triangle().perimeter()); // 0
console.log(new Triangle().area()); // 0
const data = [ [3, 4], [5, 5], [3, 4, 5], [10], [] ];
for (const array of data) {
    let output = "";
    array.length == 0 ? output = ("Shape with 0 sides unsupported") :
    array.length == 1 ? output = ("Shape with 1 side unsupported") :
    array.length == 2 ? output = (`Rectangle with sides ${array.toString()} has a perimeter of ${new Rectangle(array).perimeter()} and an area of ${new Rectangle(array).area()}`):
    array.length == 3 ? output = (`Triangle with sides ${array.toString()} has a perimeter of ${new Triangle(array).perimeter()} and an area of ${new Triangle(array).area()}`):
    output = "";
    console.log(output);
}
```
