
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

---
---
---
---
---


## Introduction
### What are Commit Scopes?
Commit scopes are optional contextual identifiers used in version control commit messages to specify the component, module, or area of the codebase affected by changes. These scopes have emerged as a vital element in modern development workflows, providing precise location context for modifications within large-scale projects.

A commit scope is a parenthetical qualifier that follows the commit type, identifying the specific section of the codebase being modified. This additional context enables more granular tracking and organization of changes across complex systems.

### Why Should We Use Them?
Commit scopes have become increasingly important in larger projects because they provide immediate location context without requiring code review or file inspection. This contextual information serves several critical purposes:

1. It enables developers to quickly identify relevant changes in their area of responsibility
2. It facilitates more efficient code review by highlighting the system components affected
3. It improves change tracking by categorizing modifications by project area
4. It supports better release management by organizing changes by component

The effort invested in properly scoping commits delivers substantial benefits through improved change navigation and enhanced project organization, particularly in larger codebases with multiple components.

### How Do We Use Them?
Implementing commit scopes requires understanding your project's architecture and establishing consistent naming conventions. While adding scopes is straightforward syntactically, the challenge lies in defining and maintaining meaningful scope boundaries that reflect your project's structure.

```md
<type>(<scope>): <description>
```

While some projects maintain a strict set of predefined scopes aligned with their architecture (e.g., api, ui, core, auth), others allow more flexible scope definitions based on feature areas or team ownership. This customization should align with your project's organization while maintaining clarity and consistency.

## Implementation Guidelines
### Adoption Considerations
### Best Practices
#### Maintain Format Consistency
#### Select Appropriate Scope
#### Document Conventions
