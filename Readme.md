# Что такое синхронность JS?
## Синхронность означает то, что строка 2 не может запуститься до тех пор, пока строка 1 не закончит своё выполнение. JavaScript сам по себе однопоточный, что означает то, что только один блок кода может запускаться за раз.

# Что такое асинхронность?
## Асинхронность (Асинхронизм) (от греч. α — отрицание, συν — вместе, χρονος — время) — не совпадение с чем-либо во времени; неодномоментность, неодновременность, несинхронность — характеризует процессы, не совпадающие во времени.

![](./img%201.png)
![](./imj%202.png)

# Как это синхронно и асинхронно?
## Синхронная коммуникация — это когда получатель сразу отвечает на сообщение. Асинхронная — когда сообщение не предполагает моментальный ответ.

# What are Callbacks in JavaScript?
## A callback is a function that is passed inside another function, and then called in that function to perform a task. Confusing? Let's break it down by practically implementing it.

        console.log('fired first');
        console.log('fired second');

        setTimeout(()=>{
        console.log('fired third');
        },2000);

        console.log('fired last')

# What are Promises in JavaScript?
We hear people make promises all the time. That cousin of yours who promised to send you free money, a kid promising to not touch the cookie jar again without permission...but promises in JavaScript are slightly different.

A promise, in our context, is something which will take some time to do. There are two possible outcomes of a promise:

We either run and resolve the promise, or
Some error occurs along the line and the promise is rejected
Promises came along to solve the problems of callback functions. A promise takes in two functions as parameters. That is, resolve and reject. Remember that resolve is success, and reject is for when an error occurs.

Let's take a look at promises at work:

const getData = (dataEndpoint) => {
   return new Promise ((resolve, reject) => {
     //some request to the endpoint;
     
     if(request is successful){
       //do something;
       resolve();
     }
     else if(there is an error){
       reject();
     }
   
      });
    };
The code above is a promise, enclosed by a request to some endpoint. The promise takes in resolve and reject like I mentioned before.

After making a call to the endpoint for example, if the request is successful, we would resolve the promise and go on to do whatever we want with the response. But if there is an error, the promise will get rejected.

Promises are a neat way to fix problems brought about by callback hell, in a method known as promise chaining. You can use this method to sequentially get data from multiple endpoints, but with less code and easier methods.

But there is an even better way! You might be familiar with the following method, as it's a preferred way of handling data and API calls in JavaScript.   


# What is Async and Await in JavaScript?
The thing is, chaining promises together just like callbacks can get pretty bulky and confusing. That's why Async and Await was brought about.

To define an async function, you do this:

const asyncFunc = async() => {

}
Note that calling an async function will always return a Promise. Take a look at this:

     const test = asyncFunc();
console.log(test);
Running the above in the browser console, we see that the asyncFunc returns a promise.

Let's really break down some code now. Consider the little snippet below:

 
The async keyword is what we use to define async functions as I mentioned above. But how about await ? Well, it stalls JavaScript from assigning fetch to the response variable until the promise has been resolved. Once the promise has been resolved, the results from the fetch method can now be assigned to the response variable.

The same thing happens on line 3. The .json method returns a promise, and we can use await still to delay the assigning until the promise is resolved.



## Глобальная функция fetch() Глобальный метод fetch() запускает процесс извлечения ресурса из сети. Возвращает promise, содержащий Response объект (ответ на запрос). Промис fetch() завершается TypeError , если возникает сетевая ошибка, хотя обычно это означает проблему с доступами или аналогичную ей.7

## Что делает Fetch JS?

Fetch API предоставляет интерфейс JavaScript для работы с запросами и ответами HTTP. Он также предоставляет глобальный метод fetch() (en-US), который позволяет легко и логично получать ресурсы по сети асинхронно. Подобная функциональность ранее достигалась с помощью XMLHttpRequest .6 янв. 2024 г.