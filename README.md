# ClaudeSkills Repository

This repository is a collection of specialized Claude Code Skills and Agent configurations designed to streamline development tasks. The structure is designed to be modular, allowing for easy integration of new skills and agents.

## Structure

The repository follows a standard structure for Claude Code projects:

```
ClaudeSkills/
├── README.md
├── skills/
│   ├── atopile/            # All Atopile-specific skills
│   │   ├── atopile-create-project/
│   │   └── ...
│   └── kappmaker/          # All KAppMaker-specific skills
│       ├── kappmaker-generate-screen/
│       └── ...
└── agents/                 # Placeholder for custom Agent configurations
    └── ...
```

## Skills

Skills are organized by the platform or domain they target. Each skill follows the multi-file structure for optimal performance and progressive disclosure:

*   `SKILL.md`: High-level overview and triggers.
*   `reference.md`: Detailed API, configuration, and code templates.
*   `examples.md`: Concrete usage scenarios.

### Atopile Skills

These skills assist in electronic circuit design using the Atopile language and compiler.

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

These skills automate boilerplate and configuration for the KAppMaker multiplatform framework.

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

## Agents

This directory is a placeholder for any custom Claude Agent configurations you may wish to add (e.g., a specialized "Git Agent" or "Security Agent").

## Usage

To use these skills in your project:

1.  Clone this repository.
2.  Copy the contents of the `skills/` directory into the `.claude/skills/` folder of your target project.
3.  Claude Code will automatically discover and use these skills when you describe a task that matches a skill's trigger.
