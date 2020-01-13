---
description: A very basic introduction to promises in Java-script
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

