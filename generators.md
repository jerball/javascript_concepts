Generators are a new feature in ECMAScript 6. Using a generator, you can interrupt the execution of a function, and communicate between the function and other elements in your script.

In the following example, we create two instances of the *foo generator. The yield expression pauses execution and sends something back. The next method (outside the generator) has the generator restart, going on to the next yield, or to completion.


```
function *foo() {
    yield 1;
    yield 2;
    yield 3;
    yield 4;
    yield 5;
}

var it = new foo();

var test = new foo();

it.next().value;//1
it.next().value;//2
it.next().value;//3
it.next().value;//4
it.next().value;//5

test.next().value;//1
test.next().value;//2
test.next().value;//3
test.next().value;//4
test.next().value;//5
```