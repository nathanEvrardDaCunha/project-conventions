# Git Commit

## Overview

This file serves as a curated collection of git commit conventions and best practices gathered from various online resources and articles. It provides a centralized reference point for developers seeking guidance on commit organization and readability.

## Purpose

The primary goal of this collection is to aggregate useful commit practices and conventions in one accessible location. While these guidelines may not be universally applicable, they offer valuable insights for developers looking to improve their commit quality.

## Conventions and Practices

### Prefer to use mainstream commit over custom one

```md
# Features - `feat:`
New feature users can interact with.
> feat: add celsius to fahrenheit unit switch

# Bug Fixes - `fix:`
Fix any bug and code issues affecting production.
> fix: patch calculator divide by zero edge case

# Documentations - `docs:`
Change to project documentation or comments.
> docs: update project semantic commit guideline

# Code Style - `style:`
Change that doesn't affect code behavior.
> style: add double commas rule to formater

# Test - `test:`
Creation and modification of test covering code.
> test: delete unit test for obsolete username validation

# Refactor - `refactor:`
Code modification that doesn't change feature nor bug.
> refactor: rename public folder to assets

# Maintenance - `chore:`
Regular system tasks and dependance maintenance.
> chore: update prettier to version 5.9

# Performance - `perf:`
Change that improve application performance.
> perf: optimize automatic images compression for mobile

# Build - `build:`
Change to build system or external dependencies.
> build: upgrade webpack to version 5.0.0

# Security - `security:`
Addressing security issues or vulnerabilities
> security: update bcrypt to patch password hashing vulnerability
```


### Prefer start your commit with the relevant prefix

```md
# Examples - Good practice
We understand what is added and why.
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

