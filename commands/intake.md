---
description: "Process a real estate contract and rider for a new transaction"
argument-hint: "[contract file]"
---

The user ran `/case-velocity:intake` with:

$ARGUMENTS

(If nothing follows, ask the user what they need before calling the connector.)

This command is the **contract-intake** skill of LVAI Pro. Its instructions are delivered by the **Case Velocity** connector (LVAI Pro is included with Case Velocity),
which checks the firm's license on every request; nothing is on disk and there is no license file to look for.

1. Call the Case Velocity connector's `get_skill` tool with `{"skill": "contract-intake"}` and wait for the result before doing anything else.
   (The tool may be listed as deferred — search the tool list for `get_skill` before concluding the connector is missing.)
2. If no `get_skill` tool exists in this session, stop and tell the user:
   > LVAI Pro comes with Case Velocity and needs your **Case Velocity** sign-in. In Claude, open
   > **Customize → Plugins → Case Velocity**, click **Finish setup**, then **Sign in** next to Case Velocity and press
   > **Allow** on the Case Velocity page. Then try again. If it is already signed in, click **+** in the message box →
   > **Connectors** and switch Case Velocity on for this chat. Help: admin@legalvelocity.ai
3. If the result says the license is expired, unpaid, deactivated or over its daily limit, show that message and stop.
4. Otherwise follow the returned instructions exactly, applied to the user's request above.

Do not search the user's Desktop, Documents or other folders for license or plugin files.
