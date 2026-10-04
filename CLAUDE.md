# CLAUDE.md — web3-wargame

Orientation for a Claude session started in this directory. (`README.md` is one
line: "Just a Fun Game to test best security practices".)

## What this is

"**Approve & Pray**" — a browser wargame that teaches Web3 security by making the
player walk into (simulated) wallet traps and learn to spot them. Part of the
CryptoShields education suite alongside `malware-simulation`.

- **Owner / identity:** CryptoShields (`realcryptoshields@gmail.com`) — resolves
  from the `github-cryptoshields` remote. GitHub: `cryptoshields/web3-wargame`.

## Layout

| File | Role |
|---|---|
| `index.html` | Entry / intro |
| `level1.html` | ERC-20 Approval Trap |
| `level2.html` … `level4.html` | Further levels |
| `leaderboard.html` | Shared leaderboard |
| `kasia-derenda-*.jpg` | Background image |

## Stack

Static HTML, no build. Each level pulls two libraries from CDN:
- **ethers 5.7.2** (`ethers.umd.min.js`) — wallet interaction / simulated traps
- **@supabase/supabase-js v2** — leaderboard persistence (Supabase project;
  anon key is inline in the pages)

## Working rules

- Edit HTML directly, open to test. Levels are self-contained.
- The traps must stay **simulated** — the point is recognising a malicious
  `approve` / signature request, not executing a real one.
- If adding a level, wire it into `index.html` and the leaderboard's level list.
