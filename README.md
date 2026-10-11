# DripDrop for ChatGPT Desktop and Codex

Edit a collaborative DripDrop document beside your agent conversation. This repository distributes the plugin package; the editor and document service are hosted by DripDrop.

## Install

In Terminal, with the Codex CLI installed, run:

```sh
codex plugin marketplace add autotelica/dripdrop-plugins --ref main
codex plugin add dripdrop@dripdrop
```

Restart ChatGPT Desktop. In Work mode or Codex, check the DripDrop marketplace in the Plugins Directory and complete the DripDrop connection when prompted. Open a new conversation with DripDrop selected and ask it to open your document. If you arrived from a share link, return to that page and choose **Open in ChatGPT**, then send the prepared message.

If you prefer your agent to perform setup, paste this prompt into a desktop Codex session with terminal access:

> Install DripDrop from the Git marketplace `autotelica/dripdrop-plugins` on branch `main`. Run `codex plugin marketplace add autotelica/dripdrop-plugins --ref main`, then `codex plugin add dripdrop@dripdrop`. Check the result. Do not recreate a private plugin or use Plugin Creator. Tell me whether I need to restart the desktop client or authenticate DripDrop. Do not claim the connection works until its tools are available.

Local Git marketplaces require a supported desktop client. They do not install into ChatGPT web or mobile. The browser document editor remains available at [DripDrop](https://dripdrop.autotelica.ai).

## Moving from a ZIP installation

This is a one-time migration to a different installation source. Install and verify the marketplace copy, then disable or remove your old ZIP installation to avoid duplicate DripDrop entries. Use the same DripDrop account. Your documents stay in DripDrop; do not delete your account, documents, or share grants. You may need to reconnect the new installation.

## Update

```sh
codex plugin marketplace upgrade dripdrop
```

Restart the desktop client and start a fresh conversation if it retains older plugin files or tool descriptions. If the plugin's tools are missing, reconnect DripDrop in the host's connection settings. A hosted editor/server update can be delivered without a package version change.

## Distribution

Plugin reference: `dripdrop@dripdrop`. Only the portable manifest, MCP connection, editing skill, logo, this guide, and marketplace catalog are distributed here. No credentials are included. This Git marketplace is separate from a reviewed listing in ChatGPT's universal plugin directory.

## License

The plugin files are licensed under the [Apache License 2.0](LICENSE). Copyright 2026 autotelica OÜ. Use of the hosted DripDrop service is governed by its own terms.
