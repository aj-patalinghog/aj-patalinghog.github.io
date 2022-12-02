---
layout: essay
type: essay
title: "Coding Recipes"
# All dates must be YYYY-MM-DD format!
date: 2022-12-01
published: true
labels:
  - Design Patterns
  - Javascript
---

When cooking food, there is no set way or recipe that is always the best. There are many different variations in ingredients, preparation methods, and cooking techniques that have a huge impact on the final result. In general, food is also subjective to each person’s taste and is up to them to determine what is good or not. This is really similar to the design patterns that we have been learning about in my ICS 314 class.

## Coding Recipes?

Design patterns are general solutions to common problems that are seen in programming. Much like in cooking, they are the various coding recipes which developers can pick and choose from. They not only guide us and give us a general structure to work with, but can also play a large role in how we code something. Just like in cooking, we also have to be able to determine what suits our needs the best, or else we end up risking bad results and wasted time. In the end, design patterns are suggestions and are not meant to restrict us to a certain method. This level of freedom is similarly found in cooking which enables them to be versatile and useful for any project.

## My Dishes

For the past month, I have been working in a team for our final project, [Rainbow Notes](https://rainbow-notes.github.io). Although I didn’t realize it, there are many different design patterns which we have been using so far. The two patterns below are examples which I want to focus on.

### Publish-Subscribe Design Pattern

In this pattern, there are two roles: publishers and subscribers. A quick summary is that publishers will send data out when an event or change in state happens and only those who are subscribed to that publication will be able to receive that data and use it. This was especially useful when dealing with the MongoDB collections in our project. Below is a sample of code from the Notes Collection which implements this design pattern.

```js
// Server side
// Define a publication to publish all notes.
Meteor.publish(Notes.userPublicationName, () => Notes.collection.find());

// Client side
// Get access to Note documents.
const subcription = Meteor.subscribe(Notes.userPublicationName);
// Get the Note documents
const notes = Notes.collection.find({}).fetch();
```

### Singleton Design Pattern

In this pattern, a “global variable” is created which can be accessed and managed from anywhere in the project. It was specifically used to create instances of the four collections which we have in our project. Each of the collections were exported to the rest of the project and were easily manipulated from the methods throughout the client side. Below is a sample of code from the Courses Collection which implements this design pattern.

```js
/**
 * The CoursesCollection. It encapsulates state and variable values for courses.
 */
class CoursesCollection {
  constructor() {
    // The name of this collection.
    this.name = 'CoursesCollection';
    // Define the Mongo collection.
    this.collection = new Mongo.Collection(this.name);
    // Define the structure of each document in the collection.
    this.schema = new SimpleSchema({
      name: String,
      path: String,
    }, { tracker: Tracker });
    // Attach the schema to the collection, so all attempts to insert a document are checked against schema.
    this.collection.attachSchema(this.schema);
    // Define names for publications and subscriptions
    this.userPublicationName = `${this.name}.publication.user`;
    this.adminPublicationName = `${this.name}.publication.admin`;
  }
}

/**
 * The singleton instance of the CoursesCollection.
 * @type {CoursesCollection}
 */
export const Courses = new CoursesCollection();
```

## The Result

Design Patterns are wonderful tools which can make our lives as developers much easier. They provide an easy way to get started on a project so that we don't have to start from scratch all the time. Rather than worrying about the structure of our code, we can instead focus that time on improving other aspects. Although I have been using them throughout my schooling, I didn’t realize what they were until this past week. I’m surprised to see how common they were and I will definitely be using them in the future as well.
