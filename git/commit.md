# Git Commit

## 1. Overview

This file serves as a curated collection of git commit conventions and best practices gathered from various online resources and articles. It provides a centralized reference point for developers seeking guidance on commit organization and readability.

## 2. Purpose

The primary goal of this collection is to aggregate useful commit practices and conventions in one accessible location. While these guidelines may not be universally applicable, they offer valuable insights for developers looking to improve their commit quality.

## 3. Introduction to Semantic Commit

<!-- TODO: Make this section more formal and professional in tone -->
<!-- IDEA: It might be possible to make it tool agnostic but would need to rewrite things other than for git and for the majority of versioning tools. -->

### 3.1. Why do we write Git Semantic Commit ?

Git is easy to grasp and use. But the way you write code for your hooby project, small professional project or large codebase can vary considerably. Because of many factor like project and team size, it become increasingly difficult to make meaningfull commit following guideline everyone understand. 

Not only that, but keeping track of which commit make the cut to the new version of the application (related to Semantic versioning) ca nbe tricky without proper guidelines or commonly adopted practices accros the industry.

That where Git Semantic Commit appear.

### 3.2. What is Git Semantic Commit ?

Git Semantic Commit (complementary yet distinct from Semantic Versioning concept) are common practices helping team and individuals to write more meaningful commit by including relevant element like type, description, scope, body, footer... 

Thanks to those, it become easier for teams to quickly navigate through the entire repository history of any project and quickly access the commit they are searching.

On top of that, thanks to some automation tool, writing commit following a clear format can help us automatically know what to include or exclude from releases of our project, especially when the new version include breaking change for the older one.

### 3.3. How do we use Git Semantic Commit ?

To write semantic commit, you just need to decide of the guidelines you and your team wish to use in your project and follow them as rigourously as possible.

Not every suggesstion in the following part below are to be implemented, nor can they be followed every single time. but while there are always cases where one need to bypass the rules they set themselves, we recommend you to abide to it as much as possible.

## 4. Conventions 

### 4.1. Mandatory semantic commit template
<!-- TODO: Refine explanation to be more formal, detailed and professional -->

The type, which will we see in detail below, guide us to what is the main purpose of the change commited.

The description give us additional but mandatory context about what has been changed.

```md
# Skeleton of mandatory commit

(type): (description)

> fix: patch calculator divide by zero edge case
```

### 4.2. Importance of Type

#### 4.2.1. Popular and commonly adopted commit types
<!-- TODO: Refine explanation to be more formal, detailed and professional -->
Most popular and adopted semantic types

```md
# Most popular commit types for semantic

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

#### 4.2.2 Popular but uncommun commit types

<!-- TODO: Refine explanation to be more formal, detailed and professional -->
Less common but as important semantic types

```md
# Less popular but important commit types for semantic

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

### 4.3. Importance of Scope
<!-- TODO: Refine explanation to be more formal, detailed and professional -->
Scope allow you to explicitly tell which part of your code does your commit affect. 
If it is too difficult to attribute only one part to your commit or the changes are globals, you can left it empty.
Scope are optional.

```md
# Skeleton of commit with optional scope

<type>(scope): <description>

> refactor(auth): rename username validation function
```

### 4.4. Importance of Body
<!-- TODO: Refine explanation to be more formal, detailed and professional -->
The body of the commit allow developer to indicate to others exactly what applying it will do. It's like telling to other what was here before and what will be done after applying it. The body is optional but recommended in general especially if you don't work alone on your project.

```md
# Skeleton of commit with optional body

<type>(<scope>): <description>

(body)

> docs(commit): add commit example to body section
>
> - Add commit example with optional body for better user comprehension.
```

### 4.5. Importance of Footer
<!-- TODO: Refine explanation to be more formal, detailed and professional -->
The footer allow the developer to include optional but important additional and more flexbile information distinct from the change written in the body. 
This information can include breaking changes forsakin the possibility to retrograde later ; if the commit is related to a pull request ; who review the commit ; the references and many more...
On top of that, you can have multiple footers per commit.

```md
# Skeleton of commit with optional body

<type>(<scope>): <description>

<body>

(footer(s))

> security(module): audit and update jest dependency to v15.9
>
> - Update jest dependency to fix critical vulnerability in test process.
>
> BREAKING CHANGE:
> - Support of CommonJs import for Jest don't work anymore.
>
> Reviewed by: John DOE
> Closes #145
```

#### 4.5.1. Understanding BREAKING CHANGE

#### 4.5.2. Understanding Review and Reference

## 5. Practices

### 5.1. Start your commit with type

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

