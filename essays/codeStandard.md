---
layout: essay
type: essay
title: "Let's reflect on ESLint"
# All dates must be YYYY-MM-DD format!
date: 2026-09-24
published: true
labels:
  - Typescript
  - ESLint
  - VSCode
  - ICS 314
---

<img class="rounded float-start pe-4" src="../img/vscode-logo.png">
<!-- Indeed, I believe some coding standards can actually help you learn a programming language. Do you agree? -->

<!-- After your first week of using ESLint with VSCode, what are your impressions? Are you finding that getting rid of all the ESLint errors is painful, or useful, or both, or something else entirely? -->

<!-- Write an interesting, informative essay on coding standards that addresses some or all of the above questions, or goes in a different direction entirely regarding coding standards. Make sure it provides your personal perspective and useful insights. -->
## First Impressions
I already have experience in VSCode going into this class, but I did not really bother to install any extensions related to coding standards such as ESLint, so I was not sure what to exactly expect in terms of how it may affect my workflow. However, after the first 2 assignments using it, I found it to be disruptive in my usual habits. My tab was made to create 4 spaces by default, and the suggestions would always warn me that it would be expecting 2. That is just one of the more annoying occurrences regarding the implementation of this extension in my assignments. After this of course, I just changed my tab to always indent by 2 spaces instead of 4. 

## Does it help? Or is it nuisance?
Honestly, I would say it is a little bit of both. There were times where ESLint would flag something that I felt did not really matter, like a missing semicolon or a trailing space at the end of a line, and fixing those over and over got tiring pretty quickly. On the other hand, there were a few times where it caught things I would have otherwise missed, such as a variable I declared but never used or a `let` that should have been a `const`. Those small catches made me stop and actually think about why I wrote something the way I did. I do think that as I get more used to the rules, the warnings will show up less often, and I can see it becoming a helpful second pair of eyes looking over my code.

# A little pivot
Thinking about ESLint made me realize that coding standards matter a lot for the people who end up reading your code. When I work on my own projects, I can get away with whatever formatting I feel like that day, since I am the only one who has to understand it. However, once I start working with other people, whether that is in a group project for class or eventually at a job, having everyone follow the same set of rules makes it a lot easier to jump into someone else's code without having to adjust to their personal habits first. In that sense, I can see why a tool like ESLint is worth the small annoyances, because it takes the guesswork out of what "clean" code is supposed to look like for everyone on the team.
