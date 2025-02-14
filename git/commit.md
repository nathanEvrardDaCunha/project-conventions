# Git Commit

## Overview

This file serves as a curated collection of git commit conventions and best practices gathered from various online resources and articles. It provides a centralized reference point for developers seeking guidance on commit organization and readability.

## Purpose

The primary goal of this collection is to aggregate useful commit practices and conventions in one accessible location. While these guidelines may not be universally applicable, they offer valuable insights for developers looking to improve their commit quality.

## Introduction to Semantic Commit

<!-- TODO: Make this section more formal and professional in tone -->
<!-- IDEA: It might be possible to make it tool agnostic but would need to rewrite things other than for git and for the majority of versioning tools. -->

### Why do we write Git Semantic Commit ?

Git is easy to grasp and use. But the way you write code for your hooby project, small professional project or large codebase can vary considerably. Because of many factor like project and team size, it become increasingly difficult to make meaningfull commit following guideline everyone understand. 

Not only that, but keeping track of which commit make the cut to the new version of the application (related to Semantic versioning) ca nbe tricky without proper guidelines or commonly adopted practices accros the industry.

That where Git Semantic Commit appear.

### What is Git Semantic Commit ?

Git Semantic Commit (complementary yet distinct from Semantic Versioning concept) are common practices helping team and individuals to write more meaningful commit by including relevant element like prefix, description, scope, body, footer... 

Thanks to those, it become easier for teams to quickly navigate through the entire repository history of any project and quickly access the commit they are searching.

On top of that, thanks to some automation tool, writing commit following a clear format can help us automatically know what to include or exclude from releases of our project, especially when the new version include breaking change for the older one.

### How do we use Git Semantic Commit ?

To write semantic commit, you just need to decide of the guidelines you and your team wish to use in your project and follow them as rigourously as possible.

Not every suggesstion in the following part below are to be implemented, nor can they be followed every single time. but while there are always cases where one need to bypass the rules they set themselves, we recommend you to abide to it as much as possible.

## Conventions and Practices

### Better using mainstream template over custom one

```md
# Popular template used by the majority of professional

fix: patch calculator divide by zero edge case
^--^  ^-------------------------------------^
|     |
|     +-> Summary in present tense.
|
+-------> Type: feat, fix, refactor (see below...).
```

### Better using mainstream commit over custom one

<!-- TODO: Refine explanation to be more formal, detailed and professional -->
Most common semantic prefix

```md
# Most popular commit prefix for semantic

## Features - `feat:`
New feature users can interact with.
> feat: add celsius to fahrenheit unit switch

## Bug Fixes - `fix:`
Fix any bug and code issues affecting production.
> fix: patch calculator divide by zero edge case

## Documentations - `docs:`
Change to project documentation or comments.
> docs: update project semantic commit guideline

## Code Style - `style:`
Change that doesn't affect code behavior.
> style: add double commas rule to formater

## Test - `test:`
Creation and modification of test covering code.
> test: delete unit test for obsolete username validation

## Refactor - `refactor:`
Code modification that doesn't change feature nor bug.
> refactor: rename public folder to assets

## Maintenance - `chore:`
Regular system tasks and dependance maintenance.
> chore: update prettier to version 5.9
```

<!-- TODO: Refine explanation to be more formal, detailed and professional -->
Less common but as important semantic prefix

```md
# Less popular but important commit prefix for semantic

## Performance - `perf:`
Change that improve application performance.
> perf: optimize automatic images compression for mobile

## Build - `build:`
Change to build system or external dependencies.
> build: upgrade webpack to version 5.0.0

## Security - `security:`
Addressing security issues or vulnerabilities
> security: update bcrypt to patch dependency vulnerability
```

### Better starting your commit with the relevant prefix

```md
# Examples - Good practice
We understand what is added and who.
> feat: add account deletion for free user

We understand what is updated and where.
> test: update test to get account information

We understand what is rewriten and how.
> refactor: rewrite billing system to singleton pattern

# Examples - Bad practice
We hesitate between security or bug fix.
> patch validation dependancies vulnerabilities

We hesitate between performance or style.
> remove css normalize file space and line break  

We hesitate between build or chore.
> add automatic update for newest prettier version
```

---

