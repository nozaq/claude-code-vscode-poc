This repository demonstrates that the Claude Code VS Code extension does not read `.claude/settings.json`. It contains two Dev Container definitions: `without-vscode-setting` and `with-vscode-setting`.

`without-vscode-setting` installs the Claude Code extension with no VS Code settings.

`with-vscode-setting` installs the extension and sets the `CLAUDE_CODE_USE_BEDROCK` environment variable via VS Code settings.

In both Dev Container definitions, the repository includes a `.claude/settings.json` file that sets `CLAUDE_CODE_USE_BEDROCK` to `1`.

## Steps to reproduece

1. Open this repository in VS Code using the `without-vscode-setting` Dev Container definition.
2. Open the Claude Code panel from the button in the top-right.

## Expected behavior
Claude Code should respect the `CLAUDE_CODE_USE_BEDROCK` environment variable from `.claude/settings.json`, and no sign-in screen should appear.

## Actual behavior

The Claude Code panel displays a sign-in screen.

![Actual behavior](./actual.png)

## Additional information

If `CLAUDE_CODE_USE_BEDROCK` is defined in VS Code settings (`claudeCode.environmentVariables`), it works as expected (no sign-in screen). You can confirm this by opening the repository with the `with-vscode-setting` Dev Container.
