# Asynchronicity-and-the-event-loop

Quick erratum for those who attended the workshop: 

.then() calls will always return a promise, which is why I was able to 
keep chaining new promises just by having a return statement in the one 
above. You could keep going like this: 

```
const promiseToExecuteMorning = new Promise((resolve, reject) => {
    setTimeout(() => {
            resolve("meow until she wakes up");
    }, 1000);
}).then((string) => {
    return string;
}).then((string) => {
    return string;
}).then((string) => {
    return string;
}).then((string) => {
    console.log(string)
});
```

There wouldn't be much of a point doing this, but you could, since every single 
.then() in the chain would return its own promise.
