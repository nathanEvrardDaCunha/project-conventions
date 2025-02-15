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




---
---
---
---
---

## Introduction
### What are Commit Footers?
### Why Should We Use Them?
### How Do We Use Them?
## Common Commit Footers
### Indicating Breaking Changes
### Referencing Request
### Blaming Responsability
## Implementation Guidelines
### Adoption Considerations
### Best Practices
#### Maintain Format Consistency
#### Inform Breaking Changes
#### Reference Existing Request
#### Take Responsability
#### Document Conventions