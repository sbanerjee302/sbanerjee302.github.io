---
description: A superficial overview to promises in Java-script
---

# Promises kept and broken

The concept of promises in Java-script hinges on the literal meaning of the word _promise._ We either keep a promise we made or we break it. Translated to the java-script, when we _keep_ a promise, we _resolve_ it and when we _break_ our promise we _reject_ it.

When it comes to the word promise, in our daily activity, we are basically making a statement based on certain conditions, the outcomes of which we are unaware of or outside our control. For example, "_I will return the book to you as soon as I get back_". The statement is _"I will return the book to you"_, the condition part being _"as soon as I get back_". Here the condition part is uncertain, in the sense that I will get back and return the book or I will not get back and so the book will not be returned. 

Enough with the literature...now let's see some code :-

Let's make a promise

```text
function crossMyHeart(didIReturn) {
    /* Making the promise....*/
    /* but I still do not know if I would return...*/
    return new Promise(function(resolve, reject) {
    
    if (didIReturn) {
      /*.. I kept my promise...*/
      resolve("I returned the book");
    } else {
      /*.. I could not keep my promise...*/
      reject("Sorry I could not return you book");
    }
    
  });
}

// When the promise is kept...
crossMyHeart(true).then(function(resolveMessage){
  // Should alert "I returned the book"
  alert(resolveMessage);
}, function(rejectMessage) {
  alert(rejectMessage);
});

// When the promise is broken...
crossMyHeart(true).then(function(resolveMessage){
  alert(resolveMessage);
}, function(rejectMessage) {
  // Should alert "Sorry I could not return you book"
  alert(rejectMessage);
});
```

I do hope that up till now I have made sense. Of course, when it comes down to actual implementation, we face way more complex scenarios like simultaneous promises, race condition handling, ordered execution, chaining, zipping and all those stuff. The essential part is the resolution and rejection criteria, which would ultimately decide the outcome, for here in lies what is popularly known as _"business logic"._

For a deeper \(and of course better\) understanding I would suggest the following :-

* [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
* [Google Developers Blog](https://developers.google.com/web/fundamentals/primers/promises)
* [Hackernoon](https://hackernoon.com/understanding-promises-in-javascript-13d99df067c1)

and last but not the least StackOverflow and YouTube. Happy promising :\)



