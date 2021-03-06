


# Node Genbrain

A node.js library for building reactive algorithm networks. A new design pattern.

http://rauljordan.github.io/node-genbrain

[![Build Status](https://travis-ci.org/rauljordan/node-genbrain.svg?branch=master)](https://travis-ci.org/rauljordan/node-genbrain)


![Imgur](http://i.imgur.com/zMPjMW7.jpg)

## The Case for a New Pattern

> Imagine a system that lives and breathes algorithms and
> data-structures reactively...a system whose components seem to link to each other
> seamlessly and change magically in real-time but at the same time all being part
> of the same whole...a truly reactive network of algorithms

Many large  systems rely on many components that can easily become nested or a large amount of complex links between them, and are considerably harder to manage once streams of real time information come into play. Eventually, they fail when users want them to work as expected on a real-time basis. **Why can't we have a design pattern that encapsulates a reactive network of components?** This is the basis of genbrain solves this issue by sticking to these two core ideas that **encapsulate** reactivity:
  - A completely reactive framework that allows users to link components of an application seamlessly
  - An unobtrusive yet simple way of managing every component in a system at once

Having a platform that gives us this power by building reactive projects and link their components together using little overhead is the strength of Genbrain.



### Core Features

Genbrain relies on a few core features as a framework for building javascript applications

* a powerful workflow for linking different data-structures and algorithms in a project
* a way of encompassing reactivity in every component of a genbrain project
* methods of immediately targeting components of a genbrain project, or the whole project at once
* reactive methods that manage internal state of a genbrain project elegantly in real-time
* being able to adapt to any kind of modular project



## Installing Genbrain

```sh
$ npm install node-genbrain
```

## A Basic Example

Imagine a simple node.js application that runs constant analysis over the data in a news website by scraping some of its components. The program runs forever and consistenly checks if there is a live update on the website, and if there is one, it reacts to it by notifying every component of the system, a part that does machine learning over the data, the part that inserts it into a database, etc.


In a reactive system, this should not be an issue. Data and output should change immediately and without a program checking for changes. What makes it worse is that if there are also many linked algorithms that increase complexity even further. Now if one thing changes, we have to respond and fetch new changes on everything else because it all goes together.

```javascript
// Non-Reactive and naive javascript implementation

runEveryFiveSeconds(function () {
  if (thereAreNewNews) {

    if (thereAreNewMachineLearningNews) {
      updateNewsAnalysis();
    }
    else {
      runNormalNewsAnalysis();
    }

    ...
  }
});

```

In Genbrain, the project architecture along with all its modules is reactive since the very beginning. Morever, genbrain includes methods out-of-the-box that allow a user to quickly decouple running algorithms or modules from the main architecture, add new ones on the fly, analyze their runtime behavior and output reactively, and visualize the entire system in a web application all at the same time. The genbrain workflow allows a user to not worry about reactivity or module decoupling, because it every part of the project is encapsulated by the common genbrain architecture.

```javascript
// Being encapsulated by genbrain, the system immediately becomes reactive
// to new news changes and runs all of its functions encapsulated by reactivity
genbrain.components({
  funcs: [
    runNewsAnalysis,
    runMachineLearning,
    runNewsSentimentAnalysis
  ]
});

genbrain.run();

```

## First Steps

We will go through the process of building a simple genbrain architecture and exploring some of its options, including showing how it encapsulates reactivity across modules.



## Development

Want to contribute? Great! Please submit a pull request and I'll review it and integrate it as fast as I can. Write up some tap tests for your implementation before submitting.



License
----

MIT
