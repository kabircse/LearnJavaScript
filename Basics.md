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
    
**Async & Await:** Async & await is basically just a syntactic sugar on top of Promises, these two keywords alone should make writing asynchronous code in Node much more bearable.
EX:

    async function getUserDetail() {
        try {
            let users = await getUsers();
            return users[0].name;
        } catch (err) {
            return {
                name: 'default user'
            };
        }
    }
    
**Scope:** Scope means variable access.
Local Scope: Inside the box

Global Scope: Outside the box

**Hoisting:**

**Closures:** A closure is simply a function inside another function that has access to the outer function variable.
Ex:
    
    const first = () => {
      const greet = 'Hi';
      const second = () => {
        const name = 'Md. Kabir';
        console.log(greet+ " " + name)
      }
      return second;
    }
    const newFunc = first()
    newFunc();
