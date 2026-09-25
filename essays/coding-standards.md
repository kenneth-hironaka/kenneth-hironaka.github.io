---
layout: essay
type: essay
title: "When Your Code Runs but Has 50 Errors: My Take on Coding Standards"
# All dates must be YYYY-MM-DD format!
date: 2026-09-24
published: true
labels:
  - Coding Standards
  - ESLint
  - VSCode
---

<img width="150px" class="rounded float-start pe-4" src="../img/coding-standards/eslint.png">

In the past few weeks in my software engineering class I've been reintroduced to an old friend: linting tools. In case you didn't know, a linter is a static code analysis tool, which means it is a tool that analyses your code without running it and checks for any syntax errors or other rules that it is set to look for. I call it an old friend because my first introduction to linting tools was a few years ago in my object-oriented programming class. Even though it was a different tool than ESLint which is purely for TypeScript/JavaScript (the other class used C/C++), the overall function of the tool was very familiar and reminded me of my past struggles with the linting tool.

# Mixed Feelings

Because of these past struggles, I initially hesitated on whether to call it an old *friend* or an old *enemy*. However, looking back on it now without the stress of having an assignment due with the linter giving me 50 errors on my code that runs perfectly fine, I do see the value in these tools in upholding coding standards. I realized that in codebases with code written and shared with multiple people, these tools can check every line of code to help the overall codebase have a consistent style, instead of every program or function looking different. 

# My Gripes with Linters

While these reasons are valid in the context of a codebase shared by multiple people, the only times I have used them are in my programming classes where the projects were all individual. Unfortunately, while I do realize these classes are introducing linters for when I do encounter them in group settings, they were more of an annoyance than anything, as there was no one else that would be writing code as a part of my projects, and my projects were all small in scope, leaving me to only code a few programs per project if not just one. These circumstances therefore removed a lot of the benefits that linters have.

# The Real Test of Linters

As my software engineering class will be the first time I will use a linter (ESLint) to uphold coding standards in a group project where we will be writing several different programs, I am interested to see how my opinion of linters change. Although the constant errors with things like having a space before an opening curly brace can result in a program having many errors while running fine, I believe these little things will make a difference with a large codebase. 

Will I swear by linters? Will I swear off linters? Only time and experience will tell. 
