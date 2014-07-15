Some languages allow you to specify whether you're passing something as a reference, or as a value. JavaScript does not. Primitives are always passed as values, meaning they are copied. Objects and arrays are passed as values that reference a pointer in memory — practically speaking, they're passed as references.

The following example shows how you can pass an object to a function, and change the value of that object. But, if you create a copy of that object, then you lose the reference to that object.

```
(function() {

  var testObj, justChangeValue, createNewObj;
  
  justChangeValue = function (obj) {
    
   obj.test =  1;
    
  }
  
  createNewObj = function(obj) {
    
    var obj = {
      test0: 0
    }
    
  }
  
  var testObj = {test: 0};

  justChangeValue(testObj);

  //testObj.test = 1;
  
  createNewObj(testObj);
  
  //testObj.test (STILL) = 1;

  
}());
```