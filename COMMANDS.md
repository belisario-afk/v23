# HoodWars Plugin Commands Reference

A comprehensive guide to all chat and console commands across the HoodWars plugin suite.

---

## 📋 Table of Contents

1. [HoodWars.cs - Core Gang System](#hoodwarscs---core-gang-system)
2. [GrandmasHouse.cs - Grandma Protection](#grandmashousecs---grandma-protection)
3. [ManualDoor.cs - Door Management](#manualdoorcs---door-management)
4. [DaHoodTags.cs - Player Tags](#dahoodtagscs---player-tags)
5. [DriveBySedanGangs.cs - Gang Vehicles](#drivebysedangangscs---gang-vehicles)
6. [GangKits.cs - Gang Equipment](#gangkitscs---gang-equipment)
7. [WelcomeScreen.cs - Player Welcome](#welcomescreencs---player-welcome)

---

## HoodWars.cs - Core Gang System

### Chat Commands

| Command | Usage | Description | Permission |
|---------|-------|-------------|------------|
| `/gangname` | `/gangname` | Display your current gang name | Player |
| `/whoami` | `/whoami` | Display your player info and gang status | Player |
| `/hoodadmin` | `/hoodadmin` | Open the admin panel UI | Admin |
| `/testsafezone` | `/testsafezone` | Test if you're in a safe zone | Admin |
| `/testtrespass` | `/testtrespass` | Test if you're trespassing in enemy territory | Admin |
| `/listhoteldoors` | `/listhoteldoors` | List all hotel doors | Admin |
| `/resetgangtc` | `/resetgangtc` | Reset gang TC assignments | Admin |

### Console Commands

| Command | Usage | Description |
|---------|-------|-------------|
| `hood.clear` | `hood.clear` | Clear gang data |
| `hood.refresh` | `hood.refresh` | Refresh gang UI |
| `hood.resetplayer <steamid>` | `hood.resetplayer 76561198...` | Reset a specific player's gang data |
| `hoodwars.admin <action>` | `hoodwars.admin <action>` | Admin control commands |

---

## GrandmasHouse.cs - Grandma Protection

### Chat Commands

| Command | Usage | Description | Permission |
|---------|-------|-------------|------------|
| `/gspawn` | `/gspawn` | Spawn grandmas at all HQ locations | Admin |
| `/gclear` | `/gclear` | Remove all spawned grandmas | Admin |
| `/cleargrandma` | `/cleargrandma` | Alias for `/gclear` | Admin |
| `/spawngrandma <gang>` | `/spawngrandma Pirus` | Spawn grandma for a specific gang at your location | Admin |
| `/spawnmom <gang>` | `/spawnmom Vagos` | Spawn mom for a specific gang at your location | Admin |
| `/killgrandma [gang]` | `/killgrandma` or `/killgrandma Surenos` | Kill all grandmas or a specific gang's grandma | Admin |
| `/gzone <action>` | `/gzone list` | Manage grandma zones (see subcommands below) | Admin |
| `/gzoneset <gang> [radius]` | `/gzoneset Pirus 25` | Set a grandma zone at your position | Admin |
| `/gtoggleSpheres` | `/gtoggleSpheres` | Toggle visibility of grandma zone spheres | Admin |

### /gzone Subcommands

| Subcommand | Usage | Description |
|------------|-------|-------------|
| `list` | `/gzone list` | Show all 4 gang zones and their status |
| `info` | `/gzone info` | Show which zone you're currently in |
| `remove <gang>` | `/gzone remove Pirus` | Remove a gang's zone |

### Gang Name Shortcuts

You can use these shortcuts instead of full gang names:
- `Pirus` → Westside Pirus
- `Vagos` → Northside Vagos
- `Surenos` → Southside Sureños
- `Disciples` → Eastside Disciples

---

## ManualDoor.cs - Door Management

### Chat Commands - Door Spawning

| Command | Usage | Description | Permission |
|---------|-------|-------------|------------|
| `/spawndoor` | `/spawndoor` | Spawn a metal door at your position | Admin |
| `/spawndoubledoor` | `/spawndoubledoor` | Spawn a metal double door | Admin |
| `/spawngaragedoor` | `/spawngaragedoor` | Spawn a garage door | Admin |
| `/spawnarmoreddoor` | `/spawnarmoreddoor` | Spawn an armored door | Admin |
| `/spawnarmoreddoubledoor` | `/spawnarmoreddoubledoor` | Spawn an armored double door | Admin |

### Chat Commands - Grandma Door Spawning (with auto-codelock)

| Command | Usage | Description | Permission |
|---------|-------|-------------|------------|
| `/spawngrandmadoor <gang>` | `/spawngrandmadoor Pirus` | Spawn armored door with locked codelock for gang | Admin |
| `/spawngrandmagaragedoor <gang>` | `/spawngrandmagaragedoor Vagos` | Spawn garage door with locked codelock for gang | Admin |
| `/spawngrandmametaldoor <gang>` | `/spawngrandmametaldoor Surenos` | Spawn metal door with locked codelock for gang | Admin |
| `/spawngrandmametaldoubledoor <gang>` | `/spawngrandmametaldoubledoor Disciples` | Spawn metal double door with locked codelock for gang | Admin |
| `/spawngrandmaarmoreddoubledoor <gang>` | `/spawngrandmaarmoreddoubledoor Pirus` | Spawn armored double door with locked codelock for gang | Admin |

### Chat Commands - Door Management

| Command | Usage | Description | Permission |
|---------|-------|-------------|------------|
| `/removedoor` | `/removedoor` | Remove the door you're looking at | Admin |
| `/claimdoor <gang>` | `/claimdoor Pirus` | Assign door to a gang (adds codelock) | Admin |
| `/dooredit` | `/dooredit` | Enter door edit mode (move/rotate) | Admin |
| `/doorinfo` | `/doorinfo` | Show info about the door you're looking at | Admin |
| `/resetdoor` | `/resetdoor` | Reset door ownership | Admin |

### Chat Commands - Sphere Management

| Command | Usage | Description | Permission |
|---------|-------|-------------|------------|
| `/addsphere [radius]` | `/addsphere 5` | Add a sphere marker to a door (default radius: 5) | Admin |
| `/removesphere` | `/removesphere` | Remove sphere from door | Admin |

### Chat Commands - Layout Management

| Command | Usage | Description | Permission |
|---------|-------|-------------|------------|
| `/savelayout <name>` | `/savelayout hotel1` | Save current doors as a layout | Admin |
| `/listlayouts` | `/listlayouts` | Show all saved layouts | Admin |
| `/spawnlayout <name>` | `/spawnlayout hotel1` | Spawn at EXACT saved world positions | Admin |
| `/spawnlayoutoffset <name>` | `/spawnlayoutoffset hotel1` | Spawn relative to where you look | Admin |
| `/deletelayout <name>` | `/deletelayout hotel1` | Delete a saved layout | Admin |
| `/savegrandmalayout <name> <gang>` | `/savegrandmalayout grandma1 Pirus` | Save grandma doors for specific gang | Admin |
| `/saveallgrandmalayouts <name>` | `/saveallgrandmalayouts allgrandmas` | Save all grandma doors from all gangs | Admin |
| `/movedoors <x> <y> <z>` | `/movedoors 0 1 0` | Move ALL doors by an offset | Admin |

#### Layout Tips
- **`/spawnlayout`** - Use this when your saved layout needs to be at the exact same map coordinates (same map/wipe)
- **`/spawnlayoutoffset`** - Use this when moving layouts to a new location (different map or new position)
- **RustEdit Alternative**: Doors placed in RustEdit will take damage in-game and work normally

### Console Commands - Door Edit Mode

| Command | Description |
|---------|-------------|
| `mdoor.moveup` | Move door up |
| `mdoor.movedown` | Move door down |
| `mdoor.moveforward` | Move door forward |
| `mdoor.moveback` | Move door backward |
| `mdoor.moveleft` | Move door left |
| `mdoor.moveright` | Move door right |
| `mdoor.rotateleft` | Rotate door left |
| `mdoor.rotateright` | Rotate door right |
| `mdoor.step1` | Set move increment to 0.1 |
| `mdoor.step2` | Set move increment to 0.5 |
| `mdoor.step3` | Set move increment to 1.0 |
| `mdoor.step4` | Set move increment to 2.0 |
| `mdoor.rot1` | Set rotation increment to 1° |
| `mdoor.rot2` | Set rotation increment to 5° |
| `mdoor.rot3` | Set rotation increment to 15° |
| `mdoor.rot4` | Set rotation increment to 45° |
| `mdoor.close` | Exit door edit mode |

---

## DaHoodTags.cs - Player Tags

### Chat Commands

| Command | Usage | Description | Permission |
|---------|-------|-------------|------------|
| `/tag` | `/tag` | Open the tag selection UI | Player |
| `/tagtest` | `/tagtest` | Test your current tag display | Admin |
| `/tagstats` | `/tagstats` | Show tag statistics | Admin |
| `/covertag` | `/covertag` | Toggle covert mode (hide your tag) | Player |

### Console Commands

| Command | Usage | Description |
|---------|-------|-------------|
| `tag.select <id>` | `tag.select 5` | Select a tag by ID |
| `tag.close` | `tag.close` | Close the tag UI |

---

## DriveBySedanGangs.cs - Gang Vehicles

### Chat Commands

| Command | Usage | Description | Permission |
|---------|-------|-------------|------------|
| `/sedandebug` | `/sedandebug` | Toggle sedan debug mode | Admin |
| `/stalksedan` | `/stalksedan` | Start tracking sedan positions | Admin |
| `/destroysedan` | `/destroysedan` | Destroy the sedan you're looking at | Admin |

---

## GangKits.cs - Gang Equipment

### Chat Commands

| Command | Usage | Description | Permission |
|---------|-------|-------------|------------|
| `/testallkits` | `/testallkits` | Test all gang kit loadouts | Admin |

---

## WelcomeScreen.cs - Player Welcome

### Chat Commands

| Command | Usage | Description | Permission |
|---------|-------|-------------|------------|
| `/welcome` | `/welcome` | Show the welcome screen | Player |
| `/info` | `/info` | Show the server info screen | Player |

### Console Commands

| Command | Description |
|---------|-------------|
| `welcomescreen.close` | Close the welcome screen |
| `welcomescreen.showinfo` | Show the info panel |
| `welcomescreen.showwelcome` | Show the welcome panel |
| `welcomescreen.reload` | Reload welcome screen config |

---

## Quick Reference by Category

### 🏠 Grandma System
```
/gzoneset <gang> [radius]  - Set zone at your position
/gzone list                - List all zones
/spawngrandma <gang>       - Spawn grandma
/killgrandma [gang]        - Kill grandma(s)
/gtoggleSpheres            - Toggle zone visibility
```

### 🚪 Door Spawning
```
/spawngrandmadoor <gang>           - Armored door with codelock
/spawngrandmagaragedoor <gang>     - Garage door with codelock
/spawngrandmametaldoor <gang>      - Metal door with codelock
/spawngrandmaarmoreddoubledoor <gang> - Armored double with codelock
```

### 🔧 Door Management
```
/dooredit        - Enter edit mode
/doorinfo        - View door info
/removedoor      - Remove door
/claimdoor <gang> - Assign to gang
/resetdoor       - Reset ownership
```

### 💾 Layout Management
```
/savelayout <name>              - Save doors
/spawnlayout <name>             - Spawn layout
/listlayouts                    - List layouts
/saveallgrandmalayouts <name>   - Save all grandma doors
```

### 👤 Player Commands
```
/whoami      - Show your gang info
/gangname    - Show your gang name
/tag         - Select your tag
/welcome     - Show welcome screen
```

### 🛡️ Admin Panel
```
/hoodadmin   - Open admin panel UI
```

---

## Notes

1. **Permissions**: Most commands require admin permissions. Player commands are available to all players.

2. **Gang Names**: Use shortcuts (Pirus, Vagos, Surenos, Disciples) instead of full names.

3. **Door Codelocks**: Grandma doors automatically get codelocks with code "1337". Gang members can open without entering the code.

4. **C4 Rewards**: When a grandma is killed, the killer's gang receives C4 rewards.

5. **Zones**: Grandma zones persist until explicitly removed. They don't change when grandmas spawn or die.
