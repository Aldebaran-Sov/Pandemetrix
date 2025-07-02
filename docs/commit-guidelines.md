# Commit Message Guidelines

This document outlines best practices for writing clear, consistent, and informative commit messages in the Pandemetrix project.

## Format Structure

Use the following format for commit messages:

``` text
<type>(<scope>): <subject>

<body>

<footer>
```

### Required Elements

- **Type**: The kind of change being made
- **Subject**: Brief description of the change (50 characters or less)

### Optional Elements

- **Scope**: Component or area affected by the change
- **Body**: Detailed explanation of what and why (wrap at 72 characters)
- **Footer**: References to issues, breaking changes, etc.

## Commit Types

| Type | Description | Example |
|------|-------------|---------|
| `feat` | New feature | `feat(auth): add OAuth2 login support` |
| `fix` | Bug fix | `fix(api): resolve null pointer in user service` |
| `docs` | Documentation changes | `docs(readme): update installation instructions` |
| `style` | Code style changes (formatting, etc.) | `style(components): fix indentation in header` |
| `refactor` | Code refactoring | `refactor(utils): extract validation helpers` |
| `test` | Adding or updating tests | `test(auth): add unit tests for login flow` |
| `chore` | Maintenance tasks | `chore(deps): update dependencies to latest` |
| `perf` | Performance improvements | `perf(db): optimize user query with indexes` |
| `ci` | CI/CD changes | `ci(github): add automated testing workflow` |
| `build` | Build system changes | `build(webpack): update production config` |
| `revert` | Revert previous commit | `revert: feat(auth): add OAuth2 login support` |

## Subject Line Rules

### Do

- Use imperative mood ("add", "fix", "update", not "added", "fixed", "updated")
- Keep it under 50 characters
- Start with lowercase letter
- No period at the end
- Be specific and descriptive

### Don't

- Use past tense
- Include generic messages like "fix bug" or "update code"
- Use unnecessary words like "just", "simply", "only"
- Include file names unless absolutely necessary

## Examples

### Good Examples

```bash
# Simple feature addition
feat(dashboard): add real-time data refresh

# Bug fix with scope
fix(auth): prevent duplicate user registration

# Documentation update
docs(api): add endpoint documentation for user management

# Performance improvement
perf(search): implement caching for frequently accessed data

# Breaking change
feat(api)!: change user endpoint response format

BREAKING CHANGE: User API now returns nested user object instead of flat structure.
Migrate existing integrations to use user.profile.name instead of user.name.
```

### Bad Examples

```bash
# Too vague
fix: bug fix

# Past tense
fixed: login issue

# Too long
feat(authentication): implement a comprehensive OAuth2 authentication system with support for multiple providers

# Not descriptive
update stuff

# Missing type
add new feature
```

## Body Guidelines

Use the body to explain:

- **What** was changed
- **Why** the change was necessary
- **How** the change addresses the issue

### Body Format

``` text
feat(api): add user profile endpoint

Add new REST endpoint to fetch and update user profile information.
This endpoint supports both GET and PUT methods and includes
validation for all user fields.

The endpoint was needed to support the new profile management
feature in the frontend application.
```

## Footer Guidelines

### Issue References

```bash
# Single issue
Closes #123

# Multiple issues
Closes #123, #456

# Related issues
Related to #789
See also #101
```

### Breaking Changes

```bash
BREAKING CHANGE: Database schema updated
User table now requires email field to be unique.
Run migration script before deploying.
```

## Common Scopes

Use these common scopes when applicable:

| Scope | Description |
|-------|-------------|
| `auth` | Authentication and authorization |
| `api` | REST API endpoints |
| `ui` | User interface components |
| `db` | Database related changes |
| `config` | Configuration files |
| `deps` | Dependencies |
| `security` | Security improvements |
| `performance` | Performance optimizations |
| `tests` | Test files and testing utilities |
| `docs` | Documentation |

## Multi-line Examples

### Feature with detailed explanation

``` text
feat(dashboard): implement real-time analytics

Add WebSocket connection to stream live analytics data to the
dashboard. This replaces the previous polling mechanism which
was causing performance issues with high user loads.

Changes include:
- WebSocket server setup with authentication
- Client-side connection management
- Fallback to polling for unsupported browsers
- Error handling and reconnection logic

Closes #245
Related to #201
```

### Bug fix with impact description

``` text
fix(payment): resolve transaction timeout issues

Fix race condition in payment processing that caused timeouts
during high traffic periods. The issue occurred when multiple
payment requests were processed simultaneously for the same user.

Added proper transaction locking and improved error handling
to prevent data corruption and ensure payment consistency.

Fixes #892
```

## Tools and Automation

### Conventional Commits

This project follows [Conventional Commits](https://conventionalcommits.org/) specification for automated:

- Changelog generation
- Semantic versioning
- Release automation

### Commit Message Linting

Consider using tools like:

- `commitlint` - Lint commit messages
- `husky` - Git hooks for commit validation
- `conventional-changelog` - Generate changelogs

### Git Hooks Example

```bash
# .gitmessage template
# <type>(<scope>): <subject>
# 
# <body>
# 
# <footer>
```

## Quick Reference

### Commit Message Checklist

- [ ] Starts with appropriate type
- [ ] Subject is 50 characters or less
- [ ] Uses imperative mood
- [ ] No period at end of subject
- [ ] Body explains what and why (if needed)
- [ ] References relevant issues
- [ ] Follows project conventions

### Common Commands

```bash
# Set commit message template
git config commit.template .gitmessage

# Interactive commit for better messages
git commit

# Amend last commit message
git commit --amend

# View commit history with format
git log --oneline --graph
```

Remember: Good commit messages are a gift to your future self and your teammates!
