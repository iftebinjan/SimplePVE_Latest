# 🛡️ SimplePVE — Advanced PvE Management for Rust Servers

**SimplePVE** is a powerful and fully customizable **PvE (Player vs Environment)** management plugin for Rust Oxide/uMod servers.  
It allows you to control PvE/PvP toggling, zone-based protection, looting rules, and purge schedules — all while integrating smoothly with other plugins such as **ZoneManager**, **ImageLibrary**, **Clans**, **RaidableBases**, and **SimpleStatus**.

> 🛒 Available on [Codefling → SimplePVE](https://codefling.com/plugins/simplepve)

---

## ✨ Features

✅ Dynamic PvE/PvP toggling and timed purges  
✅ Full vehicle and turret protection logic  
✅ Auto-claim vehicles on engine start (Mini, ScrapHeli, Boats, etc.)  
✅ Player-friendly chat, UI, and toast notifications  
✅ Extensive configuration (JSON-based)  
✅ Integration with third-party plugins (Clans, RaidableBases, Notify, etc.)  
✅ Discord webhooks for purge announcements  
✅ Permission-based admin overrides and commands  

---

## ⚙️ Installation

1. Download the latest **SimplePVE.cs** file.  
2. Place it into your server’s `oxide/plugins` directory.  
3. A default configuration file will be created in:
   ```bash
   oxide/config/SimplePVE.json
   
## 🔑 Permissions

   | Permission              | Description                               |
   | ----------------------- | ----------------------------------------- |
   | `simplepve.admin`       | Full access to all plugin commands.       |
   | `simplepve.adminloot`   | Allows bypassing loot protection.         |
   | `simplepve.admindamage` | Allows bypassing PvE damage restrictions. |

## 💬 Commands

   | Command         | Description                                      |
   | --------------- | ------------------------------------------------ |
   | `/simplepve`    | Enables or toggles PvE mode.                     |
   | `/resetsprules` | Resets all rules to default values.              |
   | `/rsp`          | Reloads the plugin safely.                       |
   | `/spdebug`      | Toggles debug mode (requires `simplepve.admin`). |


