---
name: hyperlinking
description: >
  Hyperlink all legal citations in a document (.docx) — case law to the opinion on Midpage (or on Descrybe when
  Midpage is not connected), statutes to Midpage's own law page for the section — or, without Midpage, to the
  section's page on law.onecle.com for that state or the U.S. Code — and federal rules to law.cornell.edu. Use when
  the user asks to "hyperlink citations", "add links to cases", "link case law", "hyperlink the brief", "hyperlink
  the memo", "add Midpage links", "add Descrybe links", "link citations", "hyperlink cases in my document", "link
  statutes", "hyperlink rules", or wants any legal document's citations turned into clickable hyperlinks. Also
  triggers when the user mentions "hyperlinking", "midpage links", "descrybe links", "onecle links", or wants
  citations in a brief or memorandum to be clickable. If the user has a .docx legal document and wants case names,
  statutes, or federal rules to link somewhere, use this skill. State court rules are intentionally not hyperlinked.
---

## LVAI Pro — licensed skill

This skill's instructions are delivered by the **Case Velocity** connector (LVAI Pro is included with Case Velocity), which also checks the firm's license on every request. Nothing is stored on disk and there is no license file to look for.

1. Call the Case Velocity connector's `get_skill` tool with `{"skill": "hyperlinking"}` and wait for the result before doing anything else. (The tool may be listed as deferred — search the tool list for `get_skill` before concluding the connector is missing.)
2. If no `get_skill` tool exists in this session, stop and tell the user:
   > LVAI Pro comes with Case Velocity and needs your **Case Velocity** sign-in. In Claude, open **Customize → Plugins → Case Velocity**, click **Finish setup**, then **Sign in** next to Case Velocity and press **Allow** on the Case Velocity page. Then try again. If it is already signed in, click **+** in the message box → **Connectors** and switch Case Velocity on for this chat. Help: admin@legalvelocity.ai
3. If the tool result says the license is expired, unpaid, deactivated or over its daily limit, show that message to the user and stop.
4. Otherwise follow the returned instructions exactly — they are the complete operating manual for this skill. They will tell you when to call `get_reference`, `get_script` and `get_template` for supporting files.

Do not search the user's Desktop, Documents or other folders for license or plugin files.
