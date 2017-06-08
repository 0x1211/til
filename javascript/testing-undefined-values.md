# Testing undefined values

While working on an open source library I often encountered this kind of statement:

```
if (typeof whatev === undefined) {
  // do whatev
}
```

I was used to write such statements this way:

```
if (!whatev) {
  // do whatev
}
```

I was then wondering why would I use the other ugly syntax ? :thinking:

Then @taxigy gave me the following enlightning explanation:

> You may use the first case when you don't know if `whatev` exists.

Then he mindblowned me with the simple-as-f*ck demo below:

```
$ node
> args
ReferenceError: args is not defined
    at repl:1:1
    at ContextifyScript.Script.runInThisContext (vm.js:23:33)
    at REPLServer.defaultEval (repl.js:339:29)
    at bound (domain.js:280:14)
    at REPLServer.runBound [as eval] (domain.js:293:12)
    at REPLServer.onLine (repl.js:536:10)
    at emitOne (events.js:101:20)
    at REPLServer.emit (events.js:191:7)
    at REPLServer.Interface._onLine (readline.js:241:10)
    at REPLServer.Interface._line (readline.js:590:8)
> typeof args
'undefined'
> typeof args === 'undefined' ? true : false;
true
> var args = undefined;
undefined
> !args ? true : false;
true
```
Here in the first statement we are asking `args` value to node. But `args` does not exist as a variable so node throws a `ReferenceError` which will not be thrown if we check its `typeof` value (see second statement above).
However when we define `args` variable with an `undefined` value then a `ReferenceError` would not be thrown.

Conclusion: checking `typeof` may be ugly to read but can prevent from `ReferenceError` at runtime.

Thanks @taxigy ! 
