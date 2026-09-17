# 👻 Phantom Anti-Cheat

[![License](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://opensource.org/licenses/GPL-3.0)
[![Minecraft](https://img.shields.io/badge/Minecraft-1.8--26.2-green.svg)](https://www.spigotmc.org/)
[![Platform](https://img.shields.io/badge/Platform-Paper%20%7C%20Spigot%20%7C%20Folia-orange.svg)](https://papermc.io/)
[![Java](https://img.shields.io/badge/Java-25-red.svg)](https://www.oracle.com/java/)

A powerful, libre simulation-based anti-cheat designed for Minecraft servers. Built on the GrimAC framework, Phantom Anti-Cheat provides comprehensive cheat detection with a modern, customizable approach and beautiful purple branding.

## ✨ Features

### 🎯 Advanced Detection System
- **Simulation-Based Detection**: Advanced packet analysis and movement simulation
- **Comprehensive Checks**: Combat, Movement, Exploit, and Player checks
- **Real-Time Alerts**: Instant notifications via Discord and in-game
- **Detailed History**: Track violations over time with session data
- **Customizable**: Extensive configuration options

### 🛡️ Detection Categories
- **Combat**: Aimbot, Killaura, AutoClicker, Reach
- **Movement**: Fly, Speed, NoFall, Step, Knockback
- **Exploits**: NoClip, Scaffold, Timer, Block exploits
- **Player**: BadPackets, Invalid Sneak, AutoSprint
- **Reach**: Combat reach violations

### 🎨 Phantom Branding
- **Purple Theme**: Beautiful ghost-themed purple branding
- **Custom Discord Integration**: Full webhook support with purple embeds
- **Staff Menu**: GUI-based moderation tools
- **Professional UI**: Clean, modern interface

## 📋 Requirements

- **Minecraft Version**: 1.8–26.2
- **Server Platform**: Paper, Spigot, or Folia
- **Java Version**: 25
- **Dependencies**: 
  - PacketEvents 2.0+
  - (Optional) ProtocolLib, ViaVersion, LuckPerms, PlaceholderAPI

## 🚀 Installation

1. Download the latest `PhantomAntiCheat-2.3.74.jar`
2. Place it in your server's `plugins/` folder
3. Restart your server
4. Configure the plugin in `plugins/PhantomAntiCheat/config.yml`
5. Set up Discord webhooks in `plugins/PhantomAntiCheat/discord.yml`

## ⚙️ Configuration

### Basic Setup
```yaml
# Enable/disable checks
alerts:
  enabled: true
  # Configure alert thresholds
  verbose:
    enabled: false

# Discord webhook setup
discord:
  enabled: true
  webhook: "YOUR_WEBHOOK_URL"
  embed-color: "#9B59B6"
  embed-title: "👻 Phantom Anti-Cheat Alert"
