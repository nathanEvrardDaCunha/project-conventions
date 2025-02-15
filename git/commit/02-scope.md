
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
### Why Should We Use Them?
### How Do We Use Them?
## Implementation Guidelines
### Adoption Considerations
### Best Practices
#### Maintain Format Consistency
#### Select Appropriate Scope
#### Document Conventions
