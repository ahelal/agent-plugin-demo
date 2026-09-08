# Agent plugin demo

Two quick demos: install a community plugin, then install this repository's **UI Quality Coach** plugin.

Use a recent VS Code with GitHub Copilot and **Chat: Plugins Enabled**. For the browser demo, install **Node.js 22+** and **Google Chrome**. Review plugins before enabling them: their MCP servers run code on your machine.

## 1. Install `security-best-practices`

1. In VS Code settings, add `github/awesome-copilot#marketplace` to **Chat: Plugin Marketplace**, keeping any existing entries.
2. Open the Chat gear menu → **Plugins**, find **security-best-practices**, and install it.
3. Open [`prompt.md`](prompt.md). In Chat, type `/` and select the plugin's safety-review skill:

   `/security-best-practices:ai-prompt-engineering-safety-review prompt.md`

Ask it to **review the prompt, not execute it**, then discuss the findings.

## 2. Install this plugin: UI Quality Coach

**A skill defines the procedure. An agent defines the role. MCP provides the browser tools.**

| Plugin component | Purpose |
| --- | --- |
| [`plugin.json`](plugin.json) | Installable plugin manifest |
| [`skills/`](skills/) | `ui-smoke-test` skill and report template |
| [`com.github.copilot/agents/`](com.github.copilot/agents/) | **UI Reviewer** agent with a **Fix findings** handoff |
| [`mcp.json`](mcp.json) | Isolated Playwright browser |

The app and all its tooling live separately in [`example/`](example/). They are not needed to install the plugin.

### Install

Once this repository is pushed to a Git host:

1. Run **Chat: Install Plugin From Source** in the VS Code Command Palette.
2. Enter this repository's Git URL.
3. Start a new chat and select **UI Reviewer**. Confirm **ui-browser** is available under **MCP: List Servers**.

**Local rehearsal, before publishing:** in User Settings (JSON), add the absolute path of this repository to the `chat.pluginLocations` object with value `true`. Reload VS Code if needed. Register the **repository root**, not `example/`; use either local registration or source installation, not both.

### Run the demo

1. Open a local checkout of this repository in VS Code.
2. From the repository root, run `npm --prefix example start`. No npm install or build is needed to serve the app.
3. With **UI Reviewer** selected, run:

   `/ui-quality-coach:ui-smoke-test http://127.0.0.1:4173`

4. Watch the browser review the task tracker and report two deliberate UI bugs.
5. Select **Fix findings** to hand off to the coding agent, then rerun the review.

Use **Reset demo** to restore sample data. The review is a functional UI check, not a security audit; browser isolation is not a security boundary.

[Optional tests, presenter notes, and troubleshooting →](example/Readme.md)