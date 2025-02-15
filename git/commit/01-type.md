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