# Contributing Guidelines

Thank you for your interest in contributing to this project! This document provides guidelines and expectations for contributors.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How to Contribute](#how-to-contribute)
- [Documentation Standards](#documentation-standards)
- [Commit Message Conventions](#commit-message-conventions)
- [Pull Request Process](#pull-request-process)
- [Code Review Checklist](#code-review-checklist)

## Code of Conduct

We are committed to providing a welcoming and inclusive environment for all contributors. Please:

- Be respectful and considerate in all interactions
- Welcome newcomers and help them get started
- Focus on constructive feedback
- Respect differing viewpoints and experiences

## How to Contribute

### Reporting Issues

- Check existing issues before creating a new one
- Provide clear, detailed descriptions
- Include steps to reproduce bugs
- Add relevant labels when possible

### Submitting Changes

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/your-feature-name`)
3. Make your changes following our standards
4. Test your changes thoroughly
5. Commit using our commit message conventions
6. Push to your fork
7. Submit a pull request

## Documentation Standards

All documentation must adhere to our established standards. Please refer to the
[Documentation Style Guide](DOCUMENTATION_STYLE_GUIDE.md) for comprehensive guidelines.

### Key Documentation Requirements

#### README Files

- Must include: Purpose, Installation, Usage, Contributing sections
- Use clear, concise language
- Provide working code examples
- Keep information up-to-date

#### Code Comments

- Write comments for complex logic and non-obvious decisions
- Use inline comments sparingly and only when necessary
- Document all public APIs and functions
- Follow language-specific documentation conventions:
  - **JavaScript/TypeScript**: Use JSDoc format
  - **Python**: Use docstrings (Google or NumPy style)
  - **Java**: Use Javadoc format
  - **Go**: Use godoc conventions

#### API Documentation

- Document all public functions, methods, and classes
- Include parameter types and return values
- Provide usage examples
- Document error conditions and exceptions
- Keep documentation in sync with code changes

### Markdown Standards

- Follow consistent formatting (enforced by markdownlint)
- Use ATX-style headers (# Header)
- Include blank lines before and after headers
- Use fenced code blocks with language identifiers
- Limit line length to 120 characters where practical
- Use reference-style links for repeated URLs

## Commit Message Conventions

We follow the [Conventional Commits](https://www.conventionalcommits.org/) specification for commit messages.

### Format

```text
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

### Types

- **feat**: A new feature
- **fix**: A bug fix
- **docs**: Documentation only changes
- **style**: Changes that don't affect code meaning (formatting, whitespace)
- **refactor**: Code changes that neither fix bugs nor add features
- **perf**: Performance improvements
- **test**: Adding or updating tests
- **chore**: Changes to build process or auxiliary tools
- **ci**: Changes to CI configuration files and scripts

### Examples

```text
feat: add user authentication module

docs: update installation instructions in README

fix: resolve null pointer exception in data processor

refactor: simplify database query logic
```

### Scope (Optional)

Add scope to provide additional context:

```text
feat(api): add endpoint for user profile retrieval
docs(readme): clarify setup prerequisites
fix(auth): prevent token expiration edge case
```

## Pull Request Process

### Before Submitting

1. **Update documentation** - Ensure all relevant documentation is updated
2. **Run linting tools** - Execute `npm run lint` to check markdown and code quality
3. **Test changes** - Verify that your changes work as expected
4. **Update changelog** - Add entry to CHANGELOG.md following Keep a Changelog format
5. **Self-review** - Review your own code using the checklist below

### PR Description Template

```markdown
## Description
Brief description of changes

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Documentation update
- [ ] Refactoring
- [ ] Other (please describe)

## Changes Made
- List key changes
- Include relevant details
- Reference related issues

## Testing
Describe testing performed

## Documentation
- [ ] README updated (if needed)
- [ ] Code comments added/updated
- [ ] CHANGELOG.md updated
- [ ] API documentation updated (if applicable)

## Checklist
- [ ] Code follows project style guidelines
- [ ] Documentation standards met
- [ ] Commit messages follow conventions
- [ ] All linting checks pass
```

### Review Process

- At least one approval required before merging
- All CI checks must pass
- Address all review comments or provide explanation
- Maintainers may request additional changes

## Code Review Checklist

### Documentation Quality

When reviewing pull requests, verify:

- [ ] **README updates** - Changes reflected in README if user-facing
- [ ] **Code comments** - Complex logic is explained clearly
- [ ] **API documentation** - All public interfaces documented
- [ ] **Inline comments** - Used appropriately, not excessively
- [ ] **Documentation accuracy** - All docs match current implementation
- [ ] **Markdown formatting** - Passes markdownlint validation
- [ ] **Spelling and grammar** - No typos or grammatical errors
- [ ] **Examples** - Code examples are correct and functional
- [ ] **Links** - All hyperlinks work correctly
- [ ] **Changelog entry** - Added to CHANGELOG.md with correct format

### Code Quality

- [ ] **Follows coding standards** - Adheres to project conventions
- [ ] **Tests included** - New features have appropriate tests
- [ ] **No breaking changes** - Or properly documented if necessary
- [ ] **Error handling** - Appropriate error messages and handling
- [ ] **Performance** - No unnecessary performance regressions

### Commit Quality

- [ ] **Commit messages** - Follow conventional commits format
- [ ] **Logical commits** - Each commit represents a logical unit
- [ ] **Clean history** - No merge commits or fixup commits (squash if needed)

## Questions?

If you have questions about contributing or need help getting started, please:

- Open an issue with the `question` label
- Reach out to the maintainers
- Review existing documentation and issues

Thank you for contributing!
