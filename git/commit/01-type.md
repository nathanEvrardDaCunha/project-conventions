## Introduction
### What are Commit Types?
Commit types are standardized prefixes used in version control commit messages to categorize the nature of changes being committed. These types have become a fundamental component of modern development workflows, adopted widely across the industry due to their effectiveness in communicating change intent.

A commit type is a predefined identifier that precisely indicates the category of modifications contained within a specific commit, enabling efficient code review and change tracking processes.

### Why Should We Use Them?
Commit types have gained widespread adoption because they provide immediate context about the nature of changes without requiring detailed commit message analysis. This standardized categorization serves multiple purposes:

1. It enables rapid assessment of change impact during code reviews
2. It facilitates automated changelog generation and semantic versioning
3. It improves project maintenance by making commit history more navigable and meaningful

The initial investment in properly categorizing commits yields significant returns through improved collaboration efficiency and enhanced project maintainability.

### How Do We Use Them?
Implementing commit types requires understanding both the standardized conventions and their practical application. While the syntax is straightforward, the challenge lies in accurately categorizing changes to reflect their primary purpose.

```md
<type>: <description>
```

While industry standards like Conventional Commits provide a well-defined set of commit types (e.g., feat, fix, docs, style, refactor), many teams extend these baseline conventions with additional types specific to their workflow needs. This customization should build upon, rather than replace, established conventions to maintain interoperability and clarity.

## Common Commit Types
### Industry-Standard Commit Types
The following commit types represent the foundational elements of semantic commit messages, widely recognized and adopted across the software development industry. These types form the core vocabulary for describing code changes in version control systems.

#### `feat`
Indicates the introduction of new functionality or features intended for end users. This type specifically denotes additions that enhance the application's capabilities from a user perspective.

```md
feat: implement celsius to fahrenheit conversion feature
feat: implement login authentification page for users
```

#### `fix`
Designates corrections to bugs or runtime issues that directly impact user experience. This type should be reserved for changes that address functional defects in the application's behavior.

```md
fix: resolve calculator division by zero error
fix: patch celsius to fahrenheit conversion edge case
```

#### `docs`
Encompasses all documentation-related modifications, including inline code comments, README files, API documentation, and development guidelines. Documentation changes should be committed separately from code changes to maintain clear revision history.

```md
docs: update semantic commit guidelines with examples
docs: create project guideline about semantic commit
```

#### `style`
Represents changes to code formatting, white space, and other stylistic elements that do not affect runtime behavior. These changes typically align with coding standards and style guides without modifying functionality.

```md
style: implement consistent double quote usage across codebase
style: format user creation service with prettier formater
```

#### `test`
Relates to the addition, modification, or removal of test cases and testing infrastructure. This type focuses exclusively on testing-related changes without altering production code behavior.

```md
test: implement unit tests for password validation edge cases
test: delete integration test about obsolete chat moderation
```

#### `refactor`
Indicates code modifications that improve non-functional attributes such as readability, modularity, or performance, while preserving existing functionality. These changes restructure implementation details without altering the external behavior.

```md
refactor: decompose user validation logic into separate services
refactor: rewrite data calculation functions as pure functions
```

#### `chore`
Encompasses maintenance tasks, dependency updates, and infrastructure changes that support development processes without directly affecting application features or business logic.

```md
chore: upgrade prettier dependency to version 5.9
chore: create automatic daily linter report for javascript files 
```

### Extended Commit Types
While the core commit types cover most development scenarios, the following extended types address specific aspects of software development. When implementing these types, document them clearly in your project's contribution guidelines to ensure consistent usage across the team.

#### `perf`
Denotes changes specifically focused on performance optimization, whether through code refactoring, algorithm improvements, or resource utilization enhancements. This type should be used exclusively for performance-related modifications that can be measured and verified.

```md
perf: optimize image compression algorithm for mobile devices
perf: replace linear user search by divide and conquer algorithm
```

#### `build`
Identifies changes to the project's build system, compilation processes, or dependency management configurations. These modifications typically affect development workflows without impacting the production runtime environment.

```md
build: migrate webpack configuration to version 5.0.0
build: download vitest package from npm for testing purpose
```

#### `security`
Addresses security vulnerabilities, implements security measures, or updates security-related dependencies. This type should be used judiciously and typically requires careful consideration of deployment timing and impact.

```md
security: patch bcrypt dependency to address CVE-2023-xxxx
security: update jest package to newer version to prevent zero-day
```

## Implementation Guidelines
### Adoption Considerations
Before implementing semantic commit conventions, carefully evaluate their applicability to your project's specific context and team dynamics. While these practices represent industry standards, their adoption should align with your project's needs and team capabilities.

Consider the following factors when evaluating these guidelines:
- Project scale and complexity
- Team size and experience level
- Existing workflows and processes
- Long-term maintenance requirements

Organizations should customize these practices to match their specific requirements while maintaining the core principles of clarity and consistency.

### Best Practices
#### Maintain Format Consistency
Consistency in commit message formatting is fundamental to achieving the benefits of semantic commits. Arbitrary or selective application of conventions diminishes their value and can lead to confusion.

While exceptions may occasionally be necessary, they should be rare and well-documented. Establish clear protocols for handling edge cases while maintaining overall consistency.

```md
### Incorrect Format Examples
implement unit tests for password validation edge cases 
> Missing commit type prefix

[security] 
> Incorrect type format and missing description

build // migrate webpack configuration to version 5.0.0
> Incorrect separator usage

### Correct Format Examples
test: implement unit tests for password validation edge cases
security: patch bcrypt dependency to address CVE-2023-xxxx
build: migrate webpack configuration to version 5.0.0
> Each follows the standard format: <type>: <description>
```

#### Select Appropriate Types and Descriptions
Commit messages should precisely communicate change intent through careful selection of commit types and clear descriptions. Common pitfalls include:
- Selecting overly generic types
- Writing vague or overloaded descriptions
- Combining unrelated changes in a single commit

Each commit should represent a logical unit of change. While it's acceptable to include multiple related modifications, they should serve a common purpose. Use the presence of conjunctions ("and") in descriptions as an indicator that your commit might need division.

```md
### Suboptimal Examples
test: add tests for user register form
> Lacks specificity about test type and scope

feat:
> Missing description entirely

feat: patch divide by zero edge case calculation in my utils files
> Incorrect type selection for a bug fix

### Optimal Examples
test: add unit tests for user register form validation functions
feat: add admin login form with jwt token validation
fix: patch divide by zero edge case calculation in my utils files
> Each combines appropriate type with specific, focused description
```

#### Document Conventions
Maintaining comprehensive documentation of your commit message conventions is essential for:
- Ensuring consistent implementation across team members
- Facilitating onboarding of new contributors
- Supporting long-term project maintenance
- Enabling effective code review processes

Documentation should include:
- Adopted commit types and their definitions
- Format requirements and examples
- Exception handling procedures
- Team-specific customizations

While documentation quality can vary, ensure it provides clear guidance for both current team members and future contributors. Focus on clarity and accessibility over stylistic perfection.