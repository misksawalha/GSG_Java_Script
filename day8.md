
## Closuer
Is a fundamental programming concept that occurs when a function retains access to its containing scope even after the function has finished executing. In simpler terms, a closure allows a function to "remember" its surrounding context, including variables, even after the function has completed its execution.
 

##### **Lexical (Static) Scoping**:
In lexical scoping, the scope of a variable is determined by its position in the source code. A variable defined within a function is accessible only within that function and any nested functions within it.  


### Asynchronous JavaScript  : 
**Promises** :  are a fundamental concept in JavaScript used for handling asynchronous operations in a more organized and manageable way. They were introduced to make it easier to work with asynchronous code and avoid callback hell, a situation where multiple nested callbacks can lead to difficult-to-read and maintain code.

Promises has three possible states:

1. Pending: The initial state, representing that the operation is ongoing.
2. Fulfilled: The operation completed successfully, and the promise now holds a value.
3. Rejected: The operation failed, and the promise holds a reason for the failure.

#### Callback queue :
part of the event loop mechanism, which is responsible for handling asynchronous operations and callbacks in a single-threaded environment

##### Callback hell:
Also known as the "pyramid of doom," refers to a situation in JavaScript where multiple nested callbacks are used to handle asynchronous operations. This can lead to code that is difficult to read, understand, and maintain due to the deep nesting of functions. Asynchronous operations executed within callbacks can quickly become challenging to manage, making the code more error-prone and harder to debug.


## Tasks:

### Q1:
You are given a function executeInSequenceWithCBs and some code. The task is to modify the executeInSequenceWithCBs function so that it runs and executes all the tasks inside the asyncTasks array.
The function should return an array of messages obtained from each task's execution.
You are only allowed to change the executeInSequenceWithCBs function or add new functions/code. You cannot modify the tasks' functions.

```
const task1 = (cb) => setTimeout(() => {
    const message = "Task 1 has executed successfully!";
    cb(message);
  }, 3000);
  
  const task2 = (cb) => setTimeout(() => {
    const message = "Task 2 has executed successfully!";
    cb(message);
  }, 0);
  
  const task3 = (cb) => setTimeout(() => {
    const message = "Task 3 has executed successfully!";
    cb(message);
  }, 1000);
  
  const task4 = (cb) => setTimeout(() => {
    const message = "Task 4 has executed successfully!";
    cb(message);
  }, 2000);
  
  const task5 = (cb) => setTimeout(() => {
    const message = "Task 5 has executed successfully!";
    cb(message);
  }, 4000);
  
  const asyncTasks = [task1, task2, task3, task4, task5];
  
  const executeInSequenceWithCBs = (tasks, callback) => {
    const results = [];
    
    const executeTask = (index) => {
      if (index < tasks.length) {
        const currentTask = tasks[index];
        currentTask((message) => {
          results.push(message);
          executeTask(index + 1);
        });
      } else {
        callback(results);
      }
    };
    
    executeTask(0);
  };
  
  executeInSequenceWithCBs(asyncTasks, (messages) => {
    console.log(messages); 
  });
```

### Q2:
You are given a function called executeInParallelWithPromises, which takes an array of APIs (represented by objects).
Your task is to write code that fetches the data of each API in parallel using promises. In Parallel means that the api which resolves first, returns its value first, regardless of the execution order.
The output of the executeInParallelWithPromises function should be an array containing the results of each API's execution.
Each result should be an object with three keys: apiName, apiUrl, and apiData..
```
const apis = [
    {
      apiName: "products", 
      apiUrl: "https://dummyjson.com/products",
    }, 
    {
      apiName: "users", 
      apiUrl: "https://dummyjson.com/users",
    }, 
    {
      apiName: "posts", 
      apiUrl: "https://dummyjson.com/posts",
    }, 
    {
      apiName: "comments", 
      apiUrl: "https://dummyjson.com/comments",
    }
  ]
  
  const fetchApiData = async (api) => {
    try {
      const response = await fetch(api.apiUrl);
      const data = await response.json();
      console.log("data "+data)
      return {
        apiName: api.apiName,
        apiUrl: api.apiUrl,
        apiData: data,
      };
    } catch (error) {
      return {
        apiName: api.apiName,
        apiUrl: api.apiUrl,
        error: error.message,
      };
    }
  };
  
  const executeInParallelWithPromises = async (apis) => {
    const promises =await apis.map(api => fetchApiData(api));
    
    try {
      const results = await Promise.all(promises);
      return results;
    } catch (error) {
      console.error(error);
      return [];
    }
  };
  
  executeInParallelWithPromises(apis)
    .then(results => {
      console.log(results);
    })
    .catch(error => {
      console.error("Error:", error);
    });

```

### Q3:
Write a closure named powerOf that takes a base number base and returns a function. 
The returned function, when invoked with an exponent exp, should calculate and return the result of base raised to the power of exp.


```
const apis = [
  {
    apiName: "products", 
    apiUrl: "https://dummyjson.com/products",
  }, 
  {
    apiName: "users", 
    apiUrl: "https://dummyjson.com/users",
  }, 
  {
    apiName: "posts", 
    apiUrl: "https://dummyjson.com/posts",
  }, 
  {
    apiName: "comments", 
    apiUrl: "https://dummyjson.com/comments",
  }
]

//modify and write your code here
const executeInSequenceWithPromises = (apis) => {}

sol:
const fetchApiData = async (api) => {
  const response = await fetch(api.apiUrl);
  const data = await response.json();
  return {
    apiName: api.apiName,
    apiUrl: api.apiUrl,
    apiData: data,
  };
};

const executeInSequenceWithPromises = async (apis) => {
  const results = [];
  for (const api of apis) {
    const result = await fetchApiData(api);
    results.push(result);
  }
  return results;
};

const apis = [
  {
    apiName: "products",
    apiUrl: "https://dummyjson.com/products",
  },
  {
    apiName: "users",
    apiUrl: "https://dummyjson.com/users",
  },
  {
    apiName: "posts",
    apiUrl: "https://dummyjson.com/posts",
  },
  {
    apiName: "comments",
    apiUrl: "https://dummyjson.com/comments",
  },
];

executeInSequenceWithPromises(apis)
  .then((results) => {
    console.log(results);
  })
  .catch((error) => {
    console.error(error);
  });

```

