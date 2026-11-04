# Case Velocity for Claude

Case Velocity (https://casevelocity.ai) is an AI-first case management site for law firms, operated by Legal Velocity, Inc.
This plugin connects a firm's Case Velocity account to Claude. Attorneys ask for work on the site — check my email for case
updates, draft this motion, put this note in the case folder, tell Tiffany to call the client — and Claude does it with the
firm's own Claude account and connections, then reports the result back to the site, where the attorney reviews, accepts or
dismisses it. Nothing Claude proposes is filed, served or sent on its own.

**One install does it all.** Click **Add**, then **Sign in** next to Case Velocity in Claude's "Finish setting up" window,
and press **Allow** on the Case Velocity page. That brings the **Case Velocity** connector (`https://casevelocity.ai/mcp`) and
**LVAI Pro**, the legal skills included with every Case Velocity subscription, under the same sign-in. No API key, and no
second plugin or connector. Then type `/case-velocity:setup` once: Claude checks your connections and schedules the
automatic checks.

## Requirements

- A Case Velocity subscription for your firm (14-day free trial at https://casevelocity.ai).
- A paid Claude plan. Scheduled checks and file-building steps run in Claude Desktop (Cowork).
- Claude's Gmail, Google Calendar and Google Drive connectors for email, calendar and case-folder work. Optional: Slack,
  Plaud, and Claude's browser for reading web mail. For legal research, the firm's own Midpage or Descrybe connector.

## Commands

| Command | What it does |
| --- | --- |
| `/case-velocity:check` | Runs Case Velocity's full check now: the attorney's waiting requests, new email and calendar items for open cases, case folders, drafts in the queue, team chat tasks. |
| `/case-velocity:pickup` | Runs the quick hourly pickup: waiting requests, mail from the last two hours, and the drafting queue. |
| `/case-velocity:setup` | Guided setup: checks the Case Velocity sign-in, the LVAI Pro license, Gmail, Google Calendar, Google Drive and Midpage/Descrybe, schedules the full check (every 12 hours) and the pickup (every hour), and shows what is left. |

### LVAI Pro legal commands (included with Case Velocity)

| Command | What it does |
| --- | --- |
| `/case-velocity:analyze-form` | Analyze a PDF form: list every fillable field and its structure |
| `/case-velocity:binder` | Build a verified Citation Binder (Word) from a brief or memorandum |
| `/case-velocity:calendar-dates` | Calendar every critical date of a real estate transaction |
| `/case-velocity:case-summary` | Produce a detailed summary and analysis of a court opinion |
| `/case-velocity:closing-docs` | Generate the closing documents for a NJ or NY transaction |
| `/case-velocity:correct` | Fix the issues found by /verify and re-verify the corrected document |
| `/case-velocity:deep-research` | Comprehensive deep legal research with full opinion analysis |
| `/case-velocity:discovery` | Generate discovery documents (interrogatories, RFPs, RFAs) |
| `/case-velocity:draft` | Draft a legal document from research and materials |
| `/case-velocity:exhibit-binder` | Merge exhibits into one tabbed, indexed, page-numbered PDF binder |
| `/case-velocity:exhibits` | Attach the exhibits a certification or affirmation refers to: matched to the files, tabbed, merged behind it |
| `/case-velocity:extract-data` | Extract structured financial and personal data from uploaded documents |
| `/case-velocity:fill-form` | Fill a PDF form from source documents in your workspace |
| `/case-velocity:hyperlink` | Hyperlink every case, statute and rule citation in a .docx |
| `/case-velocity:intake` | Process a real estate contract and rider for a new transaction |
| `/case-velocity:license` | Show your LVAI Pro license: licensee, seat, plan, expiry and status |
| `/case-velocity:prepare-rider` | Generate a buyer's or seller's contract rider (NJ or NY) |
| `/case-velocity:research` | Research case law on a legal issue with verified citations |
| `/case-velocity:title-review` | Review a title binder or commitment and generate the closing package |
| `/case-velocity:verify` | Verify citations and legal claims in a brief or memorandum |

LVAI Pro's research and citation checks read the actual court opinions through the firm's own **Midpage** or **Descrybe**
connector (connect one in Claude: Customize → Connectors → Discover). With both connected, every authority is cross-checked on both.

## What the plugin runs, sends and fetches

So that you can see exactly what happens with your data:

- **The connector reads from Case Velocity:** your firm's open cases, the requests attorneys made on the site, drafting
  steps, team chat messages addressed for review, and documents kept on the site. It returns only your own firm's records.
- **The connector writes to Case Velocity:** proposals for the attorney to review (case updates found in email and
  calendar, tasks from team chat), records of emails and notes filed into case folders, calendar copies, finished drafts and
  their file links, team chat messages the attorney asks Claude to send, and reminders. Nothing in the connector deletes data.
- **Claude uses your own connectors, under your own sign-in:** Gmail and Google Calendar are read to find case updates;
  Google Drive is used to create case folders and save copies of case emails and notes into them. Claude sends an email or a
  Slack message only when an attorney wrote it on the site and pressed Send. Web mail (Outlook on the web, Yahoo and others)
  is only ever read, never written. Claude never files or serves anything with a court.
- **Draft files** (Word and PDF) are uploaded through a one-time link that Case Velocity issues for that request, into the
  case's own Google Drive folder.
- **LVAI Pro** (included with a paid Case Velocity subscription): the connector also returns licensed legal-skill
  instructions, reference files, document templates, blank government forms and build scripts. The build scripts (Python or
  shell, for verification reports and exhibit binders) are run by Claude in its own workspace to assemble documents; they do
  not contact any server. Case law is read through the firm's own Midpage or Descrybe connector.
- **Nothing is read from your Claude conversations, memory or chat history.**

Case Velocity's privacy policy: https://casevelocity.ai/privacy · Terms: https://casevelocity.ai/terms

## Help

Documentation: https://casevelocity.ai/help · Support: admin@legalvelocity.ai
