**CallBack:** A callback is a function that passed as an argument to another function.

**Asynchronous:** Asynchronous is a way to call/running multiple functions in parallelly.

**Promise:** Promise is an object that represents the eventual completion/failure of an asynchronous operation and its resulting value.
  Promises can be used to avoid chaining callbacks. 
  
  A Promise states:

    1. pending: initial state, neither fulfilled nor rejected.

    2. fulfilled: meaning that the operation completed successfully.

    3. rejected: meaning that the operation failed.
Ex:
  
    var promise1 = new Promise(function(resolve, reject) {
      isDbOperationCompleted = false;
      if (isDbOperationCompleted) {
          resolve('Completed');
      } else {
          reject('Not completed');
      }
    });

    promise1.then(function(result) {
        console.log(result); //Output : Completed //fulfillment
    }).catch(function(error) { //rejection
        console.log(error); //if isDbOperationCompleted=FALSE                                                  
        //Output : Not Completed
    })
