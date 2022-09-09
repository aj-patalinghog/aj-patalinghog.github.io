---
layout: essay
type: essay
title: "Learning to Ask Smart Questions"
# All dates must be YYYY-MM-DD format!
date: 2022-09-08
published: true
labels:
  - StackOverflow
  - Questions
---

<img width="175px" class="rounded float-start pe-4" src="../img/asking-smart-questions/question.jpg">

During my time as a computer engineering student, there were many times where I was frustrated with a problem or piece of code that wasn't working. As someone who used to hate asking questions, this meant hours of trial and error only to find that the problem could have been easily resolved had I talked to a friend or to my professors. Asking questions would have saved me time and effort which could have been spent doing other homework or activities.

Now that I am in my Junior year, I have finally learned that asking questions is a necessary part of the learning process. However, this doesn't mean that you should just ask whatever comes to mind. Most of the time, questions like "where did you find that?" result in sarcastic responses like "did you read the textbook?" or that it was "in the lecture slides." Being able to ask concise and intelligent questions is a crucial learning skill, one that needs to be developed through much practice. The difference between good and bad questions can especially be seen on StackOverflow, an online community where programmers can ask and answer each other's questions.

## Smart Way
In my ICS 314 class, we learned how to ask smart questions through an essay by Eric Raymond found [here](http://www.catb.org/esr/faqs/smart-questions.html). His essay can be summarized into the following four points. First, before asking a question online you should research your issue using the various forums and documents found online. This demonstrates that you have at least tried to fix your problem before asking for more help. Second, when posting to forums like StackOverflow, be sure to use a specific title and to include the appropriate tags otherwise you will be ignored. Third, to write in clear, grammatical language and be explicit about your questions. Finally, being courteous will go a long way, but it should never reach the point that you are groveling for an answer. 

A great example that follows these four guidelines can be seen in the StackOverflow post ["How should I do floating point comparison?"](https://stackoverflow.com/questions/4915462/how-should-i-do-floating-point-comparison). The title is concise but descriptive enough to show what they need help with. They then give an overview of their program which consisted of several if statements containing comparisions between floating point numbers. The user also demonstrated that they already did some research on the unreliability of floating point arithmetic which can be seen in the code below. 

```c#
double a = 1.0 / 3.0;
double b = a + a + a;
if ((3 * a) != b)
  Console.WriteLine("Oh no!");
```

This code will print out "Oh no!" even though it logically makes sense for 3 * a to be equal to b. It also shows that they were able to understand why floating point arithmetic is unreliable for their use cases and why they needed more help. Finally, they were explicit about what they want and their question "How can I reliably compare floating point numbers (less than, greater than, equality)?" was easily identifiable due to the bold font. By creating a descriptive post and asking a smart question, this person was then able to participate in a meaningful discussion and received several different methods to solve their problem. 

## !Smart Way
An example centered about the same topic of floating point comparisions but asked in a bad way can be found in the StackOverflow post [“the problem is from a algorithm problem I do recently,but I can't gain the right answer”](https://stackoverflow.com/questions/59642233/the-problem-is-from-a-algorithm-problem-i-do-recently-but-i-cant-gain-the-right). In addition to the poor grammar, the title makes it unclear what topic this person needs help with. The description then begins with a small piece of code, seen below, with no context on how it was related to their program. 

```c
int k = 12;
float a = 1.0/12;
if ( 1.0 / k == a )
  printf("%d",0);
```

Only after analyzing the rest of their code did I see that their goal was to find combinations of two fractions that added up to the given input. This user then asked the simple question “what’s the reason?” after the output wasn't what they expected. No prior research into solving their problem can be found either. In addition, this person also had an entirely unrelated paragraph of pleasantries which added nothing of material to their post. Finally, they ignored one of the most important practices of not posting code as pictures, since this prevents other users from reproducing your work. By posting an unclear question and ignoring the smart question guidelines, this person warded off any potential help and in the end, did not receive the help they needed. 

## Conclusion
As a programmer, there are bound to be times when we need to seek help from other people. We can either ask friends, teachers, or even look online to sources like StackOverflow for help. However, in order to get the help we need in an efficient and effective way, we first need to be able to ask good questions. Properly describing our problems and needs not only saves time for both sides, but it could also lead to better answers as well. In addition, asking smart questions can create thought-provoking discussions which make the post worth reading for those with similar questions in the future. Everyone benefits from asking good questions, therefore, we should do our best to make all of our questions smart ones.

