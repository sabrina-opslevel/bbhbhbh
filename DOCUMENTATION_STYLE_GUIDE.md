# Documentation Style Guide

This guide establishes consistent documentation writing practices across all repositories in the organization.

## Table of Contents

- [Overview](#overview)
- [Tone and Voice](#tone-and-voice)
- [Document Structure](#document-structure)
- [Formatting Conventions](#formatting-conventions)
- [README Files](#readme-files)
- [Code Comments](#code-comments)
- [API Documentation](#api-documentation)
- [Markdown Standards](#markdown-standards)
- [Language and Grammar](#language-and-grammar)
- [Examples and Code Samples](#examples-and-code-samples)

## Overview

### Goals

- **Consistency**: Maintain uniform documentation across all repositories
- **Clarity**: Make documentation easy to understand for all audiences
- **Maintainability**: Keep documentation in sync with code changes
- **Accessibility**: Ensure documentation is welcoming to all skill levels

### Principles

1. Write for your audience
2. Be clear and concise
3. Use active voice
4. Provide examples
5. Keep it up-to-date
6. Make it scannable

## Tone and Voice

### General Guidelines

- **Professional yet approachable**: Write in a friendly, conversational tone while maintaining professionalism
- **Active voice**: Prefer "Use this command" over "This command can be used"
- **Present tense**: Write "This function returns" not "This function will return"
- **Direct address**: Use "you" when addressing the reader
- **Positive language**: Focus on what to do rather than what not to do

### Examples

✅ **Good**:

```markdown
Use the `install` command to add dependencies to your project.
```

❌ **Avoid**:

```markdown
Dependencies can be added to projects through the use of the install command.
```

## Document Structure

### Standard Sections

Every README should include these sections in order:

1. **Title and Description**
   - Project name as H1 header
   - Brief one-line description
   - Badges (build status, version, etc.) if applicable

2. **Purpose** (or "About")
   - Explain what the project does
   - Describe the problem it solves
   - Target audience

3. **Table of Contents** (for longer docs)
   - Auto-generated or manual
   - Link to major sections

4. **Installation**
   - Prerequisites
   - Installation steps
   - Platform-specific instructions if needed

5. **Usage**
   - Basic examples
   - Common use cases
   - Configuration options

6. **Contributing**
   - Link to CONTRIBUTING.md
   - Quick contribution overview

7. **Changelog**
   - Link to CHANGELOG.md

8. **License**
   - License type or link to LICENSE file

### Optional Sections

Include these as needed:

- **Features**: Key capabilities
- **Architecture**: System design overview
- **API Reference**: Link to detailed API docs
- **Troubleshooting**: Common issues and solutions
- **FAQ**: Frequently asked questions
- **Acknowledgments**: Credits and thanks

## Formatting Conventions

### Headers

- Use ATX-style headers (`#` symbols)
- Include space after `#`: `# Header` not `#Header`
- Use sentence case: "Installation guide" not "Installation Guide"
- Only one H1 (`#`) per document (the title)
- Don't skip header levels (H1 → H2 → H3, not H1 → H3)

```markdown
# Main Title (H1)

## Section (H2)

### Subsection (H3)

#### Minor Section (H4)
```

### Lists

- Use `-` for unordered lists
- Use `1.` for ordered lists (numbers will auto-increment)
- Indent nested lists with 2 spaces
- Add blank line before and after lists

```markdown
- First item
- Second item
  - Nested item
  - Another nested item
- Third item

1. First step
2. Second step
3. Third step
```

### Code

- Use backticks for inline code: `` `code` ``
- Use fenced code blocks with language identifiers
- Include language for syntax highlighting

````markdown
Inline code: Use the `npm install` command.

Code block:
```javascript
function greet(name) {
  return `Hello, ${name}!`;
}
```
````

### Links

- Use reference-style links for repeated URLs
- Use descriptive link text, not "click here"

```markdown
Check the [documentation](https://example.com/docs) for details.

Or with references:
See the [official docs][docs] and [API reference][api].

[docs]: https://example.com/docs
[api]: https://example.com/api
```

### Emphasis

- Use `**bold**` for strong emphasis (UI elements, important terms)
- Use `*italic*` for slight emphasis
- Don't use underscores for emphasis in Markdown

```markdown
**Important**: This is critical information.

Configure the *optional* timeout parameter.
```

## README Files

### Template Structure

```markdown
# Project Name

Brief description of what this project does.

## Purpose

Detailed explanation of the project's purpose and goals.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)

## Installation

### Prerequisites

- Requirement 1
- Requirement 2

### Setup

Step-by-step installation instructions.

## Usage

Basic usage examples with code samples.

## Contributing

Link to CONTRIBUTING.md and brief overview.

## License

License information.
```

### Best Practices

- **Keep it concise**: Aim for 200-500 words for main sections
- **Start with essentials**: Most important info at the top
- **Use examples**: Show, don't just tell
- **Update regularly**: Keep in sync with code changes
- **Test instructions**: Verify that setup steps actually work

## Code Comments

### When to Comment

**Do comment**:

- Complex algorithms or business logic
- Non-obvious decisions or trade-offs
- Public APIs and functions
- Workarounds or hacks (with explanation)
- TODOs with context

**Don't comment**:

- Obvious code that's self-explanatory
- Redundant information already in function name
- Outdated information (update or remove)
- Commented-out code (use version control instead)

### Comment Style Guidelines

**Python**:

```python
def calculate_discount(price, customer_type):
    """Calculate discount based on customer type.
    
    Args:
        price (float): Original price before discount
        customer_type (str): Customer category ('regular', 'premium', 'vip')
    
    Returns:
        float: Discounted price
    
    Raises:
        ValueError: If customer_type is invalid
    """
    # VIP customers get 20% discount due to loyalty program
    if customer_type == 'vip':
        return price * 0.8
    # Premium customers get 10% discount
    elif customer_type == 'premium':
        return price * 0.9
    return price
```

**JavaScript/TypeScript** (JSDoc):

```javascript
/**
 * Calculate discount based on customer type.
 * 
 * @param {number} price - Original price before discount
 * @param {string} customerType - Customer category ('regular', 'premium', 'vip')
 * @returns {number} Discounted price
 * @throws {Error} If customerType is invalid
 */
function calculateDiscount(price, customerType) {
  // VIP customers get 20% discount due to loyalty program
  if (customerType === 'vip') {
    return price * 0.8;
  }
  return price;
}
```

**Java** (Javadoc):

```java
/**
 * Calculate discount based on customer type.
 * 
 * @param price Original price before discount
 * @param customerType Customer category ('regular', 'premium', 'vip')
 * @return Discounted price
 * @throws IllegalArgumentException If customerType is invalid
 */
public double calculateDiscount(double price, String customerType) {
    // VIP customers get 20% discount due to loyalty program
    if ("vip".equals(customerType)) {
        return price * 0.8;
    }
    return price;
}
```

**Go**:

```go
// calculateDiscount calculates discount based on customer type.
// 
// Parameters:
//   price: Original price before discount
//   customerType: Customer category ('regular', 'premium', 'vip')
// 
// Returns the discounted price or an error if customerType is invalid.
func calculateDiscount(price float64, customerType string) (float64, error) {
    // VIP customers get 20% discount due to loyalty program
    if customerType == "vip" {
        return price * 0.8, nil
    }
    return price, nil
}
```

## API Documentation

### Documentation Requirements

For all public APIs, document:

1. **Purpose**: What the function/method does
2. **Parameters**: Name, type, description, required/optional
3. **Return value**: Type and description
4. **Errors/Exceptions**: What can go wrong
5. **Examples**: Basic usage example
6. **Side effects**: Any state changes or I/O operations

### Example Structure

````markdown
### `functionName(param1, param2)`

Brief description of what the function does.

#### Parameters

- `param1` (type, required): Description of first parameter
- `param2` (type, optional): Description of second parameter, defaults to X

#### Returns

`ReturnType`: Description of return value

#### Throws

- `ErrorType1`: When this error occurs
- `ErrorType2`: When this error occurs

#### Example

```javascript
const result = functionName('value1', 'value2');
console.log(result); // Expected output
```

#### Notes

Any additional information, caveats, or performance considerations.
````

## Markdown Standards

### Linting Rules

We use markdownlint to enforce consistent Markdown formatting. Key rules:

- **MD001**: Header levels increment by one
- **MD003**: Header style (ATX: `#`)
- **MD004**: List style (dash: `-`)
- **MD013**: Line length limit (120 characters, flexible)
- **MD022**: Headers surrounded by blank lines
- **MD025**: Single H1 per document
- **MD031**: Fenced code blocks surrounded by blank lines
- **MD040**: Code blocks must specify language

### File Naming

- Use lowercase with hyphens: `setup-guide.md`
- Use `.md` extension for Markdown files
- README, CONTRIBUTING, CHANGELOG in uppercase

## Language and Grammar

### Grammar Rules

- **Capitalize proper nouns**: GitHub, Python, JavaScript
- **Use Oxford comma**: "apples, oranges, and bananas"
- **Spell out acronyms** on first use: "Application Programming Interface (API)"
- **Avoid jargon** unless necessary and explained
- **Use contractions sparingly** in formal documentation

### Terminology

Be consistent with technical terms:

✅ **Correct**:

- **filename** (one word)
- **email** (not e-mail)
- **setup** (noun/adjective), **set up** (verb)
- **login** (noun/adjective), **log in** (verb)
- **JavaScript** (capital S)
- **Node.js** (with .js)

### Writing Style

- **Be concise**: Remove unnecessary words
- **Use parallel structure**: In lists, use consistent grammatical form
- **Avoid redundancy**: Don't repeat information unnecessarily
- **Use simple words**: "use" instead of "utilize"

## Examples and Code Samples

### Writing Good Examples

- **Self-contained**: Examples should work on their own
- **Realistic**: Show real-world usage, not contrived examples
- **Annotated**: Explain what the code does
- **Tested**: Verify examples actually work
- **Complete**: Include necessary imports and setup

### Example Template

````markdown
## Example: User Authentication

This example shows how to authenticate a user:

```javascript
// Import required modules
const auth = require('./auth');

// Create authentication credentials
const credentials = {
  username: 'user@example.com',
  password: 'securePassword123'
};

// Authenticate user
auth.login(credentials)
  .then(user => {
    console.log(`Welcome, ${user.name}!`);
  })
  .catch(error => {
    console.error('Authentication failed:', error.message);
  });
```

Expected output:

```text
Welcome, John Doe!
```
````

## Review and Maintenance

### Documentation Review Checklist

Before publishing documentation:

- [ ] All sections are present and complete
- [ ] Examples are tested and work correctly
- [ ] Links are valid and point to correct locations
- [ ] Spelling and grammar are correct
- [ ] Code samples use proper syntax highlighting
- [ ] Markdown linting passes with no errors
- [ ] Content is up-to-date with current implementation
- [ ] Screenshots (if any) are current
- [ ] Table of contents matches document structure

### Keeping Documentation Current

- Update docs in the same PR as code changes
- Review documentation quarterly for accuracy
- Mark deprecated features clearly
- Archive outdated documentation
- Solicit feedback from documentation users

## Tools and Automation

### Recommended Tools

- **markdownlint**: Markdown linting and formatting
- **markdown-spellcheck**: Spell checking for Markdown files
- **prettier**: Code and Markdown formatting
- **vale**: Prose linting for style consistency

### Running Linters

```bash
# Lint all Markdown files
npm run lint

# Fix auto-fixable issues
npm run lint:fix

# Spell check
npm run spellcheck
```

## Questions and Feedback

This style guide is a living document. If you have suggestions or questions:

- Open an issue with suggestions
- Submit a pull request with improvements
- Discuss in team meetings

---

**Last Updated**: 2024-03-19  
**Version**: 1.0.0
