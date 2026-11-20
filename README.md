# Code with Beto plugins

The Code with Beto plugin for Claude Code and Codex: the Code with Beto
MCP server (https://mcp.codewithbeto.dev) and Beto's skills for React Native, Expo and
SwiftUI apps.

This repo is generated from the Code with Beto site and overwritten on
every release, so pull requests here get lost. Report problems at
https://codewithbeto.dev/mcp.

## Install

Claude Code:

```bash
claude plugin marketplace add Code-with-Beto/plugins
claude plugin install code-with-beto@code-with-beto
```

Codex:

```bash
codex plugin marketplace add Code-with-Beto/plugins
codex plugin add code-with-beto@code-with-beto
```

Then sign in with your Code with Beto account: `/mcp` in Claude Code,
`codex mcp login codewithbeto` in Codex. Details and the API key
option are in [the plugin README](plugins/code-with-beto/README.md).

On Claude.ai or Claude Desktop, add the server as a custom connector
instead: Customize → Connectors → Add custom connector, URL `https://mcp.codewithbeto.dev`.

## Skills

- `app-icon`: Create, prepare, or integrate a mobile app icon. Use for icon concepts, adapting supplied artwork, iOS asset catalogs or Icon Composer, Android adaptive icons, or an Expo app icon configuration.
- `cwb-ai-image-flow`: Design, implement, or debug an image generation or editing feature, including input validation, provider requests, progress, results, retries, and cost controls. Use for photo-to-result or prompt-to-image workflows.
- `cwb-app-launch`: Check a mobile app's readiness for internal beta, public beta, or store submission. Use for release checklists, App Review preparation, testing release candidates, or choosing a native build versus an over-the-air update.
- `cwb-local-first`: Design, implement, or review offline-capable mobile features and on-device data. Use for local storage choice, durable writes, migrations, sync boundaries, data recovery, or tests after a restart.
- `cwb-mobile-ui`: Review or improve a mobile screen, navigation flow, or interaction for usability and native feel. Use for visual hierarchy, gestures, keyboard behavior, accessibility, adaptive layouts, and empty or error states.
- `cwb-monetization`: Design or verify mobile paywalls, product choices, and purchase entitlements. Use for subscriptions, one-time purchases, restore handling, sandbox tests, or diagnosing access after payment.
- `cwb-onboarding`: Design or improve mobile first-run onboarding, from initial launch to a first useful result. Use when reviewing welcome screens, starter demos, optional setup, or the timing of permission prompts and paywalls.
- `cwb-ship-coach`: Turn a mobile app idea into a focused MVP, choose an appropriate stack, and plan small implementation milestones. Use for app direction, scope, stack selection, or deciding what to build next.
- `local-build`: Produce and verify an installable local mobile build using the project's native toolchain. Use for iOS Simulator apps, physical-device builds, Android APKs, or artifacts for beta and UI testing.
- `theming`: Set up or improve semantic color tokens, light and dark appearance, system colors, and navigation theming in a mobile app. Use when color choices diverge across screens or the app needs a coherent appearance system.

The free plan reads the blog, guides, skills, app screens, sample lessons
and the Oyelo source. Pro adds project-specific skills, the full courses, and other premium
repos: https://codewithbeto.dev/pricing

## Rolling it out to a team

Each release is tagged `v<version>`, so you can pin one.

Claude Code reads these keys from managed settings (Claude.ai admin
console, MDM or `managed-settings.json`) and installs the plugin on every
machine:

```json
{
  "extraKnownMarketplaces": {
    "code-with-beto": {
      "source": {
        "source": "github",
        "repo": "Code-with-Beto/plugins"
      }
    }
  },
  "enabledPlugins": {
    "code-with-beto@code-with-beto": true
  }
}
```

Add `"ref": "v<version>"` next to `repo` to pin a release.

Codex teams that restrict marketplaces add this repo to the allowed
sources in `requirements.toml`, and the MCP server if they also restrict
those:

```toml
[marketplaces]
restrict_to_allowed_sources = true

[marketplaces.allowed_sources.code-with-beto]
source = "git"
url = "https://github.com/Code-with-Beto/plugins.git"

[mcp_servers.codewithbeto]
identity = { url = "https://mcp.codewithbeto.dev" }
```
