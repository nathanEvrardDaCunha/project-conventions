
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


---
---
---
---
---

## Introduction

### What are Commit Bodies?
Commit bodies are detailed explanations that follow the commit message's first line, providing comprehensive context about the changes being committed. While the commit type, scope, and description offer a quick summary, the body serves as the primary vehicle for communicating the full scope and implications of modifications.

A commit body is a multi-line text block that elaborates on the 'why' and 'how' of changes, separated from the commit's first line by a blank line. This extended content enables developers to document their reasoning, approach, and potential impacts in detail.

### Why Should We Use Them?
Commit bodies have become essential in maintaining comprehensive project documentation because they preserve critical context that might otherwise be lost. This detailed documentation serves several vital purposes:

1. It provides future maintainers with crucial insights into the decision-making process
2. It documents technical decisions and their rationale for historical reference
3. It facilitates more thorough code reviews by explaining complex changes
4. It serves as self-documenting project history for architectural decisions

The time invested in crafting detailed commit bodies yields significant long-term benefits through improved knowledge sharing, more efficient troubleshooting, and enhanced project maintainability.

### How Do We Use Them?
Implementing effective commit bodies requires understanding both formatting conventions and content expectations. While the structure is straightforward, the challenge lies in determining what information to include and how to present it clearly.

```md
<type>(<scope>): <description>

<body>
```

While projects may have specific requirements for body content and formatting, maintaining clear separation between the summary line and body text is a universal convention. Bodies should focus on explaining the rationale behind changes, their impacts, and any essential context for understanding the modifications.

## Implementation Guidelines

### Adoption Considerations
Before implementing detailed commit body conventions, evaluate their applicability to your project's context and team dynamics. While comprehensive documentation benefits most projects, the level of detail and structure should align with your team's needs and capabilities.

Consider the following factors when establishing body guidelines:
- Project complexity and technical depth
- Team communication preferences
- Documentation requirements
- Code review processes
- Long-term maintenance needs

Organizations should adapt these practices to match their specific requirements while maintaining the core principles of clarity and completeness in documentation.

### Best Practices

#### Maintain Format Consistency
Consistency in commit body formatting is essential for maintaining readable and searchable commit histories. Inconsistent formatting can make it difficult to locate and understand important project decisions and changes.

When exceptions to standard formatting become necessary, document them clearly and ensure they remain rare. Establish explicit guidelines for handling special cases while preserving overall consistency.

```md
### Incorrect Format Examples
feat(api): implement user registration

changed the registration process to include email verification also added password strength validation and updated the database schema
> Problem: No line break after description, informal structure

feat(ui): add responsive navigation

- Changed the navigation layout
- Made it responsive
- Fixed some bugs
> Problem: Bullet points without context or explanation

### Correct Format Examples
feat(api): implement user registration

The registration process now includes mandatory email verification to ensure account security and reduce spam accounts. Email verification uses a time-limited token system with a 24-hour expiration.

Implementation details:
1. Added email verification service
2. Implemented password strength validation
3. Updated user schema to include verification status
> Explain and structure important changes

feat(ui): add responsive navigation

This update implements a responsive navigation system to improve mobile user experience. The changes focus on maintaining consistent navigation patterns across all device sizes while optimizing performance.

Key changes:
1. Implemented collapsible menu for mobile viewports
2. Added touch-friendly interaction patterns
3. Optimized animation performance
> Explain and structure important changes
```

#### Write Appropriate Body
Commit bodies should provide comprehensive context while maintaining focus and relevance. Common challenges include:
- Including insufficient context about changes
- Providing excessive or irrelevant details
- Mixing implementation details with impact assessment

Each commit body should present a complete picture of the change while maintaining appropriate detail level. Consider your audience and future maintainers when determining content scope and depth.

```md
### Suboptimal Examples
feat(core): implement payment processing

Changed how payments work.
> Problem: Lacks specific details and context

feat(auth): update password validation

Modified password validation to use regex. The regex pattern is ^(?=.*[A-Za-z])(?=.*\d)[A-Za-z\d]{8,}$ which checks for minimum eight characters, at least one letter and one number. Updated the validation function to use this pattern. Added tests for the new pattern.
> Problem: Focuses on implementation details without explaining rationale

### Optimal Examples
feat(core): implement payment processing

This commit introduces a robust payment processing system designed to handle multiple payment providers while maintaining consistent transaction handling.

The new system addresses several key requirements:
1. Support for multiple payment providers (Stripe, PayPal)
2. Consistent transaction logging across providers
3. Automated receipt generation
4. Failure recovery mechanisms

Security considerations:
- All payment data is encrypted at rest
- PCI compliance measures implemented
- Audit logging enabled for all transactions
> Introduce the changes with detailed explainations and considerations

feat(auth): update password validation

This update strengthens our password security requirements based on NIST Special Publication 800-63B guidelines and recent security audit recommendations.

Key changes:
- Increased minimum password length to 8 characters
- Added complexity requirements (letters + numbers)
- Implemented checks against common password patterns

Impact:
- Existing passwords remain valid
- New passwords must meet updated requirements
- Password change will be required at next login for non-compliant passwords
> Introduce the changes with detailed explainations and considerations
```

#### Document Conventions
Maintaining comprehensive documentation of commit body conventions is crucial for:
- Ensuring consistent communication across teams
- Facilitating effective knowledge transfer
- Supporting project maintenance
- Enabling efficient code review processes

Documentation should address:
- Required and optional body sections
- Formatting requirements and examples
- Context inclusion guidelines
- Team-specific conventions

Your body documentation should provide clear guidance for determining appropriate content and structure. Focus on creating documentation that supports both immediate understanding and long-term project maintenance needs.