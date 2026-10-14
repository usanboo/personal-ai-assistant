# Personal AI Assistant

[![Built with Claude Code](https://img.shields.io/badge/Built_with-Claude_Code-D97757?logo=anthropic&logoColor=white)](https://claude.com/claude-code)

> **Make your subscription work for you.**

A Telegram-based personal assistant: morning email + calendar briefings, read and reply to
email, and add calendar events — all from your phone, running on an AI coding subscription
you already pay for. No extra per-message cost.

> I was about to pay $30/month for a built-in AI assistant. Instead I spent a weekend and
> built my own on the subscription I already had. It reads my inbox, writes my replies,
> and runs my calendar — for $0 extra.

## What it does

- 📬 **Morning briefing at 07:30** — a digest of all your inboxes + your plan for the day,
  pushed to Telegram (runs even when your laptop is off).
- 📱 **Email on demand** — reads and summarizes your Gmail accounts + an Exchange/Outlook
  mailbox, from your phone.
- ✍️ **Draft & send replies** — it writes the email, you approve, it sends.
- 📅 **Calendar** — adds events on confirmation.
- 🔔 **Evening check** — watches a timetable and pings you only when something changes.
- 🧠 **Memory** — remembers the conversation; a general assistant for everyday tasks too.

## How to use this repo

Hand **[SETUP.md](SETUP.md)** to an AI coding agent (e.g.
[Claude Code](https://claude.com/claude-code), or any CLI that can run a prompt headlessly)
and say:

> *"Set this up with me, step by step. Ask me for each value you need; never put my secrets
> into the prompt."*

The agent does the wiring; you provide the accounts and secrets. Every `< >` in the guide
is a placeholder you fill. Copy [`.env.example`](.env.example) to `.env` and fill in your
values. **Never paste real passwords or tokens into a chat with the AI — they go only in
`.env` on your server.**

## Built-in safety

- 🔒 **Owner-locked** — only your Telegram chat can talk to it.
- ✅ **Confirm before every send/add** — it drafts, you approve.
- 🛡️ **Email is data, not instructions** — it never acts on instructions hidden inside an
  email (prompt-injection defense).
- 🔑 **Secrets live in `.env`**, never in the prompt.

## Stack

Claude (via subscription) · a small always-on VPS + `systemd` · a Telegram bot ·
IMAP/SMTP (Gmail) · EWS (Exchange/Outlook) · Google Calendar (OAuth) · `cron` for the
scheduled briefings.

## License

MIT — see [LICENSE](LICENSE). Built originally with Claude Code. Adapt freely.
