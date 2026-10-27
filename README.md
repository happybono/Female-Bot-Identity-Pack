# Female-Bot-Identity-Pack
Female Bot Names - GIGN Japanese &amp; GSG9 English : A Mod for Counter-Strike : Condition Zero.

## Description
This is a drop-in `BotProfile.db` for Counter-Strike : Condition Zero. It adds female-named bots and ties each name to a fixed CT skin, so a name always matches the model you see.

## What it does
- Adds 31 female bot names (37 profiles) across Fair, Normal, Tough, Hard and Expert, so they show up at every difficulty.
- `GIGN` is reserved for Japanese names : Kanade, Sakura, Hina, Mio, Yui, Rin, Aoi, Haruka, Mei, Nanami, Akari, Misaki, Shiori, Ayaka, Hikari, Kokona, Riko, Sora, Tsubasa, Rei.
- `GSG9` is reserved for English names : Alice, Bella, Clara, Diana, Elena, Fiona, Grace, Hannah, Irene, Julia, Luna.
- Female bots are CT-only (`Team = CT`), so they never get assigned to T, where the same skin numbers mean different models.
- Kanade and Luna are defined once per difficulty, with the same skin every time.
- Roughly `1` in `4` CT bots will be female at Normal and above (about `1` in `9` on Easy).
-  Female bots use `VoicePitch = 125`.

> [!Important]  
> **Stock bots are changed too.**
>   
> To make `GIGN` / `GSG9` exclusive to the female bots, all original male bots now use fixed skins (`Urban` / `SAS` on `CT`, `Terror` / `Arctic` on T) instead of a random one. Their names, skill and weapons are unchanged. If you want the old random skins back, delete the `Skin` lines of the male bots (or set them to `0`), but then male names can appear as `GIGN` / `GSG9` again.

## Installation
1. Back up your original `czero/BotProfile.db`.
2. Copy the new `BotProfile.db` into your `czero` folder (e.g. Steam : `Steam\steamapps\common\Half-Life\czero\`).
3. Fully restart the game, then add bots as usual. You can also test with `bot_add_ct Kanade`.

To uninstall, restore your backup.

## Customizing
Each bot is one block. Change the name, or `Skin` (`2 = GSG9`, `4 = GIGN`) :
  
```DB
Hard+Rifle Ayaka
	Team = CT
	Skin = 4
	VoicePitch = 125
End
```
  
## Disclaimer
Female names are correctly paired with `GIGN` / `GSG9` skins when bots are created on their assigned side (CT). 

However, if the game's built-in auto-balance feature moves bots from the Terrorist side to the CT side (when the Terrorists have more players / bots), a transferred bot may end up with a male name instead of a female one. 

This only happens in that specific scenario, and it is caused by the game's auto-balance mechanics rather than the profile data in this mod. This only happens in that situation. 

It is caused by the game's auto-balance behavior, not by the profile data in this mod.

> [!NOTE]  
> This mod only changes bot profiles. It doesn’t include models or voices, so GIGN / GSG9 look like the stock models unless you use female player models or voice packs. Works well alongside those.  
> It replaces `BotProfile.db`, so it will conflict with other mods that replace the same file (including bot packs).  
> Tested in `Condition Zero`. Not tested in other games.

## Known Limitation / Trade Off
- Female names and their assigned `GIGN` / `GSG9` models are matched correctly when bots are initially created. To prevent stock male names from spawning with the female `GIGN` and `GSG9` replacement models, this mod restricts the stock male bot profiles to `Skin = 1` and `Skin = 3`.
- Repeated testing confirms that this modification introduces a team-transfer limitation that does not occur with the original `BotProfile.db`. When an existing Terrorist bot is moved to the Counter-Terrorist team by auto-balance or a team change, the game preserves the bot's original name while converting its model.
- Because the modified male profiles use only `Skin = 1` and `Skin = 3`, transferred bots become limited to GSG9 and SAS under these conditions. As a result, a transferred male bot may retain its male name while using the female GSG9 replacement model, and `GIGN` and `Seal Team 6` may not appear among the transferred bots.
- This is a trade-off introduced by reserving `GIGN` and `GSG9` for the female-name profiles. It affects team-transfer events only; bots created normally on their intended team remain correctly matched.

> [!NOTE]
> This exception is limited specifically to team-switch events. When an existing terrorist bot is converted to the `GSG9` model, the bot may retain its original male in-game name rather than display a female name.
>  
> This is not a `BotProfile.db` syntax or configuration error. It is a team transfer limitation exposed by this mod's fixed skin assignments and the game's built-in team switch model-conversion behavior. BotProfile.db controls a bot's profile when it is created, but it cannot rename or rematch an existing bot after the game transfers that bot to the opposite team.

## Credits
Original `BotProfile.db` : Valve / Turtle Rock Studios.

## Copyright
Copyright (C) 2002 Valve / Turtle Rock Studios.  
Copyright (C) 2026 HappyBono. All Rights Reserved.


  
