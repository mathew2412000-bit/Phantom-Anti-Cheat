<div align="center">

# 👻 Phantom Anti-Cheat

### Advanced Simulation-Based Anti-Cheat for Minecraft Servers

[![License](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://opensource.org/licenses/GPL-3.0)
[![Minecraft](https://img.shields.io/badge/Minecraft-1.8--26.2-green.svg)](https://www.spigotmc.org/)
[![Platform](https://img.shields.io/badge/Platform-Paper%20%7C%20Spigot%20%7C%20Folia-orange.svg)](https://papermc.io/)
[![Java](https://img.shields.io/badge/Java-25-red.svg)](https://www.oracle.com/java/)
[![Version](https://img.shields.io/badge/Version-2.3.74-purple.svg)](https://github.com/your-repo/phantom-anticheat)

**A powerful, libre simulation-based anti-cheat designed for Minecraft servers.**
</div>

---

## ✨ Features

### 🎯 Advanced Detection System

| Feature | Description |
|---------|-------------|
| **Simulation-Based Detection** | Advanced packet analysis and movement simulation for accurate cheat detection |
| **Comprehensive Checks** | Combat, Movement, Exploit, and Player checks covering all major cheat types |
| **Real-Time Alerts** | Instant notifications via Discord and in-game with detailed violation information |
| **Detailed History** | Track violations over time with session data and statistical analysis |
| **Customizable** | Extensive configuration options for fine-tuning detection sensitivity |

### 🛡️ Detection Categories

#### Combat Checks
- ✅ Aimbot detection
- ✅ Killaura analysis
- ✅ AutoClicker detection
- ✅ Reach violations
- ✅ Critical hits analysis
- ✅ NoSwing detection

#### Movement Checks
- ✅ Fly detection
- ✅ Speed violations
- ✅ NoFall analysis
- ✅ Step exploits
- ✅ Knockback abnormalities
- ✅ Sprint exploits
- ✅ Velocity violations

#### Exploit Checks
- ✅ NoClip detection
- ✅ Scaffold analysis
- ✅ Timer exploits
- ✅ Block exploits
- ✅ Liquid exploits
- ✅ Ghost hand detection

#### Player Checks
- ✅ BadPackets analysis
- ✅ Invalid Sneak
- ✅ AutoSprint detection
- ✅ Transaction packets
- ✅ Flying packets

### 🎨 Phantom Branding

- **🟣 Purple Theme**: Beautiful ghost-themed purple branding throughout
- **🎭 Custom Discord Integration**: Full webhook support with purple embeds and custom logos
- **👥 Staff Menu**: GUI-based moderation tools with intuitive interface
- **🎨 Professional UI**: Clean, modern interface with hover information
- **🌍 Multi-language Support**: English, Spanish, French, Portuguese

### 🔧 Advanced Features

- **🔄 Folia Compatible**: Full support for regionalized servers
- **⚡ Async Processing**: Most checks run asynchronously for minimal impact
- **💾 Efficient Caching**: Optimized data structures for low memory usage
- **🎯 Per-Player Settings**: Individual configuration for exempt players
- **📊 Performance Metrics**: Built-in performance monitoring
- **🔍 Debug Tools**: Comprehensive verbose mode for troubleshooting

---

## 🎯 Why Phantom?

| Feature | Phantom | Other Anti-Cheats |
|---------|---------|------------------|
| **Simulation-Based** | ✅ Advanced packet simulation | ❌ Often flag-based |
| **Open Source** | ✅ Fully libre (GPLv3) | ❌ Often proprietary |
| **Active Development** | ✅ Regular updates | ⚠️ Varies |
| **Discord Integration** | ✅ Native support | ⚠️ Requires plugins |
| **Staff GUI** | ✅ Built-in menu | ❌ Rare |
| **Purple Theme** | ✅ Beautiful branding | ⚠️ Generic |
| **Folia Support** | ✅ Full support | ❌ Limited |
| **Performance** | ✅ Optimized | ⚠️ Varies |
| **Customization** | ✅ Extensive | ⚠️ Limited |
| **Documentation** | ✅ Comprehensive | ⚠️ Basic |

---

## 📋 Requirements

### Server Requirements
- **Minecraft Version**: 1.8–26.2
- **Server Platform**: Paper, Spigot, or Folia
- **Java Version**: 25 or higher
- **RAM**: Minimum 2GB (4GB+ recommended)

### Required Dependencies
- **PacketEvents** 2.0+ (automatically included)

### Optional Dependencies
- **ProtocolLib** - Enhanced packet handling
- **ViaVersion** - Cross-version support
- **LuckPerms** - Permission management
- **PlaceholderAPI** - Placeholder support
- **Database Drivers** (MySQL, PostgreSQL, MongoDB, SQLite)

---

## 🚀 Installation

### Quick Start

1. **Download the Plugin**
   ```bash
   # Download the latest release
   wget https://github.com/your-repo/phantom-anticheat/releases/latest/PhantomAntiCheat-2.3.74.jar
   ```

2. **Install on Your Server**
   ```bash
   # Place the JAR in your plugins folder
   cp PhantomAntiCheat-2.3.74.jar /path/to/server/plugins/
   ```

3. **Restart Your Server**
   ```bash
   # Restart to load the plugin
   ./restart.sh
   ```

4. **Configure the Plugin**
   ```bash
   # Edit the configuration
   nano plugins/PhantomAntiCheat/config.yml
   ```

5. **Set Up Discord Webhooks**
   ```bash
   # Configure Discord integration
   nano plugins/PhantomAntiCheat/discord.yml
   ```

### Verification

Check if the plugin loaded successfully:
```bash
# In server console
/phantom version

made by qk9lxz
