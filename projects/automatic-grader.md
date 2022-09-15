---
layout: project
type: project
image: img/automatic-grader/GAS.png
title: "Automatic Grader"
date: 2022-09
published: true
labels:
  - JavaScript
  - Google Apps Script
  - Application Programming Interface (API)
summary: "A program which automatically inputs grades to Google Classroom."
---

## Background 

<img width="250px" class="rounded float-start pe-4" src="../img/automatic-grader/zyBooks.png">
During the Fall 2022 semester, I worked as one of the Teaching Assistants for EE 160 - Programming for Engineers. Each of us were in charge of teaching a lab section where students learned Python through an online [zyBooks](https://www.zybooks.com/catalog/programming-in-python-3/) course. As Teaching Assistants, we also had to input the grades of zyBook assignments into Google Classroom. This was a very tedious and painful process considering that there were almost 100 students in the class. One of the other Teaching Assistants then introduced me to the Google Apps Script service which would allow us to automate inputting grades. When I learned it used JavaScript, I decided to utilize what I had been learning for the past few weeks in my ICS 314 class.


<img width="250px" class="rounded float-start pe-4" src="../img/automatic-grader/Google-Classroom.png">
## What I Learned

Since zyBooks created assignment reports which were CSV files, I was able to upload them into a spreadsheet. However, I did not know how to take the grades from the spreadsheet and transfer them into Google Classroom. This let me to research into the different Application Programming Interfaces (APIs) of Google and how to use them in Google Apps Script. The two which I ended up using were the Google Sheets API, as well as the Google Classroom API. Writing the script also reinforced my understanding of concepts being taught in ICS 314 such as functional programming, which was often used to access and modify data with either of the two APIs. The function below demonstrates an example of how I used the Google Classroom API, in addition to using functional programming with the built-in array methods of JavaScript.

```javascript
function getAssignmentID(COURSE_ID, ASSIGNMENT_NAME) {

  const assignments = Classroom.Courses.CourseWork.list(COURSE_ID).courseWork;

  const assignmentItem = assignments.find(assignment => assignment.title === ASSIGNMENT_NAME);

  if (assignmentItem !== undefined) {
    return assignmentItem.id;
  } else {
    console.log(`Did not find the Assignment '${ASSIGNMENT_NAME}'`);
  }

};
```

Source: [EE 160 Grading Script](https://script.google.com/d/1AvZ8lDavanu9NaFii6yyoyNH4mckSeCE12NVNav8phw69AmsxB9DtNGD/edit?usp=sharing)