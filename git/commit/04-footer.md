## Introduction
### What are Commit Footers?
Commit footers are structured metadata elements that appear at the end of commit messages, providing standardized additional information about the changes. These footers, separated from the commit body by a blank line, follow a specific key-value format to communicate important metadata such as breaking changes, related issues, or accountability information.

A commit footer consists of one or more lines, each following a "Key: Value" format, where the key identifies the type of metadata being provided. This structured approach ensures that critical information is consistently formatted and easily parseable by both humans and automated tools.

### Why Should We Use Them?
Commit footers have become an integral part of modern version control practices because they provide essential metadata in a standardized, machine-readable format. This structured information serves several critical purposes:

1. It clearly identifies breaking changes that require attention during upgrades
2. It establishes traceable connections between commits and their associated tasks or issues
3. It maintains accountability by documenting responsibility for changes
4. It supports automated tooling for changelog generation and version management

The systematic use of commit footers enhances project maintainability by providing consistent, structured metadata that supports both development workflows and automated processes.

### How Do We Use Them?
Implementing commit footers requires understanding their format conventions and appropriate usage contexts. While the syntax is straightforward, the challenge lies in determining when and how to include specific types of metadata.

```md
<type>(<scope>): <description>

<body>

<footer>
```

While projects may define custom footer types for specific needs, several standard footer conventions (such as breaking changes and issue references) are widely recognized across the industry. These conventional footers should be preferred when applicable to maintain consistency and interoperability between projects and tools.

## Common Commit Footers
### Indicating Breaking Changes
Breaking changes represent modifications that disrupt existing functionality or require updates to dependent code. The breaking change footer provides a standardized way to communicate these significant modifications, ensuring they receive appropriate attention during updates and version management.

Breaking change footers require explicit formatting and comprehensive descriptions to ensure clarity about the impacts and necessary adaptations.

```md
feat(api): implement rate limiting

Introduces API rate limiting to ensure service stability.

BREAKING CHANGE: API calls now require authentication token
BREAKING CHANGE: Requests limited to 1000 per hour per client
```

### Referencing Request
Issue and pull request references establish traceable connections between commits and their corresponding task tracking or version control items. These references support project management processes and maintain clear documentation of change origins.

References can indicate various relationships between commits and requests, such as implementations, fixes, or related changes.

```md
fix(core): resolve payment processing timeout

Updates payment processing timeout handling to prevent transaction failures.

Fixes: #234
Related: #235, #236
See-also: #237
```

### Accounting Responsibility
Responsibility footers document the individuals involved in creating, reviewing, or approving changes. These footers support accountability and provide contact points for future inquiries about specific modifications.

Multiple responsibility footers can be used to document different roles in the change process, creating a clear chain of accountability.

```md
feat(security): implement two-factor authentication

Adds two-factor authentication support with backup codes.

Signed-off-by: David Chen <david.chen@example.com>
Reviewed-by: Sarah Williams <sarah.williams@example.com>
Approved-by: Security Team <security@example.com>
```

## Implementation Guidelines
### Adoption Considerations
Before implementing commit footer conventions, evaluate their applicability to your project's specific context and team dynamics. While structured metadata benefits most projects, the extent and types of footers should align with your project's needs and team capabilities.

Consider the following factors when establishing footer guidelines:
- Project size and complexity
- Team collaboration patterns
- Automation requirements
- Integration with existing tools
- Long-term maintenance needs

Organizations should adapt these practices to match their specific requirements while maintaining the core principles of consistency and clarity in metadata communication.

### Best Practices
#### Maintain Format Consistency
Consistency in footer formatting is essential for maintaining parseable and useful commit metadata. Inconsistent formatting can break automated tools and make it difficult to track important project information.

When exceptions to standard formatting become necessary, document them clearly and ensure they remain rare. Establish explicit guidelines for handling special cases while preserving overall consistency.

```md
### Incorrect Format Examples
BREAKING-CHANGE - Removed legacy API endpoints
> Incorrect delimiter and format

Fixes #123, Related to #124
> Missing proper footer format

Signed by: John Smith
> Incorrect key format

### Correct Format Examples
BREAKING CHANGE: Removed legacy API endpoints
Fixes: #123
Related: #124
Signed-off-by: John Smith <john.smith@example.com>
> Each follows standard footer format conventions
```

#### Inform Breaking Changes
Breaking changes must be clearly communicated to facilitate proper version management and update planning. Common challenges include:
- Inadequate description of impacts
- Unclear migration guidance
- Missing documentation references

Ensure breaking change notices provide comprehensive information about the changes and their implications.

```md
### Suboptimal Breaking Change Examples
BREAKING CHANGE: Changed API
> Lacks specific impact details

BREAKING CHANGE: Updated authentication
See docs for details
> Missing specific guidance

### Optimal Breaking Change Examples
BREAKING CHANGE: API response format changed from XML to JSON
Migration guide: docs/api/migration-v2.md

BREAKING CHANGE: Authentication now requires OAuth2 token
- All existing API keys will be invalidated
- New tokens can be generated at /auth/token
- Migration deadline: 2024-03-01
> Each follows standard breaking changes format conventions
```

#### Reference Existing Request
Issue and pull request references should provide clear traceability between commits and their related tasks. Key considerations include:
- Using correct reference formats
- Maintaining appropriate relationship types
- Providing context when necessary

```md
### Suboptimal Reference Examples
Related to ticket 123
> Incorrect reference format

Fixes: multiple issues
> Missing specific references

### Optimal Reference Examples
Fixes: #123
Related: #124, #125
See-also: organization/repo#456
> Clear and specific references with proper formatting
```

#### Take Responsibility
Responsibility footers should clearly document involvement in changes while maintaining appropriate accountability structures. Important aspects include:
- Using standardized signature formats
- Including appropriate contact information
- Maintaining clear role indication

```md
### Suboptimal Responsibility Examples
By: J. Smith
> Incorrect format and missing details

Reviewed by the team
> Too vague, missing specific accountability

### Optimal Responsibility Examples
Signed-off-by: Jane Smith <jane.smith@example.com>
Reviewed-by: Security Team <security@example.com>
Co-authored-by: John Doe <john.doe@example.com>
> Complete information with proper formatting
```

#### Document Conventions
Maintaining comprehensive documentation of footer conventions is crucial for:
- Ensuring consistent implementation across teams
- Facilitating automated processing
- Supporting project maintenance
- Enabling effective change tracking

Documentation should address:
- Required and optional footer types
- Formatting requirements and examples
- Usage guidelines and contexts
- Team-specific conventions

Your footer documentation should provide clear guidance for selecting and formatting appropriate metadata. Focus on creating documentation that supports both manual composition and automated processing of commit metadata.