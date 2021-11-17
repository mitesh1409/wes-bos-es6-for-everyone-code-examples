# Module-10: Promises

## Using Promises

Promises are often used for fetching the response from a JSON API and doing some AJAX work.

fetch() returns an object of type Promise.

Some of the available functions on Promise object are
.then()
.catch()

.then() is called as soon as the response is received.

.catch() is used to handle failures.

----

## Building Your Own Promises

We can build our own promises as per the application requirement.


----

## References

[JavaScript Promise in 100 Seconds](https://www.youtube.com/watch?v=RvYYCGs45L4)

JavaScript Promise manages a single async value that can be handled in the future.

Example

Analogy with an Uber ride request

```
// Create a Promise

// It takes a callback function as an argument.
// This callback is an executer, it can either resolve it with a value or reject it with an error.

const ride = new Promise((resolve, reject) => {
    // resolve with a value

    // OR

    // reject with an error

    if (! driverArrived) {
        reject(Error('Ride request cancelled.'));
    }

    resolve('Driver arrived, ride can be started.');
});

// Consume a Promise

// then() function takes a callback as an argument.
// It is called as soon as the Promise is resolved/fulfilled successfully.
// So basically it handles fulfillment.

// catch() handles reject/failure.

// finally() is called in both the cases.

// All of these methods return the same Promise object so that they can be chained together 
// to handle multiple asynchronous operations.

ride
    .then(value => {
        console.log(value);
    })
    .catch((error) => {
        console.error(error);
    })
    .finally(() => {
        console.log('Ride request settled!');
    });
```
