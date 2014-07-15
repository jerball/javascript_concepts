Some languages allow you to specify whether you're passing something as a reference, or as a value. JavaScript does not. Primitives are always passed as values, meaning they are copied. Objects and arrays are passed as values that reference a pointer in memory — practically speaking, they're passed as references.

The following example shows how you can pass an object to a function, and change the value of that object. But, if you create a copy of that object, then you lose the reference to that object.

```
(function() {

  var testObj, justChangeValue, createNewObj;

  //this is going to change the value of the object when you pass that object in
  justChangeValue = function (obj) {

   obj.test =  1;

  }

  //we pass the object in, but we also create a new object with the same name
  createNewObj = function(obj) {

    obj = {
      test: 0
    }

  }

  // our object
  testObj = {test: 0};

  //pass in a reference to the object
  justChangeValue(testObj);

  //hey! it's changed!
  console.log(testObj.test);// this equals 1

  //pass the object in again, to a different function
  createNewObj(testObj);

  //it's NOT changed!
  console.log(testObj.test);// this STILL equals 1


}());
```