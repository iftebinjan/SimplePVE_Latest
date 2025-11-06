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
  
## ⚙️ Configuration Overview

      The configuration file is highly modular.
      ```bash
      {
     "PVE Enabled": true,
     "Auto Claim Vehicle(Mini, ScrapHeli, Boats, Moudlars etcs) On Engine Start": true,
     "Notifications": {
       "Prefix": "<color=#00ffff>[SimplePVE]</color>: ",
       "Chat Avatar": 0,
       "Show PVE Icon Overlay": true,
       "Show PVE Warning Messages": true,
       "Show PVE Warning Messages TIP": true,
       "PVE Warning Type(Chat/UI/Both(Chat & UI)/Toastify/Notify)": "Both(Chat & UI)",
       "PVE Warning Chat Message": "PVE enabled on this server, blocking damage.",
       "PVE Warning Tip Message": "PVE enabled on this server, blocking damage.",
       "PVE Warning Custom UI Message(Toastify/Notify)": "PVE enabled on this server, blocking damage.",
       "PVE Warning UI Settings": {
         "Anchor Min": "0.786 0.722",
         "Anchor Max": "0.99 0.815",
         "Warning Image URL": "https://i.postimg.cc/0jZNDr9x/Add-a-subheading-2.png"
       },
       "Show Loot Protection Messages": true,
       "Show Loot Protection Messages TIP": true,
       "Loot Protection Type(Chat/UI/Both(Chat & UI)/Toastify/Notify)": "Both(Chat & UI)",
       "Loot Protection Chat Message": "This entity is protected!",
       "Loot Protection Tip Message": "This entity is protected!",
       "Loot Protection Custom UI Message(Toastify/Notify)": "This entity is protected!",
       "Loot Protection UI Settings": {
         "Anchor Min": "0.786 0.722",
         "Anchor Max": "0.99 0.815",
         "Warning Loot UI Image URL": "https://i.postimg.cc/SxSsS67s/Add-a-subheading-1.png"
       },
       "PVE/PVP Icon UI Settings": {
         "Anchor Min": "0.5 0",
         "Anchor Max": "0.5 0",
         "Offset Min": "190 30",
         "Offset Max": "250 60"
       }
           },
           "Loot Protection Excluded Entitys": [
             "mailbox.deployed",
             "dropbox.deployed"
           ],
           "Schedules Setting": {
             "UTC Time Difference": 360,
             "Enable Weekly Schedule Only": true,
             "PVP On Notify Message": "<#990000>PVP ENABLED: You can now raid other bases and engage in combat!</color>",
             "PVE On Notify Message": "<#008000>PVE ENABLED: Raiding and fighting are now prohibited. Enjoy peace and safety!</color>",
             "PVP Purge Start Before Message": "PVP TIME APPROACHING: Only {TIMELEFT} minutes remaining until PVP begins!",
             "PVP Purge Ending Before Message": "PVP TIME ENDING: Only {TIMELEFT} minutes remaining until PVP ends!"
           },
           "PVP Delay Setting": {
             "PVP delay time in seconds(If enabled from ZoneRules)": 10,
             "Show PVP Delay Message": true,
             "PVP Delay Message": "You will be removed from PVP state in <color=#DC143C>{delay}</color> seconds."
           },
           "Discord Setting": {
             "Enable Discord Notification": false,
             "Discord Webhook URL": "",
             "Enable Message Before PVP Time Start": false,
             "Before PVP Time Start Minutes": 30,
             "PVP Message Embed Color(Hexa)": "#990000",
             "Before PVP Time Start Message Content": [
               "🔔 **Attention Rust Survivors!**",
               "",
               "PVP purge approaching!",
               "In {Minutes} Minutes🕒",
               "",
               "Prepare yourselves for intense battles! ⚔️"
             ],
             "Enable Message Before PVE Time Start": false,
             "Before PVE Time Start Minutes": 30,
             "PVE Message Embed Color": "#32CD32",
             "Before PVE Time Start Message Content": [
               "🔔 **Attention Rust Survivors!**",
               "",
               "PVP purge ending soon!",
               "In {Minutes} Minutes🕒",
               "",
               "Make your final moves wisely!",
               "Collect your victories and gear up for the next day!"
             ]
           },
           "Commands when PVP Purge Starts": [],
           "Commands when PVP Purge Ends": [],
           "Exclude Zone IDs From Rules": [
             "999",
             "6969"
           ],
           "Status UI": {
             "Enable Status": true,
             "Interval Time In Seconds": 10,
             "PVE/PVP Status": {
               "Status Enable": true,
               "PVE Status": {
                 "Enable Status": true,
                 "Text List": [
                   "PVE ENABLED",
                   "RAID IS DISABLED",
                   "PVP IS DISABLED"
                 ],
                 "Text Color": "#FFFFFF",
                 "Icon Image Url": "https://i.postimg.cc/4ymwFnSC/quality.png",
                 "Icon Image Color": "#A4FE0A",
                 "Status Color": "#718D48"
               },
               "PVP Status": {
                 "Enable Status": true,
                 "Text List": [
                   "PVP ENABLED",
                   "RAID IS ENABLED",
                   "PVE IS DISABLED",
                   "PVP IS ENABLED"
                 ],
                 "Text Color": "#FFFFFF",
                 "Icon Image Url": "https://i.postimg.cc/50YVChxW/human-skull-with-crossed-bones-silhouette.png",
                 "Icon Image Color": "#FFFFFF",
                 "Status Color": "#B22222"
               }
             },
             "Purge Schedule Status": {
               "Status Enable": true,
               "Purge PVP Status": {
                 "Enable Status": true,
                 "Text List": [
                   "PVP ENABLEING IN {TIMER}",
                   "RAID ENABLEING IN {TIMER}",
                   "PVP PURGING IN {TIMER}"
                 ],
                 "Text Color": "#FFFFFF",
                 "Icon Image Url": "https://i.postimg.cc/0j2n3rzp/time.png",
                 "Icon Image Color": "#FFFFFF",
                 "Status Color": "#A30000"
               },
               "Purge PVE Status": {
                 "Enable Status": true,
                 "Text List": [
                   "PVE ENABLING IN {TIMER}",
                   "RAID DISABLEING IN {TIMER}",
                   "PVE PURGING IN {TIMER}"
                 ],
                 "Text Color": "#FFFFFF",
                 "Icon Image Url": "https://i.postimg.cc/rydRF7cc/time.png",
                 "Icon Image Color": "#FFFFFF",
                 "Status Color": "#718D48"
               }
             }
           },
           "Config Version (Don't Edit This)": {
             "Major": 1,
             "Minor": 2,
             "Patch": 11
           }
         }

         

