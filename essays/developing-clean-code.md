---
layout: essay
type: essay
title: "Developing Clean Code"
# All dates must be YYYY-MM-DD format!
date: 2022-09-22
published: true
labels:
  - Coding Standards
---

## Clean Code?
Clean code refers to code that is easy to understand and it is something that every software engineer should keep in mind. After all, large software projects will always be done by a team rather than an individual. Clean code is essential in a team environment in order to be able to read and understand what a piece of software is doing, no matter who it was written by. Otherwise, when you have many types of formatting styles, even simple functions can become difficult to comprehend. The way that this problem can be fixed is through the use of coding standards and analysis programs like ESLint, which we have started using in my ICS 314 Software Engineering class.

## My Experience
This past week, we have been learning how to use IntelliJ Idea as well as getting used to programming with coding standards and ESLint. I think that the hardest part of this week was adjusting to using an integrated development environment (IDE) like IntelliJ Idea since I have always used Vim. So far, I have seen many positives to IntelliJ Idea such as the many helpful packages and navigation shortcuts. Looking back, learning to use an IDE is something that I definitely wished I had done sooner.

On the other hand, I have not had that much trouble with implementing the coding standards through ESLint. The coding standard we are currently using in the ICS 314 class is similar to the formatting I have used since I started learning programming. Seen below are examples of how I structured my code before and after learning about the coding standards used in this class. Something slightly different between both formatting styles was the spacing in conditional statements and loops. Another helpful aspect I noticed was the recommendations on when to use let or const to declare a variable. Overall, I definitely think that ESLint has been helpful as it points out any errors in my code and has also made my code easier to read.

```js
// Before Using ESLint
function BertErnie() {
  for(let i = 1; i <= 100; i++) {
    if(i % 4 === 0 && i % 6 === 0) {
      console.log("BertErnie");
    } else if(i % 4 === 0) {
      console.log("Bert");
    } else if(i % 6 === 0) {
      console.log("Ernie")
    } else {
      console.log(i);
    }
  }
}
```

```js
// After Using ESLint
function zipList(arr1, arr2) {
  const returnArray = [];
  for (let i = 0; i < arr1.length; i++) {
    returnArray.push(arr1[i]);
    returnArray.push(arr2[i]);
  }
  return returnArray;
}

function zipListTheSimpleWay(arr1, arr2) {
  return _.flatten(_.zip(arr1, arr2));
}
```

## Future
Although using ESLint results in code which is not that different from my old formatting, I continue making some errors such as determining when to use const or let to define a variable. I definitely have to continue practicing coding with ESLint in order to become more efficient and comfortable with the style. However, once I am adapted to using the coding standards, one big positive is producing code that is easily understandable for myself and others. No matter what class or job I take in the future, I would definitely consider using some sort of coding standard.
