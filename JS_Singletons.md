# Singletons

Get the same instance of the object every time

```JS
var mySingleton = (function(){
  // scope 1
  var instance
  
  function init(){
    // scope 2
    var privateRandomNumber = Math.random()
    return {
      getRandomNumber: function(){
                        return privateRandomNumber
                       },
      nu: priveteRandomNumber
     }
  }
  
  return {
    getInstance: function() {
      if(!instance){
        instance = init()
      }
      return instance
    }
  }

})()

var singleA = mySingleton.getInstance()
console.log(singleA.getRandomNumber())
var singleB = mySingleton.getInstance()
console.log(singleB.getRandomNumber())
```

The first time you run mySingleton.getIntance() it returns object created by init()
Next time it returns the same object (because of the if statement)

Components:
* 1 anonymouse driver function that returns the an object containing getInstance function
* one init function which returns a new instance containing private methods and props, called by getInstance
* getInstance function which returns instance
  
You will get the same random number in every instance
