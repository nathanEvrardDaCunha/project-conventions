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
# Skeleton of commit with optional footer(s)

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
> Review: John DOE
> Reference: #167
```

#### 4.5.1. Understanding BREAKING CHANGE
<!-- TODO: Refine explanation to be more formal, detailed and professional -->
As a team player, wetheryou work with a team or have client using your products and services into their own, it's important to clearly inform people about the potential or observed consequences of any of your commit.
That why including BREAKING CHANGE allow to draw attention to the fact that this commit could or will break some part of the prior codebases necessiting time and effort to update and refactor a new approach. 

```md
# Skeleton of commit with optional BREAKING CHANGE footer

<type>(<scope>): <description>

<body>

(footer with BREAKING CHANGE)

> security(module): audit and update jest dependency to v15.9
>
> - Update jest dependency to fix critical vulnerability in test process.
>
> BREAKING CHANGE:
> - Support of CommonJs import for Jest don't work anymore.
```

#### 4.5.2. Understanding Review and Reference
<!-- TODO: Refine explanation to be more formal, detailed and professional -->
Tracking things is a daily tasks of any developer, especially when they work with others peoples, especially their respectives issues.

One way to clearly inform people about what need to be keep track of and what is already done is through the use of Review and Reference.

```md
# Skeleton of commit with optional Review and Reference footer

<type>(<scope>): <description>

<body>

(footer with Review and/or Reference)

> fix(weather-form): patch new zealand middle space input error
>
> - Patch the weather city input form to accept middle space between city name.
>
> Review: EVRARD-DA CUNHA Nathan
> Reference: #196
```

## 5. Practices

### 5.1. Always include relevant type at the start
<!-- TODO: Refine explanation to be more formal, detailed and professional -->
Including the relevant type at the start of your commit is one of the best way to quickly indicate to others developers what you did so they can quickly navigate and find what they need.

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

### 5.2. Include relevant scope whenever possible
<!-- TODO: Refine explanation to be more formal, detailed and professional -->
Including the relevant scope whenever possible is a powerful way to clearly make others understand where there is change enhancing their navigation capabilities and conflict solving skills.

```md
# Examples - Good practice

We understand where things changed.
> feat(user-statistic): add statistic display in user profil

We understand where things changed.
> test(calculator): delete obsolete sum function test

# Examples - Bad practice

We hesitate where are the changes.
> security: add data form validation with trim and hash  

We hesitate where are the changes.
> test: delete profil statistic display function test
```

### 5.3. Always include relevant body
<!-- TODO: Refine explanation to be more formal, detailed and professional -->
The body can always be part of your commit so it's a good idea to always write one. it hugely enhance the capabilities of your peers to understand the consequence of your action and work before applying or using it.

```md
# Examples - Good practice

We understand what will happen.
> docs(commit): add scope recommendation in practice section
>
> - Add scope recommendation part in practice section.
>
> - Add introduction to scope recommendation explaining it's purpose.
>
> - Add example to scope recommendation to enhance user understanding.

# Examples - Bad practice

We can only guess what will happen but not how much.
> docs(commit): add scope recommendation in practice section 
```

### 5.4. Include relevant informations footer when necessarry
<!-- TODO: Refine explanation to be more formal, detailed and professional -->
When your commit contain important information notably about changes breaking incompatible with older version, an already existing issue, request... Always add it to inform your peers.
If you've nothing that could be included in the footer, don't add one.

Also, only include usefull information. If the only important thing about it is it close an existing request, only include that.
If there is no existing reference but your commit is not retrogradable, only mention this.

```md
# Examples - Good practice

We understand the consequences, the causes and the one who approuved it.
> security(module): audit and update jest dependency to v15.9
>
> - Update jest dependency to fix critical vulnerability in test process.
>
> BREAKING CHANGE:
> - Support of CommonJs import for Jest don't work anymore.
>
> Review: John DOE
> Reference: #167

# Examples - Bad practice

We have no idea what consequences will this bring, neither why was this done nor who will take responsability.
> security(module): audit and update jest dependency to v15.9
```

### 5.5. Always be consistent in your formating even with imperfect guideline
<!-- TODO: Refine explanation to be more formal, detailed and professional -->
One of the most important thing in any project, no matter the subject, is to be consistent. Nothing is perfect, not your rules nor those guidelines so it's okay to not be the best or have the exception sometime.

But exception doesn't justify not following throughtfully your own rules. One of the worst thing, no matter who write the code, can do is to be inconsistent.

You can iterate and evolve your rules and guidelines over time, but you should always have a standardize way to do things, especially when it allow you to communicate with others.

For your commit consistency, we recommend you think about the others practices sections you want to include. On top of them, also think and define:
- How does I separate each line (generally we seperate be empty line).
- How do we list things in the body (generally we start with a hyphen).
- How do I write my sentences (generally we write in present tense).
- How much is my sentence max length (generally 70 to 80 characters).
- How big or small my commit need to be (generally 1 to 3 small things).

```md
# Examples - Good practice

We can quickly understand the commit content because we know by habit how it's formated even if it can miss important informations.
> security(module): audit and update jest dependency to v15.9
>
> - Update jest dependency to fix critical vulnerability in test process.
>
> BREAKING CHANGE:
> - Support of CommonJs import for Jest don't work anymore.
>
> Review: John DOE
> Reference: #167

# Examples - Bad practice

We loss too much time trying to interpret not only the content but the unpredictable format of this hazardous commit.
> #167 - [security] - audit and update jest dependency to v15.9 (module)
> 
> /!\ Support of CommonJs import for Jest don't work anymore. /!\
>
> 
> John Doe reviewed this commit and approve
> Update jest dependency to fix critical vulnerability in test process.
```

## Conclusion
<!-- TODO: Refine explanation to be more formal, detailed and professional -->
Despite the wide adoption and use of versioning, many overlook the impact predictable and meaningfull commit can have over the productivity of individual or entire team.

Contrary to what people could think, semantic commit doesn't slow developers in their iterative development process. It push them to communicate more clearly by structuring and formating their work in a predictable and clear manner.
This help them avoid wasting huge amount of time when trying to search or understand something in the project history, if they succeed at all. All this by taking just a few more seconds to make sure they give proper meaning to their commit.  

### Further Reading
<!-- TODO: Refine explanation to be more formal, detailed and professional -->
For those you want to dig deeper into the subject, you can read thoses next articles explaining each their valuable opinion:
- https://gist.github.com/joshbuchea/6f47e86d2510bce28f8e7f42ae84c716
- https://sparkbox.com/foundry/semantic_commit_messages
- https://karma-runner.github.io/1.0/dev/git-commit-msg.html
- https://365git.tumblr.com/post/3308646748/writing-git-commit-messages
- https://karma-runner.github.io/1.0/dev/git-commit-msg.html
- https://www.conventionalcommits.org/en/v1.0.0/