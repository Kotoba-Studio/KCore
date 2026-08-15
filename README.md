⚙️ KCore
![Minecraft](https://img.shields.io/badge/Minecraft-1.21%2B-5EAF47?style=flat-square&logo=minecraft&logoColor=white)
![Platform](https://img.shields.io/badge/Platform-Paper%20%7C%20Folia%20%7C%20Canvas-2F80ED?style=flat-square)
![Version](https://img.shields.io/badge/Build-R01--v9-8A5CF6?style=flat-square)
![Folia](https://img.shields.io/badge/Folia-Supported-22C55E?style=flat-square)
![License](https://img.shields.io/badge/Kotoba%20Studio-Plugin-111827?style=flat-square)
> [!IMPORTANT]
> **KCore** là core gameplay dành cho EcoSMP: Home, Warp, Spawn, TPA, Settings, Profile, Leaderboard, Player Vault, RTP, Menu Engine, Placeholder, Policy theo rank và các module bảo vệ server — gom vào một plugin thống nhất, tối ưu cho Paper/Folia.
✨ Highlights
🏠 Home / Warp / Spawn — GUI, warmup, hủy khi di chuyển, giới hạn home theo rank.
🌀 TPA đầy đủ — `/tpa`, `/tpahere`, inbox GUI, confirm GUI, auto accept, toggle nhận request.
⚙️ Player Settings — toggle chat, TPA, mob spawn, phantom, night vision, personal time/weather và nhiều integration flags.
🧭 RTP Engine — queue, async snapshot scan, safe-location validation, cooldown/cost theo LuckPerms, refund an toàn.
📦 Player Vault — tối đa 15 vault, session lock, atomic-save/journal, anti-loss khi đang mở kho.
🏆 Leaderboard — balance/shards top với cache và provider bridge.
👤 Profile & Achievements — balance, shards, kills/deaths, homes, rank/policy và achievement cards.
🧩 Custom Menu Engine — menu YAML, dynamic command, requirements, click actions, PlaceholderAPI.
💱 Currency Bridge — KEssentials / Vault / PlayerPoints / KShards / SolarShards.
🛡️ KWL / KWB / AntiLagMachine — command firewall, crystal/anchor protection và chống abuse boat/snow-golem.
🔊 Teleport Sound Effects — start, countdown, success, cancelled, failed.
🎨 Theme system — `donut` và `other`, toàn bộ GUI có thể chỉnh bằng YAML.
📦 Installation
Đặt `KCore-R01-v9.jar` vào thư mục `plugins/`.
Khởi động server một lần để KCore tạo config và resource mặc định.
Chỉnh `plugins/KCore/config.yml` và các file trong `modules/`, `styles/`, `menus/`.
Dùng `/kcore reload` sau khi chỉnh phần hỗ trợ reload runtime.
> [!NOTE]
> LuckPerms, Vault, PlayerPoints, KShards, SolarShards và PlaceholderAPI đều là **soft dependency**. KCore chỉ hook tính năng tương ứng khi plugin đó tồn tại.
🧱 Modules
Module	Mặc định	Chức năng
Homes	✅	Home GUI, set/delete/teleport, rank limits
Warps	✅	Warp GUI, set/delete/teleport
Settings	✅	Player preference GUI + runtime behavior
TPA	✅	Requests, GUI, auto/toggle, warmup
Menus	✅	Custom YAML Menu Engine
Placeholders	✅	`%kcore_*%` + internal placeholders
Leaderboards	✅	Balance/Shards top GUI
Vaults	✅	Personal 54-slot vaults + anti-loss
RTP	✅	Safe random teleport engine
Profile	✅	Profile & achievements
KWL	❌	Command whitelist/firewall
KWB	❌	Crystal/anchor/minecart protection
AntiLagMachine	❌	Boat + snow-golem abuse protection
⌨️ Main Commands
```text
/kcore <reload|status|doctor|antilag|setspawn|setwarp|delwarp|menu>
/kmenu <open|menu|reload|list|validate>
/spawn              /setspawn
/home [name]         /homes
/sethome [name]      /delhome <name>
/warp [name]         /warps
/setwarp <name>      /delwarp <name>
/settings
/tpa [player]        /tpahere [player]
/tpaccept [player]   /tpadeny [player]
/tpacancel           /tpaauto [on|off]
/tpatoggle [on|off]  /confirmmenu <on|off>
/acceptmenu <on|off>
/baltop              /shardstop
/pv [number]
/rtp [overworld|nether|the_end]
/profile
/kwl <status|reload>
/kwb <status|reload>
```
🔌 Integrations
Integration	Use
LuckPerms	Rank policy, RTP profiles/meta overrides
Vault / VaultUnlocked	Balance provider
PlayerPoints	Optional balance/shards provider
KShards / SolarShards	Shards provider
PlaceholderAPI	`%kcore_*%` expansion + menu placeholders
KTeams	Soft dependency reserved for ecosystem integration
🧩 Placeholder Examples
```text
%kcore_version%
%kcore_build%
%kcore_style%
%kcore_home_count%
%kcore_balance%
%kcore_balance_short%
%kcore_shards%
%kcore_shards_short%
%kcore_tpa_auto%
%kcore_setting_public_chat%
%kcore_setting_player_time%
```
📚 Full Documentation
KCore có tài liệu riêng đầy đủ cho toàn bộ command, permission, placeholders, Menu Engine, RTP, Policy, Vault anti-loss, Settings, KWL/KWB/AntiLag và cấu trúc config:
➡️ `docs/FULL-DOCUMENTATION.md`
🗂️ Main Files
```text
plugins/KCore/
├─ config.yml
├─ data.yml
├─ menus/
│  ├─ main.yml
│  └─ example-pro.yml
├─ modules/
│  ├─ policy.yml
│  ├─ rtp.yml
│  ├─ vault.yml
│  ├─ kwl.yml
│  ├─ kwb.yml
│  └─ anti-lag-machine.yml
└─ styles/
   ├─ donut.yml
   └─ other.yml
```
🧠 Design Notes
> [!TIP]
> KCore chủ động **override các command gameplay dùng chung** thay vì để Essentials chiếm command. `commands.force-override: true` phù hợp khi KCore là core chính của server.
Economy/shards placeholders dùng cache và refresh bất đồng bộ để không block server tick.
RTP dùng queue + ChunkSnapshot scan và final live safety check trước teleport.
Player Vault có session lock, journal và giới hạn thao tác khi vault đang mở để giảm rủi ro mất/nhân bản item.
Menu refresh bị giới hạn tối thiểu để tránh config chạy inventory update mỗi tick.
Scheduler bridge hỗ trợ Paper và Folia/Canvas-style scheduler API.
💬 Support
Kotoba Studio · `https://dsc.gg/k-studio`
---
<p align="center"><sub>KCore R01-v9 · Built for the Kotoba Studio Minecraft ecosystem.</sub></p>
