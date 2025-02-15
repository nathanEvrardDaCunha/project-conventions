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






## 5. Practices









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