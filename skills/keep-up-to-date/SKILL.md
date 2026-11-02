---
name: keep-up-to-date
description: >
  Set up the two scheduled tasks that keep a firm's Case Velocity site current: a full check every 12 hours and a pickup
  every hour. Use when the user says "keep Case Velocity up to date", "set up Case Velocity", "schedule the Case Velocity
  check", or pastes the setup line Case Velocity shows after connecting.
---

## Case Velocity — keep it up to date

1. Confirm the Case Velocity connector is connected: its `get_work` tool should be in the tool list (search for it if
   tools are deferred). If it is missing, tell the user to open **Customize → Connectors**, find **Case Velocity**, click
   **Connect** and sign in, then come back.
2. Check the user's existing scheduled tasks first, and do not create a duplicate of one that already runs Case
   Velocity's full check or pickup.
3. With the scheduling tools available in this session, create:
   - **Case Velocity full check**, every 12 hours, with the prompt: "Run Case Velocity's full check."
   - **Case Velocity pickup**, every hour, with the prompt: "Run Case Velocity's pickup."
   Ask for the user's time zone if it is not known. Each task needs the Case Velocity, Gmail, Google Calendar and Google
   Drive connectors.
4. If no scheduling tool is available here, say so plainly and suggest setting them up from Claude Desktop.

Tell the user, in two sentences, which tasks were created and when they run.
