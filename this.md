An example of using Function.prototype.bind to apply the scope of _this_ to a closure inside an object's method.

As an aside, if you need to support IE8, you'll need to use a polyfill, as Function.protytope.bind wasn't supported in IE until IE9.

```
var myObj = {
  
  a: function() {
  
    console.log( "a" );
    
  },
  
  b: function() {
  
    console.log( "b" );
    
  },
  
  c: function() {
  
    var doA, doB, doBoth;
    
    doA = function() {
     
      this.a();
      
    }.bind(this);
    
    doB = function() {
      
      this.b();
      
      
    }.bind(this);
    
    doBoth = function() {
     
      this.a();
      this.b();
      
    }.bind(this);
    

    return {
      doA: doA,
      doB: doB,
      doBoth: doBoth
    }
    

  }
  
}

myObj.c().doA();
myObj.c().doB();
myObj.c().doBoth();
```