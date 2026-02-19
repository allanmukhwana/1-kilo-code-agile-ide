# Kilo Code Agile PM Mode

A Kilo Code custom mode for Agile project management. This mode helps teams break down projects into actionable agile artifacts that connect directly to code implementation.

## Features

- **Evidence-Based Analysis**: Analyzes your actual codebase to ground agile artifacts in reality
- **Repo-Aware**: Reads your code structure to understand functionality before generating artifacts
- **Execution-Optimized**: Focuses on deliverable user stories with verifiable acceptance criteria
- **7-Command Suite**: Multiple commands for flexible project planning
- **Technical Specs**: Generates architecture diagrams and API documentation

## Installation

### Option 1: Per-Project (Recommended)

1. Copy the `.kilocodemodes` file to your project root:
   ```bash
   cp .kilocodemodes /path/to/your/project/
   ```

2. The mode will be automatically detected when you open the project in Kilo Code

### Option 2: Global Installation

1. Copy to your global Kilo Code settings:
   ```bash
   # Windows
   copy .kilocodemodes %APPDATA%\Code\User\globalStorage\kilocode.kilo-code\settings\custom_modes.yaml
   
   # macOS/Linux
   cp .kilocodemodes ~/.config/Code/User/globalStorage/kilocode.kilo-code/settings/custom_modes.yaml
   ```

## Usage

### Starting the Mode

1. Open your project in Kilo Code
2. Switch to "Agile PM Mode" using the mode switcher
3. The mode will analyze your repository structure

### Using the Custom Commands

Once in Agile PM Mode, use any of these commands:

```bash
# 1. Generate core agile artifacts (recommended for new projects)
/agile-plan A task management app with user authentication, project boards, and real-time collaboration

# 2. Generate product backlog
/generate-backlog Create a backlog for the e-commerce platform

# 3. Generate roadmap
/generate-roadmap Plan the roadmap for mobile app expansion

# 4. Generate sprint retrospective
/generate-retrospective 1

# 5. Generate technical architecture specs
/generate-specs Design the system architecture for a SaaS platform

# 6. Generate all agile artifacts
/generate-all Build a comprehensive project plan

# 7. Generate everything (agile + technical)
/generate-all-full Complete documentation for new platform
```

**All Commands:**

| Command | Description | Output |
|---------|-------------|--------|
| `/agile-plan [desc]` | Core 6 artifacts | USER_PERSONAS.md, USER_JOURNEYS.md, EPICS.md, USER_STORIES.md, ACCEPTANCE_CRITERIA.md, SPRINTS.md |
| `/generate-backlog [desc]` | Product backlog | PRODUCT_BACKLOG.md |
| `/generate-roadmap [desc]` | Timeline & milestones | ROADMAP.md |
| `/generate-retrospective [sprint]` | Sprint retrospective | SPRINT_RETROSPECTIVE.md |
| `/generate-specs [desc]` | Technical specs | ARCHITECTURE.md, API_SPEC.md, DATABASE_SCHEMA.md |
| `/generate-all [desc]` | All 8 artifacts | All above + additional

### Generated Artifacts

The mode generates these Markdown files in your project root:

| File | Description |
|------|-------------|
| `USER_PERSONAS.md` | Distinct user types identified from code patterns |
| `USER_JOURNEYS.md` | Critical user paths mapped from routes/APIs |
| `EPICS.md` | Feature themes grouped by module boundaries |
| `USER_STORIES.md` | Actionable stories with clear value propositions |
| `ACCEPTANCE_CRITERIA.md` | Verifiable success conditions from code behavior |
| `SPRINTS.md` | Time-boxed iterations with shippable goals |
| `PRODUCT_BACKLOG.md` | Prioritized feature list with story points |
| `ROADMAP.md` | Timeline and milestones |
| `SPRINT_RETROSPECTIVE.md` | Sprint retrospective template |
| `ARCHITECTURE.md` | System architecture overview |
| `API_SPEC.md` | REST API specifications |
| `DATABASE_SCHEMA.md` | Database schema documentation |
| `COMPONENT_DIAGRAM.md` | Component diagram descriptions |

## Configuration

### Mode Settings

The `.kilocodemodes` file contains:

```yaml
customModes:
  - slug: agile-pm
    name: Agile PM Mode
    groups:
      - read           # Read any file
      - - edit         # Edit only
        - fileRegex: \.md$  # Markdown files
      - command        # Execute commands
```

### Customizing Tool Access

If you need to adjust tool permissions, modify the `groups` array:

```yaml
groups:
  - read               # Enable file reading
  - - edit             # Enable editing
    - fileRegex: \.md$ # Restrict to markdown
    - fileRegex: \.yaml$ # Also allow YAML
  - command            # Enable CLI commands
```

## How It Works

### Evidence-Based Approach

1. **Code Analysis**: Reads actual source files to understand functionality
2. **Pattern Detection**: Identifies API routes, UI components, database schemas
3. **Artifact Generation**: Creates agile artifacts grounded in real code

### Execution-Focused Output

- Each user story has a clear "then" (deliverable)
- Acceptance criteria are verifiable through testing
- Sprints have concrete goals resulting in shippable increments

### Artifact Pipeline

```
Project Description → Code Analysis → User Personas → User Journeys → 
Epics → User Stories → Acceptance Criteria → Sprints → Backlog → Roadmap
```

**Command Flow:**

1. `/agile-plan` - Core 6 artifacts for initial planning
2. `/generate-backlog` - Refine and prioritize backlog
3. `/generate-roadmap` - Create timeline
4. `/generate-retrospective` - Sprint review (run after each sprint)
5. `/generate-specs` - Technical architecture documentation
6. `/generate-all` - Complete agile set
7. `/generate-all-full` - Everything (agile + technical)

## For Developers

### Forking This Mode

1. Clone this repository
2. Modify `.kilocodemodes` with your customizations
3. Test locally in your project

### Adding Custom Artifacts

To add new artifacts, edit the `customInstructions` section in `.kilocodemodes`:

```yaml
customInstructions: >-
  ADD YOUR CUSTOM ARTIFACT HERE:
  - Generate CUSTOM_ARTIFACT.md based on...
```

### Creating New Modes

This project demonstrates the mode creation pattern. To create your own:

1. Add a new entry to `customModes` array
2. Define `slug`, `name`, `roleDefinition`
3. Configure `groups` for tool access
4. Add `customInstructions` for behavior

See [Kilo Code Mode Documentation](https://github.com/kilo-code/docs) for full schema.

## Project Structure

```
.
├── .kilocodemodes       # Mode configuration (copy to your project)
├── README.md            # This file
├── LICENSE              # MIT License
└── CONTRIBUTING.md      # Contribution guidelines
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! Please read our [contributing guidelines](CONTRIBUTING.md) before submitting PRs.

## Support

- **Issues**: Report bugs or request features via GitHub Issues
- **Discussions**: Ask questions and share feedback

## Acknowledgments

- Kilo Code for the extensible mode system
- Agile methodology practitioners for best practices
