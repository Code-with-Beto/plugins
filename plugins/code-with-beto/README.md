# Code with Beto plugin

One install adds the Code with Beto MCP server and Beto's skills to Claude
Code or Codex. Claude Code also gets a few slash commands.

## Claude Code

```bash
claude plugin marketplace add Code-with-Beto/plugins
claude plugin install code-with-beto@code-with-beto
```

Then run `/mcp`, pick `codewithbeto` and sign in with your Code with Beto
account.

### Using an API key instead of signing in

Copy a key from https://codewithbeto.dev/profile and save it on its own
line in `~/.config/codewithbeto/mcp-api-key`:

```bash
mkdir -p ~/.config/codewithbeto
pbpaste > ~/.config/codewithbeto/mcp-api-key
chmod 600 ~/.config/codewithbeto/mcp-api-key
```

Restart Claude Code. The plugin sends the key as a bearer token. Delete the
file to go back to signing in.

### Commands

- `/code-with-beto:start`: Check your Code with Beto plan and get three first steps for this project
- `/code-with-beto:build-like-template`: Build a feature in this app using the code from a Code with Beto template
- `/code-with-beto:launch`: Build a launch checklist for this app from Beto's launch guide
- `/code-with-beto:connect`: Fix the Code with Beto MCP connection in Claude Code

## Codex

```bash
codex plugin marketplace add Code-with-Beto/plugins
codex plugin add code-with-beto@code-with-beto
```

Then run `codex mcp login codewithbeto` and sign in with your Code
with Beto account. Codex doesn't load plugin slash commands; ask for the
same things in plain words, or call a skill with `$` and its name.

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
