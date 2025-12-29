+++
date = 2024-06-21T12:52:57Z
description = ""
draft = true
image = "__GHOST_URL__/content/images/2024/06/race.webp"
slug = "applying-a-timeout-to-promises-with-promise-race-2"
title = "Applying a Timeout to Promises with Promise.race()"

+++


In modern web development, handling asynchronous operations efficiently is crucial for creating responsive and performant applications. JavaScript’s Promise object is a cornerstone in managing these operations, but what happens when a promise takes too long to resolve? This is where Promise.race() comes into play, allowing developers to impose a timeout on promises. This blog post explores how to use Promise.race() alongside a custom timeout promise to ensure your application remains responsive, even when some operations don't go as planned.


Understanding Promise.race()

Before we dive into timeouts, let’s briefly recap what Promise.race() does. This method takes an iterable of Promise objects and returns a new promise that resolves or rejects as soon as one of the promises in the iterable resolves or rejects, with the value or reason from that promise.

This behavior is perfect for implementing timeouts. By racing your promise against a timeout promise, you can ensure that your operation either completes in the allotted time or fails with a timeout error, thus preventing it from hanging indefinitely.


Creating a Timeout Promise

To implement a timeout, we first need to create a promise that rejects after a certain amount of time. This is straightforward with JavaScript’s setTimeout() function. Here's how you can create such a promise:

function timeout(ms, errorMessage = 'Operation timed out') {
  return new Promise((_, reject) =>
    setTimeout(() => reject(new Error(errorMessage)), ms)
  );
}

In this function, ms represents the timeout duration in milliseconds, and errorMessage is the error message that will be used if the promise times out. This promise does not resolve; it either rejects after the specified timeout or is ignored if another promise in the race completes first.


Using Promise.race() for Timeout

Now that we have a timeout promise, let’s see how to apply it to an asynchronous operation. Suppose we have a function fetchData() that returns a promise which resolves with some data from an API. We want this operation to timeout if it takes more than 2 seconds. Here's how we can achieve that:

function fetchData() {
  // This function returns a promise that resolves with data from an API
}

function withTimeout(promise, ms) {
  return Promise.race([
    promise,
    timeout(ms)
  ]);
}

const promise = fetchData();

withTimeout(promise, 2000)
  .then(data => {
    console.log('Data:', data);
  })
  .catch(error => {
    console.error('Error:', error.message);
  });

In this example, withTimeout is a utility function that takes a promise and a timeout duration. It races the given promise against the timeout promise created by our timeout function. If fetchData completes within 2 seconds, its result will be logged. If it takes longer, the operation will be aborted, and the timeout error will be logged instead.


What Have You Accomplished

Using Promise.race() for timeouts adds robustness to your application, especially when dealing with external APIs or operations that may hang due to unforeseen circumstances. However, it's important to handle these timeouts gracefully, ensuring your application's user experience remains smooth.

Additionally, remember that the timeout does not cancel the original operation; it merely stops waiting for its completion. If you need to cancel the operation (for example, an HTTP request), you’ll need to implement cancellation logic specific to that operation.