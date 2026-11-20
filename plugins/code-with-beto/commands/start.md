---
description: "Check your Code with Beto plan and get three first steps for this project"
argument-hint: "[question]"
---

The user wants to start using Code with Beto in this project.

Their question, if any: $ARGUMENTS

1. Call the Code with Beto MCP tool `cwb_status`. If the server isn't connected or returns 401, stop and tell the user to run `/mcp`, pick `codewithbeto` and sign in. If they use an API key, it goes in `~/.config/codewithbeto/mcp-api-key` (see the plugin README).
2. Look at this repo just enough to know the platform and stack (package.json, app.json or app.config, an Xcode project).
3. Suggest three concrete first steps that fit both their plan and this repo. Name the MCP tool or the `code-with-beto` skill for each one.

Keep it short. If they're on the free plan, mention once what Pro adds and link https://codewithbeto.dev/pricing.
