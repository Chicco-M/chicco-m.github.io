---
layout: essay
type: essay
title: "There IS such thing as a stupid question!"
# All dates must be YYYY-MM-DD format!
date: 2026-09-10
published: true
labels:
  - Questions
  - Answers
  - StackOverflow
---

## What exactly is a STUPID question?

According to [Raymond](http://www.catb.org/esr/faqs/smart-questions.html), a "stupid" question isn't stupid just because it is simple or the person asking doesn't know much, it's stupid because of the way it is asked. A question becomes "stupid" when it shows that the person didn't even bother to try to help themselves first, such as not searching through a manual, not googling the error message, and not attempting to debug code on their own before asking AI or a Coworker to do the thinking for them. It's also deemed stupid when the question is vague, like simply posting "it doesn't work, why?" with no context, no code, no error message, nothing that would actually let someone help you efficiently. Basically, a stupid question wastes the time of the person answering because the asker didn't put in any effort of their own.

## What is NOT a stupid question?

A question that shows genuine effort is never stupid, even if the topic is basic or the person asking is a beginner. Raymond makes it clear that if you've actually tried to solve the problem yourself first, researched it, and you're still stuck, then asking online is a valid approach, no matter how "simple" the answer might end up being. What matters is that you did your part of trying to answer your OWN question, you provide enough detail (like the exact error message, what you already tried, or the code itself) so the person helping doesn't have to guess just to understand your situation. In the end, having put in the effort to help yourself is a good habit to have in general.

## An example of a "stupid" question

After sifting through StackOverflow, I've found an ancient relic of a [question](https://stackoverflow.com/questions/3217514/for-loop-not-executing) that was asked 16 years ago, in 2010, that perfectly demonstrates a "stupid" question.

```
Q: For Loop not executing

The formula simply isn't executing. I tried using printf to debug and it printed out 0 for i at the end of the code

#include <stdio.h>

int main()
{
 int i, base, height;
 printf("Lumber  Cross-Sectional   Moment of Section\n");
 printf("Size  Area    Inertia  Modulus\n");
 for (i = 0; i > 35; i++)
 {
  if (i == 6 || i == 12 || i == 18|| i == 24 || i == 30)
  {
   base = base * 2;
   height = 2;
  }
  if (i != 6 || i != 12 || i != 18 || i != 24 || i != 30)
  {
   height = height * 2;
  }
  printf("%d x %d %d  %d   %d \n", base, height, base * height, base * 2 + height); 

 }//for  
 return (0);
}//main

```

In this poster's defense, he at least provided his entire code for people to test and provide meaningful answers. However, they are very vague with what they expect the formula to return, and what their console prints out. Not only that, but they describe that they used printf to debug the code, when in reality, their bug is in their loop condition. (i = 0,; i > 35). The lack of documentation in their efforts to debug allow us to infer that they did not do a simple read through of their code, therefore not have any real effort in answering their own question.

## The "smart" way to ask a question

On the other hand, StackOverflow is usually strict with their guidelines regarding the submissions of people's questions and concerns regarding their code. So, it was easy to find a [smart question](https://stackoverflow.com/questions/65482702/why-is-my-for-loop-not-working-or-is-it-something-else-that-is-causing-problems):

```
Q: My question is not about the result of my function or loop being correct. It is about my loop not working no matter what I do.

What I tried to fix it myself:

I checked if html and JavaScript is linked correctly and if the function is triggered by the button called "Dreieck" at all. To check that I used document.getElementById("ausgabe").innerHTML="x"; right after the loop to see if it is generally working and it worked. That means after clicking on "Dreieck" an x appeared within the div with the id "ausgabe".

Then I thought maybe my loop isn't working because it is not getting any value from the variable "anzahlZeilen". So defined "i" as the following i=5. I actually changed the whole loop to a basic loop:

 for (var i=5; i==10; i++){
 document.getElementById("ausgabe").innerHTML="x";
 }
So when I click on "Dreieck" there should appear an x again, but it didn't.
.
.
.
More code is provided. Click the link to see the full contents of this question.
```
From the way the question is framed where they specifically stated their expectations and correctness of the code gets rid of any ambiguity that the previous question had. We can also see that real effort is already shown from the original poster since they specified the steps they took to debug their own code, especially with their thought process highlighting their approach to their initial solutions. 

This allows the community in StackOverflow to answer the question with the right mindset, even if this question itself may still only be marginally smarter than the previous one.

## Conclusion

With all that being said, there is a lot of value in learning how to ask smart(er) questions. This not only applies to Stack Overflow, but essentially all disciplines of life. By taking a step back to analyze any tough situations one might find themselves in, it might save a lot more time and effort to take a crack at it for a moment rather than typing out the problem and waiting for some unknown amount of time to have someone help you.
