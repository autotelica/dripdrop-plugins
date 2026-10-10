---
name: dripdrop
description: Work with DripDrop documents using the connected DripDrop MCP tools. Use for creating, reading, editing, sharing, or discussing DripDrop documents.
---

Discover available DripDrop tools first. A local plugin installation does not establish that the configured remote endpoint is deployed or authorized.

Use the user's ChatGPT or other host agent to edit; do not invoke DripDrop's built-in AI. DripDrop supplies the live collaborative document and editing tools. Respect the user's chosen model.

When a document or selected passage is already in context, edit that document. Requests such as "change this", "rewrite", or "make it better" do not mean create a new document. Use create_document only when a new document is requested. Open the editor with open_dripdrop_panel and the documentId returned by create_document or open_document; never ask the user to copy a known ID into the panel.

Read the current selected range and use the operation schema advertised by apply_edits. Use supported range operations for edits that add or remove line breaks or span paragraphs. Preserve content outside the requested range. On stale selection, re-read current context; do not silently broaden the target or fall back to computer-use editing after a tool error.

For export, discover available templates with list_export_templates when needed and pass the requested styling and pending-change policy to export_document. Accepting or rejecting changes in an export does not review them in the live document.

Figures are document-owned image assets, not URLs in document JSON. For a requested flow or architecture diagram, compose a legible self-contained SVG and call create_svg_figure with its markup, then read the intended insertion point and call apply_edits with one insertBlocks figure operation using the returned assetId. Use alt text and width 624 for a page-width diagram; width is pixels, not a percentage. SVG requires numeric width and height, ordinary drawing elements and inline presentation attributes. It cannot contain scripts, CSS, foreignObject or external resources. An existing figure can be replaced or removed with replaceFigure or deleteFigure. These edits are reviewable structural changes in the current document. Do not create a new document to add a diagram.

Markdown imports may use public HTTPS image links; DripDrop fetches supported images and stores private copies during creation. Never imply that an external URL remains the document's live image source. Markdown exports with images are ZIP files containing document.md and relative images; text-only exports remain plain Markdown.

Use document handles and fresh bounded reads returned by the service. Address targeted edits with returned read tokens and anchors; re-read on STALE_READ. Persistent writes require a stable caller-generated requestId; preserve it for retries of the identical operation. Text edits are tracked changes. Accept or reject only when asked.

Read comment context before addressing a thread. Reply to explain edits. Resolve comments only on explicit instruction; editing alone does not resolve them.

Sharing gives anyone with the link edit access. Return the share link when asked; do not imply named invitations or send messages. Guest access does not grant account discovery, document creation, owner share retrieval, or share reset.

Tool-only hosts can use text results and Open in DripDrop links. Graphical hosts may render the MCP App; do not claim Cowork compatibility until the actual host checklist has passed. Session secrets remain in app-only metadata, never in prose, URLs, files, or persistent browser storage.
