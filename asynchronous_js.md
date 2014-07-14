An example of using callbacks.

'''
(function() {

  var alpha, alphaCallback, beta, betaCallback;
    
  beta = function(callback) {
    
    console.log('gamma');

    callback();
    
  }

  betaCallback = function() {

    console.log('delta');

  }

  alphaCallback = function() {
   
    console.log('beta');

  };
  
  alpha = function(callback) {
   
    console.log('alpha');
    
    callback();

    beta(betaCallback);
    
  }

  alpha(alphaCallback);
  
}());
'''

Using callbacks with a _setTimeout_ function — to demonstrate how callbacks are handled asynchronously.

'''
(function() {

  var alpha, alphaCallback, beta, betaCallback;
    
  beta = function(callback) {
    
    setTimeout(function() {
      console.log('gamma');
    }, 1000);

    callback();
    
  }

  betaCallback = function() {

    console.log('delta');

  }

  alphaCallback = function() {
   
    console.log('beta');

  };
  
  alpha = function(callback) {
   
    setTimeout(function() {
      console.log('alpha');
    }, 1000);    
    
    callback();

    beta(betaCallback);
    
  }

  alpha(alphaCallback);
  
}());
'''