---
description: "Build a feature in this app using the code from a Code with Beto template"
argument-hint: "<feature, e.g. onboarding like Platano>"
---

The user wants to build this feature in their app, based on code from a Code with Beto template:

$ARGUMENTS

If nothing was passed, ask what they want to build and which template it should look like (Platano, Inkigo, Oyelo, or "whichever fits").

1. Read this repo first: platform, navigation, theme and the files the feature will touch.
2. Call `prepare_feature` with the request, the platform and the stack. Use the plan it returns. On the free plan it only covers Oyelo; say so if they asked for another template.
3. Read the source it points to with `copy_from_template` (repo + path is fastest; template + pattern works too) or `search_template_code`. If GitHub access fails, call `check_github_access` and explain the fix.
4. Adapt the code to this project: imports, theme tokens, navigation, naming. Don't paste a whole screen when a component does the job.
5. Run the project's typecheck or tests if they exist. Report which template files you read and what you changed from them.
