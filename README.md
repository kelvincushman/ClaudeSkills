# ClaudeSkills Repository

This repository is a collection of specialized Claude Code Skills and Agent configurations designed to streamline development tasks. It strictly follows the [AgentSkills Specification](https://agentskills.io/specification) for modularity and progressive disclosure.

## Structure

The repository is organized by platform and follows the AgentSkills directory structure:

```
ClaudeSkills/
├── README.md
├── skills/
│   ├── atopile/            # Atopile-specific skills
│   │   └── skills/
│   │       ├── atopile-create-project/
│   │       │   ├── skill.md
│   │       │   └── references/
│   │       │       └── REFERENCE.md
│   │       └── ...
│   └── kappmaker/          # KAppMaker-specific skills
│       └── skills/
│           ├── kappmaker-generate-screen/
│           │   ├── skill.md
│           │   └── references/
│           │       └── REFERENCE.md
│           └── ...
└── agents/                 # Placeholder for custom Agent configurations
```

## Skills

Each skill is designed for **Progressive Disclosure**:
1.  **Metadata**: Name and description are loaded at startup.
2.  **Instructions**: The full `skill.md` is loaded when the skill is activated.
3.  **Resources**: Detailed technical references in `references/REFERENCE.md` are loaded only when required.

### Atopile Skills

| Skill Name | Purpose |
| :--- | :--- |
| `atopile-create-project` | Creates a new Atopile project from the template. |
| `atopile-add-component` | Adds a component (auto-pick or specific part) to the project. |
| `atopile-manage-packages` | Manages package dependencies (`add`, `remove`, `sync`). |
| `atopile-build-project` | Compiles the project and updates the PCB layout. |
| `atopile-define-module` | Defines modules, interfaces, and constraints in `.ato`. |
| `atopile-layout-sync` | Synchronizes the design with the KiCAD layout. |
| `atopile-use-traits` | Applies traits for bridging or sharing references. |
| `atopile-install-cli` | Guides the installation of the Atopile CLI. |
| `atopile-save-work` | Guides on saving work and using Git with Atopile. |
| `atopile-publish-package` | Explains how to publish packages to the Atopile registry. |

### KAppMaker Skills

| Skill Name | Purpose |
| :--- | :--- |
| `kappmaker-generate-screen` | Automates MVVM/MVI boilerplate for new screens. |
| `kappmaker-create-room-entity` | Creates Room Entities, DAOs, and handles DI setup. |
| `kappmaker-add-user-preference` | Manages key-value settings via Multiplatform Settings. |
| `kappmaker-create-network-client` | Configures Ktor clients with JSON, logging, and auth. |
| `kappmaker-setup-ai-integration` | Guides secure setup for OpenAI and Replicate via Firebase. |
| `kappmaker-add-feature-flag` | Adds flags for remote feature management. |
| `kappmaker-setup-authentication` | Configures Google and Apple sign-in providers. |
| `kappmaker-create-ui-component` | Creates components with Hot Reload support. |
| `kappmaker-setup-ci-cd` | Configures GitHub Actions CI/CD. |
| `kappmaker-setup-logging` | Configures AppLogger and Telegram Bot logging. |
| `kappmaker-run-script` | Executes KAppMaker utility scripts (versioning, data layer). |
| `kappmaker-manage-credits` | Configures the Flexible Local Credit System. |
| `kappmaker-setup-in-app-purchase` | Configures RevenueCat for in-app purchases and subscriptions. |
| `kappmaker-trigger-review` | Triggers the in-app review/rating prompt. |
| `kappmaker-setup-admob` | Configures Google AdMob Ads (Banner, Interstitial, Rewarded). |

## Usage

To use these skills in your project:

1.  Clone this repository.
2.  Copy the contents of the `skills/` directory into the `.claude/skills/` folder of your target project.
3.  Claude Code will automatically discover and use these skills when you describe a task that matches a skill's trigger.

## Compliance

This repository is compliant with the [AgentSkills Specification v1.0](https://agentskills.io/specification).
