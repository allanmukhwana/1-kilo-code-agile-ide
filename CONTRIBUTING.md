# Contributing to Kilo Code Agile PM Mode

Thank you for your interest in contributing! This guide will help you get started.

## Code of Conduct

By participating in this project, you agree to abide by our [Code of Conduct](CODE_OF_CONDUCT.md). Please be respectful and inclusive.

## How to Contribute

### Reporting Bugs

1. Check if the issue already exists
2. Create a new issue with:
   - Clear title describing the problem
   - Steps to reproduce
   - Expected vs actual behavior
   - Environment details (OS, Kilo Code version)

### Suggesting Features

1. Open a discussion first to gauge interest
2. Create an issue with:
   - Clear description of the feature
   - Use cases and benefits
   - Potential implementation approach

### Pull Requests

#### PR Process

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/my-feature`
3. Make your changes
4. Test locally in your project
5. Commit with clear messages: `git commit -m "Add feature X"`
6. Push to your fork: `git push origin feature/my-feature`
7. Open a Pull Request

#### PR Requirements

- [ ] Tests pass (if applicable)
- [ ] Documentation updated
- [ ] Commit messages are clear
- [ ] Code follows existing style

## Development Setup

### Prerequisites

- Kilo Code installed
- A text editor (VS Code recommended)

### Local Testing

1. Copy `.kilocodemodes` to your test project:
   ```bash
   cp .kilocodemodes /path/to/test-project/
   ```

2. Open the project in Kilo Code
3. Switch to Agile PM Mode
4. Test your changes:
   ```
   /agile-plan Test project description
   ```

### Mode Configuration Guide

The mode uses YAML configuration. Key fields:

```yaml
customModes:
  - slug: agile-pm          # Unique identifier
    name: Agile PM Mode    # Display name
    roleDefinition: >-     # Mode behavior
    groups:                # Tool permissions
    customInstructions:    # Mode commands
```

#### Available Tool Groups

| Group | Tools Allowed |
|-------|---------------|
| `read` | read_file, list_files, search_files |
| `edit` | write_to_file, search_and_replace |
| `command` | execute_command |
| `browser` | Browser actions |
| `mcp` | MCP tools |

#### File Restrictions

Restrict editing to specific file types:

```yaml
groups:
  - - edit
    - fileRegex: \.md$
      description: Markdown files only
```

## Style Guide

### YAML Formatting

- Use 2-space indentation
- Use `>-` for multiline strings
- Use descriptive comments

### Commit Messages

Format: `type: description`

Types:
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation
- `refactor`: Code restructuring
- `test`: Adding tests

## Recognition

Contributors will be listed in the README and credited for their work.

## Questions?

- Open an issue for bugs/features
- Start a discussion for questions
- Contact maintainers for sensitive issues

---

*By contributing, you agree to release your contributions under the MIT License.*
