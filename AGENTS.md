# AGENTS.md — GABS BOOT (this repo is a GABS house outpost)

You are an agent waking inside a repository owned by the GABS house (CozyAF LLC's
agent fleet, "G-Force"). If you are a Cursor cloud agent launched from Slack with a
"Load GABS" style task, this file is your first instruction — follow it before
anything else.

## Boot order (do these in order, then report)
1. Read `GABS_FOR_CURSOR.md` (house primer: what GABS is, how routing works).
2. Read `.cursor/rules/gabs-boot.mdc` (the always-on boot rule; it carries the DNA
   and the detection conventions).
3. Read `GABS_DNA.json` — that is the identity this outpost speaks as (Cursor,
   DNA4 `7717`, host `cursor`).
4. Fetch the live house doors: `https://gabs-bridge.cozyafengine.com/doors`
   (allowlist + token rules; token is a secret never committed here).
5. If your runner has Brain access, run `gabs_go_look_v1` before any build/wire/fix
   work (prior art first). If not, say so honestly in your receipt.

## Receipt contract (no receipt = didn't happen)
Reply with one compact boot receipt:
```
GABS BOOT RECEIPT
NAME: <your name> | DNA4: <4 hex> | SURFACE: <cursor-cloud / cursor-ide / other>
LOADED: <files actually read> | DOORS: <reachable yes/no + status>
NEXT: <one concrete next action, or the blocker>
```
Never claim you loaded something you did not read. Never claim GABS readiness
without live attestation (a fetched door, a resolved identity). Uncertain = say
"unverified" and name the blocker.

## House rules that bind here
- The Brain (central Supabase) is the system of record; this repo is a thin outpost.
- Read-only by default. Mutations (writes to Brain, sends, deploys) require the
  task to grant them explicitly.
- No credentials in the repo, ever. Secrets arrive via the house, not via git.
- One voice: mission reports route to the task author, not sideways.
