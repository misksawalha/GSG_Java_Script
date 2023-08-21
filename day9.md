
## Promises
- Fetch : is a modern and powerful way to make network requests, typically used for fetching resources such as data or files from a server. It returns a Promise that resolves to the Response to that request, whether it's successful or not

- .then : method in JavaScript is a key feature of Promises, which are used to manage asynchronous operations and handle their outcomes.

- Microtask queue : is a concept related to the event loop and asynchronous execution. It's a queue that holds microtasks, which are tasks that need to be executed as soon as possible after the currently executing script, but before rendering

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
You are given a function called executeInSequenceWithPromises, which takes an array of APIs (represented by objects).

Your task is to write code that fetches the data of each API sequentially (one after the other) using promises.

In Sequence means that the api which executes first, returns its value first.

The output of the executeInSequenceWithPromises function should be an array containing the results of each API's execution.

Each result should be an object with three keys: apiName, apiUrl, and apiData.

```
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
