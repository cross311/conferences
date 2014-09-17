Defying callback hell
======

functional asynchronous programming with promises
-------

Presenter: [Marc Harter](http://twitter.com/wavded)

Writer: [Connor Ross](http://twitter.com/otter311)

library to help: `async`.  But does not help the problem callbacks!

### Promises!

Part of the ECMAScript 6.  IE7 and Up

Use the promise at anytime.


#### State Machine

```

-Pending
|
| - Fulfilled
|
| - Rejected

```

Fulfilled and rejected are settled.  Once settled the promise never changes.

#### Unwrapping

`promise.then(onFulfilled, onRejected)`

The two handlers are always async.

Variations:

```

promise.then(onFulfilled, onRejected)
promise.then(undefined, onRejected)
promise.catch(onRejected)

```

Then returns a new promise.  [spec](http://promiseaplus.com)

Promises are *values*

promise.then *unwraps* a promise


```

function forever(task) {
    return task().then(function() {
        return forever(task);
    });
}

```

^^ Stack not blown!!!


Combination

```

Promise.all
Promise.race
Promise.any
Promise.map
Promise.reduce

```

Libraries:

- Bluebird (authors choice)
- When
- Q
- (many others)

Convert your callbacks, bluebird

```

var fs = Promise.promisifyAll(require('fs'))
var promise = fs.readFileAsync('/path/to/file)

```

#### Tips

- drop the return habit
  - turns into returning undefined
- unhandled rejections
  - either return a promise or end in .done()
- 