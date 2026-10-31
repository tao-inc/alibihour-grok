# Alibi Hour Mystery Game

A daily mystery game for Grok Bot: a non-violent whodunit. Something has gone missing, there are four suspects and six ten-minute times, and one suspect, the culprit, lies in every answer. Everyone gets the same case each day, and a new one opens at 00:00 UTC.

- **Ask** where a suspect was at a time, in your own words ("Where was Ben at 8:30?") or by tapping a square in the card. Each answer comes word for word from the case stored on Alibi Hour's server. You have 10 questions.
- **Catch the liar.** Three suspects tell the truth; the culprit's story can't fit with theirs. Grok never sees a statement you didn't ask for, or the culprit, while the case is open.
- **Accuse.** The accusation is final. A solver says whether your answers proved it ("proven") or you got lucky, shows par (the fewest questions that prove it) and how you did against everyone who played that day.
- **Party mode** runs a fresh case for friends in one room: up to four guests take a suspect's private sheet on their phone, everyone else joins as a detective, and everyone votes.

The card is an MCP App that works inline within 800 px: the room map, the four suspects, a timeline to tap, your answers so far and, once you accuse, the full solution.

## Your detective code

Grok doesn't tell apps who you are, so Alibi Hour gives you a **detective code** (for example `AH-7Q3K9M`) the first time you open a case, shown in the card. Grok passes it with each question. To continue your case or streak in a new conversation or on another day, say "My Alibi Hour detective code is AH-…". We store only a scrambled form of it. Keep it to yourself: it is the only key to your record.

## Sample prompts

- "Use Alibi Hour to open today's mystery."
- "Use Alibi Hour to ask Ben where he was at 8:30."
- "Use Alibi Hour to accuse Cleo."
- "Use Alibi Hour to start a mystery party for four friends."
- "Use Alibi Hour to show my streak. My detective code is AH-7Q3K9M."

## Tools

| Tool | What it does | What it changes |
|---|---|---|
| `show_daily_case` | Opens today's case file in the card; gives a new detective code when called without one | Nothing |
| `ask_suspect` | One suspect's statement for one time, word for word; uses one of 10 questions | Adds the question to your case |
| `accuse_suspect` | Your one final accusation; reveals the culprit, every statement and par | Ends your case for the day |
| `show_case_results` | An earlier day's solution (last 30 days) | Nothing |
| `get_my_stats` | Streak, cases solved and proven, the last 7 cases | Nothing |
| `create_share_link` | A public link to your result (no culprit until the case closes) and paste-ready text | Publishes a share page |
| `delete_my_data` | Deletes your questions, accusations, streak, share links and parties | Deletes your data |
| `start_party` | A fresh party case with a join link, QR code and 4-letter code | Creates a party (deleted 24 h after its last activity) |
| `get_party` | Which sheets are taken and how many have voted | Nothing |
| `reveal_party` | Closes voting and reveals the culprit on every phone | Ends voting |
| `end_party` | Deletes the party; its link stops working | Deletes the party |

Grok asks before running a tool that changes something.

## Server

`mcp.json` connects Grok Bot to `https://alibihour.ambientapp.ai/mcp/grok` (Streamable HTTP, no sign-in). Grok can't see what you tap inside the card; your questions are kept on the server, so the next time the case is opened they are all there.

## Install

- **Grok Bot:** once the plugin is listed, add it from Connect apps. Until then, tell Grok Bot "Add this MCP server: https://alibihour.ambientapp.ai/mcp/grok".
- **Grok CLI:** `grok plugin install tao-inc/alibihour-grok --trust`

## Privacy, terms and support

Alibi Hour keeps your questions, accusations, streak, share links and parties under a scrambled form of your detective code; it receives no name, email or user ID. Technical logs (never statements, suspects, codes or IP addresses) are kept for 30 days. Every case is fiction with no violence. No ads, no payments, no AI-generated media. For adults (Grok users are 18+).

- Documentation: https://alibihour.ambientapp.ai/docs
- Privacy policy: https://alibihour.ambientapp.ai/privacy
- Terms: https://alibihour.ambientapp.ai/terms
- Support: https://alibihour.ambientapp.ai/support · support@theopenapps.com

Made by The Open Apps, Inc. This repository holds only the plugin configuration (MIT); the server is operated by The Open Apps, Inc.
