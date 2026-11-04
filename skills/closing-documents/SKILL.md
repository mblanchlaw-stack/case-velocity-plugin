---
name: closing-documents
description: >
  Generate real estate closing documents for a transaction. Use when the user asks to
  "prepare closing documents", "draft a deed", "create affidavit of title", "prepare GIT form",
  "affidavit of consideration", "seller closing documents", "closing package", "settlement documents",
  "prepare deed", "generate closing docs", "seller documents", "transfer documents", "deed prep",
  "closing paperwork", or needs any combination of deeds, affidavits, tax forms, or transfer
  documents for a NJ or NY real estate closing. Produces Word documents from firm templates and
  auto-fills bundled government PDF forms via LVAI PDF Filler integration.
---

## LVAI Pro — licensed skill

This skill's instructions are delivered by the **Case Velocity** connector (LVAI Pro is included with Case Velocity), which also checks the firm's license on every request. Nothing is stored on disk and there is no license file to look for.

1. Call the Case Velocity connector's `get_skill` tool with `{"skill": "closing-documents"}` and wait for the result before doing anything else. (The tool may be listed as deferred — search the tool list for `get_skill` before concluding the connector is missing.)
2. If no `get_skill` tool exists in this session, stop and tell the user:
   > LVAI Pro comes with Case Velocity and needs your **Case Velocity** sign-in. In Claude, open **Customize → Plugins → Case Velocity**, click **Finish setup**, then **Sign in** next to Case Velocity and press **Allow** on the Case Velocity page. Then try again. If it is already signed in, click **+** in the message box → **Connectors** and switch Case Velocity on for this chat. Help: admin@legalvelocity.ai
3. If the tool result says the license is expired, unpaid, deactivated or over its daily limit, show that message to the user and stop.
4. Otherwise follow the returned instructions exactly — they are the complete operating manual for this skill. They will tell you when to call `get_reference`, `get_script` and `get_template` for supporting files.

Do not search the user's Desktop, Documents or other folders for license or plugin files.
