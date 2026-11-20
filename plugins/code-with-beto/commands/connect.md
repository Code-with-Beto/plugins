---
description: "Fix the Code with Beto MCP connection in Claude Code"
---

The user wants to check their Code with Beto MCP connection.

1. Call `cwb_status`. If it works, report the plan and stop.
2. If the server is missing or failing, explain the two ways to connect, in this order:
   - Sign in: run `/mcp`, pick `codewithbeto`, then Authenticate.
   - API key: copy one from https://codewithbeto.dev/profile and save it on its own line in `~/.config/codewithbeto/mcp-api-key`, then restart Claude Code. Each copy on the profile page issues a new key and disables the previous one.
3. If `cwb_status` works but private repos fail, call `check_github_access` and walk them through what it says.

Never ask the user to paste a key into the chat.
