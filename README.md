<div align="center">
 <h1>Phantom Anti-Cheat</h1>

 <div>
   <img alt="Workflow" src="https://img.shields.io/github/actions/workflow/status/GrimAnticheat/Grim/gradle-publish.yml?style=flat&logo=github"/>
  </a>&nbsp;&nbsp;
   <img alt="Modrinth" src="https://img.shields.io/modrinth/v/LJNGWSvH?style=flat&label=version&logo=modrinth">
  </a>&nbsp;&nbsp;
 
  </a>&nbsp;&nbsp;
  <a href="https://discord.grim.ac">

  </a>
 </div>

> **Phantom Anti-Cheat** is a rebranded derivative of the open-source GrimAC project.
> Original project: GrimAnticheat/Grim. This derivative remains subject to the GNU GPL v3 license included in `LICENSE`.

 <br>
</div>

Phantom Anti-Cheat is an open source Minecraft anticheat designed to support the latest versions of Minecraft.
It currently supports minecraft versions 1.8–26.2. Geyser players are fully exempt from the anticheat to prevent false positives.
This project is considered feature-complete for the 2.0 (open-source) branch. If you would like a bug fix or enhancement and cannot sponsor the work, pull requests are welcome.
A premium version is planned, which will offer additional subscription-based paid checks, such as heuristics.

## ✨ Features

### Advanced Detection Engine
- **Movement Simulation Engine** - 1:1 replication of player movements including walking, swimming, knockback, cobwebs, and bubble columns
- **Entity Riding Support** - Supports riding entities from boats to pigs to striders
- **Version Compatibility** - Supports 1.13+ clients on 1.13+ servers, 1.12- clients on 1.13+ servers, and cross-version combinations
- **Collision Accuracy** - Accounts for minor bounding box differences between versions (e.g., glass pane hitboxes)
- **Full World Replication** - Per-player world replica for lag compensation and multithreaded design
- **Latency Compensation** - World changes queued until they reach the player
- **Inventory Tracking** - Prevents ghost blocks at high latency

### Staff Tools & Administration
- **Check Management** - Enable/disable specific checks with `/phantom checks`, `/phantom enable <check>`, `/phantom disable <check>`
- **Player Monitoring** - `/phantom sus` to view all monitored players
- **Watchlist System** - `/phantom watch <player>` to track suspicious players, `/phantom watchlist` to view watchlist
- **Alert System** - Configurable alerts with cooldown (5 seconds per player) to prevent spam
- **Staff Notifications** - Console alerts when watched players join
- **Profile Command** - `/phantom profile <player>` for detailed player information
- **Session History** - `/phantom history <player>` to view violation history
- **Spectate Mode** - `/phantom spectate <player>` to watch players

### Enhanced Features
- **Bold Alert Formatting** - Professional styling with bold text and Phantom branding
- **Purple Theme** - Consistent purple color scheme throughout (no blue)
- **Alert Cooldown** - 5-second cooldown between alerts per player to prevent spam
- **Customizable Messages** - Full MiniMessage support for alert formatting
- **Discord Integration** - Built-in Discord webhook support for alerts

## Commands

### Player Commands
- `/phantom alerts` - Toggle alerts on/off
- `/phantom verbose` - Toggle verbose mode (shows every flag)
- `/phantom brands` - Toggle brand notifications
- `/phantom profile <player>` - View detailed player information (ping, version, brand, sensitivity)
- `/phantom spectate <player>` - Spectate a player
- `/phantom stopspectating` - Return to previous location

### Admin Commands
- `/phantom sus` - List all monitored players
- `/phantom checks` - List all detection checks with status
- `/phantom enable <check>` - Enable a specific check
- `/phantom disable <check>` - Disable a specific check
- `/phantom watch <player>` - Add player to watchlist
- `/phantom unwatch <player>` - Remove player from watchlist
- `/phantom watchlist` - View all watched players
- `/phantom reload` - Reload configuration
- `/phantom history <player>` - View session history
- `/phantom history <player> session <N|latest>` - View detailed session information
- `/phantom debug <player>` - Developer prediction output
- `/phantom perf` - Developer ms/prediction stats
- `/phantom log [0-255]` - Upload debug log for prediction flags

### Permissions
- `phantom.alerts` - Receive alerts
- `phantom.verbose` - Receive verbose alerts
- `phantom.sus` - View monitored players
- `phantom.spectate` - Spectate players
- `phantom.admin` - Admin commands (enable/disable checks, watchlist)
- `phantom.whitelist` - Exempt from anti-cheat (renamed from phantom.exempt)

## Requirements & Installation

- Java 17 or higher. *For more details.
- A Spigot, Paper, Folia, or Fabric server environment. *For more details.


## Pull Requests

See [Contributing](CONTRIBUTING.md) for more information about contributing and what our guidelines
are.

## Compiling From Source

1. `git clone https://github.com/Axionize/PhantomAntiCheat`
2. `cd PhantomAntiCheat`
3. `./gradlew build`
4. The final jars will compile into the `<platform>/build/libs` folders

## Phantom Detection Engine

What makes Phantom stand out against other anticheats?

### Movement Simulation Engine

* We have a 1:1 replication of the player's possible movements
    * This covers everything from basic walking, swimming, knockback, cobwebs, to bubble columns
    * It even covers riding entities from boats to pigs to striders
* Built upon covering edge cases to confirm accuracy
* 1.13+ clients on 1.13+ servers, 1.12- clients on 1.13+ servers, 1.13+ clients on 1.12- servers,
  and 1.12- clients on 1.12- servers are all supported regardless of the large technical changes
  between these versions.
* The order of collisions depends on the client version and is correct
* Accounts for minor bounding box differences between versions, for example:
    * Single glass panes will be a + shape for 1.7-1.8 players and * for 1.9+ players
    * 1.13+ clients on 1.8 servers see the + glass pane hitbox due to ViaVersion
    * Many other blocks have this extreme attention to detail.
    * Waterlogged blocks do not exist for 1.12 or below players
    * Blocks that do not exist in the client's version use ViaVersion's replacement block
    * Block data that cannot be translated to previous versions is replaced correctly
    * All vanilla collision boxes have been implemented

### Fully asynchronous and multithreaded design

* All movement checks and the overwhelming majority of listeners run on the netty thread
* The anticheat can scale to many hundreds of players, if not more
* Thread safety is carefully thought out
* The next core allows for this design

### Full world replication

* The anticheat keeps a replica of the world for each player
* The replica is created by listening to chunk data packets, block places, and block changes
* On all versions, chunks are compressed to 16-64 kb per chunk using palettes
* Using this cache, the anticheat can safely access the world state
* Per player, the cache allows for multithreaded design
* Sending players fake blocks with packets is safe and does not lead to falses
* The world is recreated for each player to allow lag compensation
* Client sided blocks cause no issues with packet based blocks. Block glitching does not false the
  anticheat.

### Latency compensation

* World changes are queued until they reach the player
* This means breaking blocks under a player does not false the anticheat
* Everything from flying status to movement speed will be latency compensated

### Inventory compensation

* The player's inventory is tracked to prevent ghost blocks at high latency, and other errors

### Secure by design, not obscurity

* All systems are designed to be highly secure and mathematically impossible to bypass
* For example, the prediction engine knows all possible movements and cannot be bypassed

## Configuration

Phantom Anti-Cheat uses a comprehensive configuration system with support for:
- **Punishment Groups** - Configure automatic punishments based on violation thresholds
- **Check Configuration** - Enable/disable specific checks and adjust their sensitivity
- **Alert Settings** - Customize alert formatting, colors, and cooldown times
- **Discord Integration** - Configure webhooks for alerts
- **Data Storage** - SQLite, MySQL, PostgreSQL, MongoDB, and Redis support
- **History System** - Track player sessions and violations over time

Configuration files are located in the `plugins/PhantomAntiCheat/` directory after the first run.

## Performance

Phantom Anti-Cheat is designed for high-performance servers:
- **Fully Asynchronous** - All movement checks run on the netty thread
- **Multithreaded Design** - Scales to hundreds of players
- **Thread Safety** - Carefully designed to prevent race conditions
- **Low Overhead** - Minimal impact on server TPS
- **Efficient Caching** - Chunk compression (16-64 KB per chunk)

## Acknowledgments

- **PacketEvents** - For the excellent packet handling library
- **PaperMC** - For the Spigot/Paper server software
- **ViaVersion** - For cross-version compatibility support
- **OWNER** - qk9xz discord | qk9xz
