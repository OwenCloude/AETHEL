# AETHEL

Support & Report Desk  
NathanFCS Studio

---

## Overview

AETHEL is a lightweight support and report system for Minecraft servers.

Players submit questions through `/ask` and report suspicious players through `/report`.  
Staff handle active questions through a simple queue. Reports are stored separately for review.

Built to stay clean, practical, and easy to use.

---

## Compatibility

- Minecraft Java Edition: 1.19.x – 1.21.11
- Paper / Spigot 1.19+
- Skript 2.8+

Bedrock players are supported through Geyser / Floodgate.

---

## Installation

1. Place `aethel.sk` inside `plugins/Skript/scripts/`
2. Run `/sk reload aethel`
3. Assign `aethel.team` to your staff and helper groups

---

## Permission

`aethel.team` — Grants access to all staff commands.

---

## Commands

### Player
| Command | Description |
|---|---|
| `/ask <message>` | Submit a question to the staff team |
| `/report <player> <reason>` | Report a player |

### Staff
| Command | Description |
|---|---|
| `/ae queue` | View active ask tickets |
| `/ae claim <id>` | Claim an ask ticket |
| `/ae reply <id> <message>` | Reply to a ticket and close it |
| `/ae info <id>` | View ticket details |
| `/ae report list` | View active reports |

### General
| Command | Description |
|---|---|
| `/ae help` | View command list |
| `/ae credits` | View credits |

`/aethel` is an alias for `/ae`

---

## How It Works

### Ask Tickets
- Players submit a question with `/ask <message>`
- Staff view open asks through `/ae queue`
- A ticket must be claimed before it can be answered
- Replying with `/ae reply` automatically closes the ticket
- Players cannot open a second ask while one is still active
- If the player goes offline, the ticket is closed automatically

### Reports
- Players report others with `/report <player> <reason>`
- Multiple reports against the same target are merged into one entry
- Staff review reports through `/ae report list`
- Reports expire automatically after 30 minutes

---

## Features

- Separate ask and report handling
- Claim system prevents two staff from handling the same ticket
- Reply automatically closes the ticket
- Ticket auto-closes if the asking player leaves the server
- Duplicate report merging
- Staff notification sound on every new ticket
- All tickets reset on server restart
- Cooldowns:
  - `/ask` → 20 seconds
  - `/report` → 60 seconds

---

## Configuration

```sk
options:
    p: &6AETHEL &8• &7
    l: &8&m----------------------------------------
    perm: aethel.team
    askcd: 20 seconds
    reportcd: 60 seconds
    reportttl: 30 minutes
    snd: entity.experience_orb.pickup
    ver: 1.4.1
```

---

## License
MIT License

Copyright (c) 2026 NathanFCS Studio

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.