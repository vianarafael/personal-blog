---
title: Events in NodeJS
subtitle: Learn HTML and CSS with 10 projects - 1 book - 1 course 
category:
  - NodeJS
author: Rafael Viana
date: December 29, 2020
featureImage: /uploads/events.png
---
## Events in Node:
Something that happens in our App that we can respond to.

## Event Emitter class
```
const EventEmitter = require('events');

class MyEmitter extends EventEmitter {}

const myEmitter = new MyEmitter();
myEmitter.on('event', () => {
  console.log('an event occurred!');
});
myEmitter.emit('event');
```

It works similar to [addEventListeners](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener) on the front end.
The .on method allows you to set an event listener - the first argument is the event, the second is the callback function that will be called when that event is emitted.

You can register more than one callback function to the same event:

```
function something() {
	console.log('do something');
}

function somethingElse() {
    console.log('do something else');
}

myEmitter.on('someEvent', something);
myEmitter.on('someEvent', somethingElse);
myEmitter.emit('someEvent');

```

## Application
In Node, events are an alternative to deeply nested callbacks, a very loose way of coupling parts of your code together.

Imagine we are building a SaaS that does a number of things when a user creates an account. When a user record
is created, we want to emit a `userCreated` event. One of the listeners for this will email a confirmation
email to that user.

```
const { EventEmitter } = require('events');
const Emailer = require('./emailer');

const emailer = new Emailer();
const eventEmitter = new EventEmitter();

eventEmitter.on('userCreated', emailer.send);
eventEmitter.emit('userCreated', 'Rafael', 'To whom it may concern ...');
```
A lot of NodeJS depends on this features, and you can find a lot of other NodeJS APIs that inherit from the event API.