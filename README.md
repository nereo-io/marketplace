# Nereo for Codex

The Codex plugin marketplace for [Nereo](https://www.nereo.io). It ships one plugin, [`nereo`](plugins/nereo),
which connects Codex to your Nereo canvas so you can make images, videos, music and edits from a Codex task.

| Install name | Display name | MCP server | Version |
| --- | --- | --- | --- |
| `nereo` | Nereo | `https://www.nereo.io/mcp` | `1.0.0` |

The plugin is a remote HTTP MCP server. It holds no client ID, keys or local server: Codex registers itself and
signs you in through the server's OAuth metadata, and every person signs in with their own Nereo account.

## Install

### Let Codex do it

Paste this into a Codex task:

```text
Install the Nereo plugin so I can create images and videos here.

1. Add the marketplace: run `codex plugin marketplace add nereo-io/marketplace --ref main`
2. Install the plugin: run `codex plugin add nereo@nereo`
3. In a new task, sign in to my Nereo account when asked

Tell me when it's ready to start creating.
```

### Or run it yourself

```bash
codex plugin marketplace add nereo-io/marketplace --ref main
codex plugin add nereo@nereo
```

Then start a new Codex task and sign in to Nereo when Codex asks (or from the MCP connections list). The
repository is public, so no GitHub sign-in is needed.

## Use

Ask in plain words, for example:

- "Show my Nereo projects"
- "Make an 8-second product video from this photo with Nereo"
- "Write a 30-second story and turn it into a multi-shot video on my Nereo canvas"

Only starting a generation spends credits. Codex tells you what a run costs before it starts, and failed runs are
refunded automatically. You can see and disconnect connected apps at
[nereo.io/connected-apps](https://www.nereo.io/connected-apps).

## Update

```bash
codex plugin marketplace upgrade nereo
codex plugin add nereo@nereo
```

Start a new Codex task afterwards. Before sign-in the server answers `401` with `WWW-Authenticate: Bearer`, and both
OAuth well-known endpoints answer `200`; that is expected.

## Uninstall

```bash
codex plugin remove nereo
codex plugin marketplace remove nereo
```
