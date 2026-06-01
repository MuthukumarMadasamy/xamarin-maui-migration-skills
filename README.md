# xamarin-maui-migration-skills

AI-ready migration skills for moving Xamarin.Forms applications to .NET MAUI, including platform migration, renderer-to-handler migration, and Syncfusion control migration.

## Quick Start

### Option 1: Using npx (Recommended)

If your assistant supports npx-based skill installation:

```bash
npx skills add https://github.com/syncfusion/xamarin-maui-migration-skills
```

This will automatically add the skills to your workspace.

If your repository URL is different, replace the URL in the command.

### Option 2: Manual Workspace Setup

**1. Clone this repository**

```bash
git clone https://github.com/syncfusion/xamarin-maui-migration-skills.git
```

**2. Add it to your VS Code workspace**

Open your `.code-workspace` file (or create one) and add this repo as a second root folder:

Example workspace file:

```json
{
  "folders": [
    { "path": "/path/to/your-maui-app" },
    { "path": "/path/to/xamarin-maui-migration-skills" }
  ]
}
```

## Prerequisites

- An AI coding assistant that supports workspace skills and reference files.
- .NET SDK compatible with your MAUI target.
- MAUI workload installed.
- Syncfusion license and packages if using Syncfusion controls.

## How These Skills Work

Each skill folder contains:

- SKILL.md: Intent, scope, workflow, and constraints.
- references/: Supporting guidance used for deeper migration tasks.

When your prompt matches a skill intent, the assistant can apply that skill and its references to produce migration guidance and action items.

## Repository Structure

```text
README.md
skills/
  INDEX.md
  xamarin-maui-framework-migration/
    SKILL.md
    references/
  xamarin-maui-syncfusion-migration/
    SKILL.md
    references/
      controls/   (control-wise API/event/method mappings)
  xamarin-maui-platform-specific-migration/
    SKILL.md
    references/
  xamarin-maui-renderer-handler-migration/
    SKILL.md
    references/
```

## Recommended Skill Sequence

For end-to-end migration runs, use this order:

1. xamarin-maui-framework-migration
2. xamarin-maui-syncfusion-migration (if Syncfusion controls are used)
3. xamarin-maui-platform-specific-migration
4. xamarin-maui-renderer-handler-migration

## Skill Index

### 1) Framework Migration

- Skill: skills/xamarin-maui-framework-migration/SKILL.md
- Use for baseline Xamarin.Forms to MAUI migration, namespace/API modernization, and migration readiness reporting.

### 2) Syncfusion Migration

- Skill: skills/xamarin-maui-syncfusion-migration/SKILL.md
- Use for Syncfusion control mapping, namespace updates, API/event/method migration mapping, package checks, and MauiProgram registration checks.
- Control-wise references: skills/xamarin-maui-syncfusion-migration/references/controls/

### 3) Platform-Specific Migration

- Skill: skills/xamarin-maui-platform-specific-migration/SKILL.md
- Use for Android/iOS/Windows capabilities, lifecycle, startup, and platform parity validation.

### 4) Renderer-to-Handler Migration

- Skill: skills/xamarin-maui-renderer-handler-migration/SKILL.md
- Use for converting custom renderers and effects to MAUI handlers, including mapping and parity validation.

## Example Prompts

- Migrate this Xamarin.Forms solution to MAUI using new-project strategy and produce a manual-fix backlog.
- Analyze platform-specific migration risks for Android and iOS and output capability parity checks.
- Migrate Syncfusion controls from Xamarin to MAUI and produce control-wise API/event/method mapping decisions.
- Convert custom Xamarin renderers to MAUI handlers and provide validation scenarios.

## Notes

- Some control migrations include unresolved items from source guides, such as Nil or Upcoming markers. These should be treated as explicit manual-review tasks.
- Keep skill references updated as Syncfusion and MAUI APIs evolve.
