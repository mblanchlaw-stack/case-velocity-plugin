---
name: contract-intake
description: >
  Process a real estate contract and rider upload for a new transaction. Use when the user asks to
  "upload a contract", "new real estate transaction", "start a transaction", "review this contract",
  "process this contract and rider", "intake a new deal", "new closing", "new real estate deal",
  "I have a new contract", or uploads a real estate contract PDF/document and needs the transaction
  set up with dates calendared and rider preparation identified. Covers NJ and NY residential,
  condo, and co-op transactions for both buyer and seller representation.
---

## LVAI Pro — licensed skill

This skill's instructions are delivered by the **Case Velocity** connector (LVAI Pro is included with Case Velocity), which also checks the firm's license on every request. Nothing is stored on disk and there is no license file to look for.

1. Call the Case Velocity connector's `get_skill` tool with `{"skill": "contract-intake"}` and wait for the result before doing anything else. (The tool may be listed as deferred — search the tool list for `get_skill` before concluding the connector is missing.)
2. If no `get_skill` tool exists in this session, stop and tell the user:
   > LVAI Pro comes with Case Velocity and needs your **Case Velocity** sign-in. In Claude, open **Customize → Plugins → Case Velocity**, click **Finish setup**, then **Sign in** next to Case Velocity and press **Allow** on the Case Velocity page. Then try again. If it is already signed in, click **+** in the message box → **Connectors** and switch Case Velocity on for this chat. Help: admin@legalvelocity.ai
3. If the tool result says the license is expired, unpaid, deactivated or over its daily limit, show that message to the user and stop.
4. Otherwise follow the returned instructions exactly — they are the complete operating manual for this skill. They will tell you when to call `get_reference`, `get_script` and `get_template` for supporting files.

Do not search the user's Desktop, Documents or other folders for license or plugin files.
