# Meeting Recall

A [Claude Code](https://docs.claude.com/en/docs/claude-code) plugin that answers questions about your past meetings by querying your local [Meetily](https://github.com/Zackriya-Solutions/meeting-minutes) database.

Ask things like *"what did we decide about billing?"*, *"action items from last week's call"*, or *"summarize the meeting on 2026-05-18"* and Claude pulls the relevant excerpts from your local transcripts and summaries, cited by meeting title and date.

Everything runs **locally and read-only** — no network calls, no writes to the database.

## Requirements

- [Claude Code](https://docs.claude.com/en/docs/claude-code)
- [Meetily](https://github.com/Zackriya-Solutions/meeting-minutes) installed, with recorded meetings in its SQLite DB at:
  `~/Library/Application Support/com.meetily.ai/meeting_minutes.sqlite` (macOS)
- `sqlite3` on your `PATH` (ships with macOS)

## Install

From within Claude Code, add this repo as a plugin marketplace / plugin source:

```
/plugin marketplace add nickmaglowsch/meeting-recall
/plugin install meeting-recall
```

Or clone it into your Claude plugins directory and enable it via `/plugin`.

## Usage

Just ask Claude about your past meetings. The `meeting-recall` skill triggers on phrases like:

- "what did we decide about X"
- "what we'll do on ticket X / feature X"
- "summarize the meeting on \<date\>"
- "find the meeting where we discussed X"
- "action items from \<topic\>"
- "what was said about X"

## What it does NOT do

- Take notes, schedule meetings, or modify the database (read-only)
- Transcribe live audio (Meetily handles that)
- Identify speakers (Meetily's speaker labels are unreliable / mostly empty)
- Semantic search (keyword search only)

## License

MIT — see [LICENSE](LICENSE).
