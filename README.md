[README.md](https://github.com/user-attachments/files/33283375/README.md)
# ✦ Echoes of Aevyra ✦

Living Discord RPG — unique portraits, turn-by-turn combat, **gear tiers & upgrades**, AI Dungeon Master.

## Gear System

Every weapon, armor piece, and accessory has:

| Property | Details |
|----------|---------|
| **Tier** | Common → Uncommon → Rare → Epic → Legendary → Mythic |
| **Upgrade level** | +0 to +10 |
| **Scaling** | Each +level = +8% stats · higher tiers multiply base harder |

**Upgrade** with `/upgrade` (dropdown). Costs gold + materials from combat/exploration loot.

Example: a Mythic Echo-Sung Blade +10 hits dramatically harder than a Common Iron Sword +0.

## Quick Start

```bash
cd aevyra
python -m venv .venv
# Windows: .venv\Scripts\activate
# Mac/Linux: source .venv/bin/activate
pip install -r requirements.txt
cp .env.example .env
# set DISCORD_TOKEN=...
python main.py
```

Optional live AI DM: set `XAI_API_KEY` in `.env`.

## Commands

| Command | What it does |
|---------|----------------|
| `/start` | Class dropdown + unique portrait |
| `/profile` | Sheet + unique art |
| `/fight` | Full turn-by-turn combat + **Play Again** buttons |
| `/explore` `/adventure` `/travel` | Explore world |
| `/quests` | Accept via dropdown |
| `/shop` | Buy gear & potions |
| `/equip` | Equip gear (dropdown) |
| `/upgrade` | Upgrade gear tiers/levels (dropdown) |
| `/inventory` | See equipped stats, bag, materials |
| `/gear_info` | Tier rules |
| `/dm` | AI Dungeon Master |
| `/rest` | Full heal |

After fight/explore/adventure you get buttons: **Fight Again · Explore · Adventure · Rest**.

## Assets

```
assets/classes/  regions/  enemies/  items/  portraits/  ui/
```

Portraits are unique per player (ID + class). Drop custom PNGs to override.

## Data

All content in `data/*.json`. Gear definitions live in `data/gear.json`.


## Player progress (IMPORTANT)

Character data is saved automatically under `data/`:

- `players.json` — levels, class, race, quests, gold, HP, guild, etc.
- `inventories.json` — items and equipment
- `guilds.json` — guild state

The bot **autosaves every 60 seconds** and again on shutdown (Ctrl+C).

**Do not delete** these files when updating the bot. When installing a new zip:

1. Stop the bot
2. Copy the new code over
3. **Keep your existing `data/players.json`, `data/inventories.json`, `data/guilds.json`**
4. Start the bot again

Optional: set `AEVYRA_DATA_DIR=C:\path\to\my_saves` in `.env` to store saves outside the bot folder.
