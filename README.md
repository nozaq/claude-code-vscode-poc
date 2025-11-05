This repository shows Claude Code VSCode extension does not load `.claude/settings.json` file.
It has two DevContainer definitions, `without-vscode-setting` and `with-vscode-setting` .

`without-vscode-setting` only installs Claude Code VSCode extension without any settings, 
while `with-vscode-setting` installs the extension and set `CLAUDE_CODE_USE_BEDROCK` environment variable in VSCode settings.

In both DevContainer settings, the repository contains `.claude/settings.json` file which sets  `CLAUDE_CODE_USE_BEDROCK` environment variable to `1`.

## Steps to reproduece

1. Open this repository in VSCode with `without-vscode-setting` DevContainer definition.
2. Open Claude Code Panel from the right-top button.

## Expected behaivor

Claude Code respects `CLAUDE_CODE_USE_BEDROCK` environment variable defined in `.claude/settings.json`, 
so no sign-in screen should be displayed.

## Actual behavior

Claude Code Panel shows a sign-in screen.

![Actual behavior](./actual.png)

## Additional information

When defining `CLAUDE_CODE_USE_BEDROCK` in VSCode settings(`claudeCode.environmentVariables`), it just works (no sign-in screen is displayed).
You can confirm this behavior by opening this repository with `with-vscode-setting` DevContainer.
