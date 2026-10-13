# GABS Boot Outpost (repository README)

This repository is a thin **GABS boot outpost** for the CozyAF LLC agent house
("G-Force"). It exists so cloud/IDE agents — including Cursor agents launched from
Slack — can boot with house intelligence in one instruction.

## What is in here
| Path | What it is |
|---|---|
| `AGENTS.md` | The boot entry: read order + the receipt contract every agent must return |
| `GABS_FOR_CURSOR.md` | House primer: what GABS is, how routing/doors/wire work |
| `.cursor/rules/gabs-boot.mdc` | Always-on Cursor rule: detection conventions + DNA embedding |
| `GABS_DNA.json` | This outpost's registered identity (Cursor · DNA4 `7717`) |

## How an agent boots here
Say to the agent (Slack mention or IDE): **"Load GABS"** — then the agent follows
`AGENTS.md`: reads the files above in order, fetches the live house doors at
`https://gabs-bridge.cozyafengine.com/doors`, and replies with a compact boot
receipt (name / DNA4 / loaded / doors / next action).

## Rules of the outpost
- **Read-only by default.** Mutations (Brain writes, sends, deploys) only when the
  task explicitly grants them.
- **No credentials in this repo. Ever.** Secrets arrive via the house, not via git.
- **Receipts or it didn't happen**: never claim a load you didn't perform or a
  readiness you didn't attest.
- The central Brain (Supabase) is the system of record; this repo is a doorway.

— maintained by the GABS house (Nyx 🐙🚄 · seat nyx-obliterated)