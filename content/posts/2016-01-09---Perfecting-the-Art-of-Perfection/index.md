---
title: Linking prototypes and Object
date: "2016-09-01T23:46:37.121Z"
template: "post"
draft: false
slug: "/posts/perfecting-the-art-of-perfection"
category: "Design Inspiration"
tags:
  - "Handwriting"
  - "Learning to write"
description: "It feels link an achievement to at least understand the prototype and its links with the objects of javascript. This blog consist of diagram and related code to make it understandable easily."
socialImage: "./media/notebook.jpg"
---

The story starts with a paradigm which has ruled the world of coding, generating efficient methods to write good programs. The paradigm known as OOP. If you're familiar with OOPs (Object Oriented Programming), objects and classes you might be particularly knowing what inheritance is. But my friend in javascript the story is implemented in a rather pesky way.

![Nulla faucibus vestibulum eros in tempus. Vestibulum tempor imperdiet velit nec dapibus](/media/notebook.jpg)

Until Es 2015 JS fully-fledgedly relied on prototypes to implement inheritance, now theres something called the Class syntax which basically overshadows the functionality. However in this article we should stick to prototype and will let the class syntax rely on a different article.

### Behind the scenes of creating an object

Consider the following set of codes-:

```js
let house = {}
```

```js
let house = new Object()
```

Its obvious that there are two ways to make an object in javascript as initiated above.
What makes it important is that we know `Object` is a constructor which is required to make objects. Both the ways described above have a pretty same syntax but under the hood they create the object in particularly without any difference i.e by using a constructor.

### The _Object.prototype_ and prototype chain

_Rule 1: Every object in javascript has a prototype called an Object.prototype._ Let this sink in.
Whenever we create an object two things happens. First the object itself is generated and secondly an _Object.prototype_ is added to it.
 The reason to introduce the constructor based syntax is to highlight the point that even Object constructor is that matter whichever syntax you choose this rule won't be neglected. The object prototype will always stay at the top of the chain i.e will be linked to any object.

If Rule 1 has sinked lets introduce the second rule which is actually hinted in the first rule itself.
_Rule 2: An object may have multiple prototype in such case each prototype will have its own prototype thus forming a prototype chain._
Javascript has reaches a particular property or method using bracket or dot notation. It first looks for them in the object then in the prototype and all the prototype chains. If the property or method doesn't exist it greets us with an `undefined`. And indicates that we have reached `null` for its own prototype.

The following rule is a combination of the above two rules we undertook.

_Rule 3: The last chain of prototype is Object.prototype and above it there is only one chain called `null`_
The prototypes will be looked for until we reach the last chain. The calling of last chain should always result in a null.

<https://www.youtube.com/watch?v=01jVgCK-HX4>
<!-- prototype needs to be set on newly created onjects -->