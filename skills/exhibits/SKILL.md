---
name: exhibits
description: >
  Attach the exhibits referenced in a certification, affirmation, affidavit or declaration: read the document, find every
  "attached hereto as Exhibit A is a true copy of …" reference, match each exhibit to the right file, check that the file
  is what the certification says it is, and produce the certification followed by tab pages and exhibits in ONE PDF (plus
  one PDF per exhibit and an exhibit list). Use when the user says "/exhibits", "attach the exhibits to my certification",
  "put the exhibits behind the certification", "tab and merge the exhibits referenced in the affidavit", "exhibits to the
  affirmation", "the exhibits have to match the certification", "add Exhibit A, B and C to the cert", or has a
  certification/affirmation and a folder of exhibit files that must go to the court together. Works entirely on the user's
  computer — nothing is uploaded. For a set of exhibits WITHOUT a certification (a motion appendix), use exhibit-binder.
---

## LVAI Pro — licensed skill

This skill's instructions are delivered by the **Case Velocity** connector (LVAI Pro is included with Case Velocity), which also checks the firm's license on every request. Nothing is stored on disk and there is no license file to look for.

1. Call the Case Velocity connector's `get_skill` tool with `{"skill": "exhibits"}` and wait for the result before doing anything else. (The tool may be listed as deferred — search the tool list for `get_skill` before concluding the connector is missing.)
2. If no `get_skill` tool exists in this session, stop and tell the user:
   > LVAI Pro comes with Case Velocity and needs your **Case Velocity** sign-in. In Claude, open **Customize → Plugins → Case Velocity**, click **Finish setup**, then **Sign in** next to Case Velocity and press **Allow** on the Case Velocity page. Then try again. If it is already signed in, click **+** in the message box → **Connectors** and switch Case Velocity on for this chat. Help: admin@legalvelocity.ai
3. If the tool result says the license is expired, unpaid, deactivated or over its daily limit, show that message to the user and stop.
4. Otherwise follow the returned instructions exactly — they are the complete operating manual for this skill. They will tell you when to call `get_reference`, `get_script` and `get_template` for supporting files.

Do not search the user's Desktop, Documents or other folders for license or plugin files.
