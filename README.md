> Official release page for AETHEL — a lightweight support and report desk built for modern Paper/Spigot environments.

# AETHEL v1.4.1
by NathanFCS Studio

AETHEL is a lightweight support and report desk for Paper/Spigot servers using Skript.

Built for server teams that want a clean way to handle player questions and reports without relying on larger helpdesk plugins or unnecessary systems.

---

## Overview

AETHEL focuses on two core systems:

- Ask ticket queue
- Player report list

Questions are handled through a simple ticket flow:
players submit a question, staff claim it, reply, and the ticket closes automatically.

Reports are stored separately in a dedicated report list for staff review.

This project is designed for server owners who want a practical internal support system that stays lightweight and easy to maintain.

---

## Requirements

- Paper or Spigot **1.19+**
- Skript **2.8+**

Bedrock players are supported through Geyser / Floodgate.

---

## Installation

1. Place `aethel.sk` in `plugins/Skript/scripts/`
2. Run `/sk reload aethel`
3. Done

---

## Commands

### Staff Only
Permission node: `aethel.team`

| Command | Description |
|---|---|
| `/ae queue` | View active ask tickets |
| `/ae claim <id>` | Claim an ask ticket |
| `/ae reply <id> <message>` | Reply to a ticket and close it |
| `/ae info <id>` | View ticket details |
| `/ae report list` | View active reports |
| `/ae help` | View command list |
| `/ae credits` | View credits |

Alias: `/aethel`

### All Players

| Command | Description |
|---|---|
| `/ask <message>` | Submit a question to the staff team |
| `/report <player> <reason>` | Report a player |

---

## Ask Ticket System

- Players can only keep **one active ask** at a time
- Staff must **claim** a ticket before replying
- Replying to a ticket **closes it automatically**
- Ask tickets close automatically if the **player goes offline**
- If the handling staff member disconnects, the **claim is released**

---

## Report System

- Reports against the same target are **merged into one entry**
- Staff review reports through `/ae report list`
- Reports are **read-only** and handled separately from ask tickets
- Reports **expire automatically** after the configured report lifetime

---

## Cooldowns

| Command | Cooldown |
|---|---|
| `/ask` | 20 seconds |
| `/report` | 60 seconds |

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

## Changelog

```text
v1.0 - initial release
     - /ask and /report system
     - basic staff notification with sound
     - unified ticket queue
     - /ae help and /ae credits

v1.1 - feature update
     - auto-close tickets after 24h of inactivity
     - /ae info <id> command
     - clickable text in queue

v1.2 - visual update
     - gold accent prefix and styling
     - cleaner message formatting
     - minor bug fixes

v1.3 - bug fix release
     - fixed /report not functioning
     - fixed /ae reply always showing recipient offline
     - fixed /ae queue not displaying ticket details
     - fixed players being able to submit multiple asks
     - fixed claim overlap between staff members

v1.4 - system rework
     - separated ask and report handling
     - added /ae report list
     - removed /ae close, reply now auto-closes tickets
     - ask tickets auto-close when player goes offline
     - claim automatically released when staff disconnects

v1.4.1 - stability update
       - all tickets reset on server restart
       - UUID-based player and staff tracking
       - minor stability improvements
```
---

## Planned

- [ ] Optional persistent storage
- [ ] Optional Discord webhook logging
- [ ] Optional report detail expansion
- [ ] Additional staff-facing quality of life improvements

---

## License

This project is licensed under the MIT License.

---

## Notes

- This is a Skript resource, not a standalone .jar plugin
- Designed for Paper/Spigot-based servers
- Lightweight and easy to maintain
- Official links are provided below for safety and authenticity

---

## Official Links

### Profiles
- **GitHub:** https://github.com/OwenCloude
- **SpigotMC Profile:** https://www.spigotmc.org/members/nathanfcs.2521802/
- **skUnity Profile:** https://forums.skunity.com/members/nathanfcs.40131/
- **Modrinth Profile:** https://modrinth.com/user/NTHFCS

### Resource Pages
- **SpigotMC:** https://www.spigotmc.org/resources/aethel.134969/
- **skUnity:** Coming Soon

### Community
- **Discord:** https://discord.gg/V8dpGdsMeT

---

## Maintained By

**NathanFCS Studio**  
Releases • Support • Product Development
