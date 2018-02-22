**Duelist** is a highly customizable complex dueling system with betting, queuing, a ranked ladder, rematches, it's own UI and an arena wall generator all made user-friendly to players and server owners.

Duelist creates it's own zones, spawn points and protection (see: 'Auto Create Dueling Zone If Zone Does Not Exist' in the config). Simply install and configure to your needs.

## Dependencies

### Optional

- [Kits](https://oxidemod.org/plugins/kits.668/)
- [Economics](https://umod.org/plugins/economics)
- [ServerRewards](https://oxidemod.org/plugins/serverrewards.1751/)

## Commands

Admin Chat Commands:

- **/duel announce** -- manually announce duelist to all players
- **/duel ban playername** -- ban/unban a player from dueling
- **/duel custom** -- create a dueling zone at the location you are looking at
- **/duel new [tp]** -- create a dueling zone at a random location on the map, and teleport to it if tp is also specified.
- **/duel remove** -- remove a dueling zone at the location you are at. this will also delete all zone walls associated with the zone
- **/duel removeall** -- remove all dueling zones. this will also delete all zone walls
- **/duel resetseed** -- reset win/loss/ratio ladder stats for the seed
- **/duel remove_all_walls** -- destroys all high external walls on the server which have an owner id greater than 0 and do not belong to a player. See the FAQ for more information on this command.
- **/duel save** -- force, an otherwise automatic, save of all data
- **/duel spawns** -- show all automatically created or custom spawn points for the zone you are at
- **/duel spawns add** -- create a custom spawn point at the location you are looking at
- **/duel spawns remove** -- remove the closet custom spawn point to you
- **/duel spawns removeall** -- remove all custom spawn points near you
- **/duel spawns wipe** -- wipe all custom spawn points
- **/duel tp** -- teleport to the nearest dueling zone with priority for players in 1v1 matches
- **/duel tpm** -- teleport to the nearest dueling zone with priority for players in TDM matches
- **/duel on** -- enable players to 1v1 and TDM
- **/duel off** -- disable players from 1v1 and TDM

Admin Console Commands:

- **duel on|off|new|removeall|resetseed**

Player Chat Commands (1v1):

- **/duel playername** -- challenge a player to a 1v1
- **/duel accept** -- accept a 1v1 challenge
- **/duel allow** -- toggle allowing players to challenge you
- **/duel cancel|decline** -- cancel or decline a 1v1
- **/duel bet [itemname] [amount]** -- create a bet
- **/duel block playername** -- block a specific player from challenging you
- **/duel chat** -- toggle showing 1v1/tdm defeat messages
- **/duel claim** -- claim all won bets
- **/duel kit [kitname]** -- show all available kits, or set your priority for your kit using the specified kit name
- **/duel ready** -- ready up for a rematch in 1v1 or TDM

Player Chat Commands (TDM):

- **/tdm playername** -- challenge a player to a TDM
- **/tdm [code]** -- join a private match using the provided code
- **/tdm accept** -- accept a TDM challenge
- **/tdm any** -- join any public TDM or any TDM where the host is an ally
- **/tdm cancel|decline** -- cancel or decline a TDM
- **/tdm leave** -- leave your match
- **/tdm kit [kitname]** -- view all kits or set the kit used for your match before it starts (hosts only)
- **/tdm kickban playername** -- ban/unban a player from your match (hosts only)
- **/tdm public** -- toggle your team as public or private (hosts only)
- **/tdm setcode code** -- view or set the code your team (hosts only)
- **/tdm size** # -- set the size of your match (2 for 2v2, 3 for 3v3, 5 for 5v5, etc) (hosts only)

Duelist GUI:

- Use **/dui** to access the GUI
- **Accept** -> Accept a 1v1 or TDM request
- **Decline** -> Decline a 1v1 or TDM request
- **Kits** -> Select the kit for your next 1v1, or the kit for a TDM match if you're a host
- **Public** -> Toggle your TDM match as public or private
- **TDM** -> Join a specific public match, or set the size of your match
- **Queue** -> Join or leave the 1v1 queue
- **Any** -> Join any match that is public is belongs to an ally
- **Ready** -> Ready up for a rematch in 1v1 or TDM
Matches refresh when updated
GUI closes when a 1v1/TDM match starts and reopens after it ends

## Localization
This plugin contains over 230 customizable messages by editing the `/oxide/lang/en/Duelist.json` file. Do not remove any indexing as noted by `{0}`, `{1}`, etc.

See the FAQ for more information.

## Configuration

**Advanced Options:**

- **Let Players Die Normally (default: false)** -- By default players are defeated when they reach 6 health. This overrides that behavior and lets the player die normally.
- **Require 1v1 Maximum Spawn Points To Be Less Than Or Equal To X (default: 200)** -- Forces zones to be chosen where the maximum number of spawn points does not exceed the given number. This is useful if using custom spawn points to distiguish between 1v1 and TDM zones.
- **Require 1v1 Minimum Spawn Points To Be Equal Or Greater Than X (default: 2)** -- Same as above, except for with the minimum number of spawn points.
- **Require TDM Minimum Spawn Points To Be Equal Or Greater To The Number Of Players Joining (default: false)** -- This is specific for Team Deathmatch when using custom spawn points.
- **Send Dead Players Back Home (default: true)** -- Sends a player home when they're defeated. If disabled then this should be used in combination with **Let Players Die Normally** enabled so players are forced to click Respawn.

**Animals:**

- **Die Instantly (default: false)** -- kills an animal instantly when it attacks a player in a match
- **Put To Sleep (default: true)** -- puts an animal to sleep instantly when it attacks a player in a match
- Animals are despawned instantly in active zones.

**Betting:**

- **Allow Bets To Be Forfeit (default: true)** -- allows players to forfeit (not refund) their bet
- **Allow Bets To Be Refunded (default: false)** -- allows players to refund (not forfeit) their bet
- **Bets** -- List of configurable bets. See config.
- **Enabled (default: false)** -- allows betting if **true**

**Custom Arenas** (arenas are independent of dueling zones and serve to benefit users using existing code from the plugin):

- **Indestructible Walls (default: true)** -- prevents all damage to arena walls
- **No Building (default: false)** -- prevent all players from building in the arena
- **No PVP (default: false)** -- prevents all player versus player combat in the arena
- **No Raiding (default: false)** -- protects structures and deployables from harm
- **Use Wooden Walls (default: false)** -- use High External Wooden Walls instead of High External Stone Walls

**Custom Kits:**

- **Kits** -- List of configurable customized kits. See config.
- **Use Workshop Skins (default: true)** -- Skins are randomly chosen already, this allows the use of randomized workship skins which are cached when the plugin is first loaded.

**Deathmatch:**

- **Announce Deaths To Match (default: true)** -- Allows players in the match to see defeat messages. This should be disabled if Let Players Die Normally is enabled and you have a death notes plugin.
- **Announce Deaths To Server (default: false)** -- Allow messages to be sent to all players when a player is defeated in a match. Players may toggle defeat messages using /duel chat, otherwise announce to the match only.
- **Chat Command (default: tdm)** -- The chat command used to access Team Deathmatch.
- **Economics Money [0 = disabled] (default: 0.0)** -- The amount of money to award the winning team.
- **Enabled (default: true)** -- enable or disable Team Deathmatch
- **Evil Shirt Skin (default: 14177)** -- the skin ID used on the Evil team
- **Friendly Fire (default: true)** -- allow/disallow friendly fire for players on the same team
- **Good Shirt Skin (default: 101)** -- the skin ID used on the Good team
- **Max Team Size (default: 5)** -- The maximum allowed team size (5v5) that can be set by a player when using /tdm size
- **Min Team Size (default: 2)** -- The minimum allowed team size that can be set by a player. This setting cannot be lower than 2, else the match will automatically start when a player accepts a TDM request.
- **ServerRewards Points [0 = disabled] (default: 0)** -- The amount of points to reward the winning team
- **Shirt Shortname (default: tshirt)** -- the shortname of the shirt for both teams

**Deployables** (allows players to use specific deployables which are removed when they are defeated):

- Allow Barbed Wooden Barricade (default: false)
- Allow Concrete Barricade (default: false)
- Allow High External Stone Wall (default: false)
- Allow High External Wooden Wall (default: false)
- Allow Metal Barricade (default: false)
- Allow Sandbag Barricade (default: false)
- Allow Stone Barricade (default: false)
- Allow Wooden Barricade (default: false)
- Morph Barricades Into High External Stone Walls (default: false)
- Morph Barricades Into High External Wooden Walls (default: false)

**Ranked Ladder:**

- **Award Top X Players On Wipe (default: 3)** -- Awards the top X players with the **duelist** group and **duelist.dd** permission for use with plugins that give titles based on groups/permissions.
- **Enabled (default: true)**
- See the FAQ for more information on the Ranked Ladder.

**Respawn:**

- **Give Kit If Respawn Items Are Empty (default: autokit)** -- the kit given to players if Items is [] (empty)
- **Items (default list: rock, torch)** -- Items to give players when they're sent home after being defeated

**Rewards** (this is for 1v1, not TDM):

- **Economics Money [0 = disabled] (default: 0.0)** -- the amount of money to give a player when they win a 1v1
- **Required Money To Duel (default: 0.0)** -- the amount of money required to challenge a player to a 1v1
- **ServerRewards Points [0 = disabled] (default: 0)** -- the amount of points to give a player when they win a 1v1

**Settings:**

- **Allow Announcement (default: true)** -- allows the plugin to announce that players have the option to duel
- **Auto Create Dueling Zone If Zone Does Not Exist (default: false)** -- for all intents and purposes this should be true. This allows the plugin to create zones when the maximum allowed is not created.
- **Auto Enable Dueling If Zone(s) Exist (default: false)** -- if enabled this automates the process of enabling dueling for everyone on the server.
- **Blacklist Commands (default: false)** -- if enabled this will block the following chat commands from being used by players in a match
- **Blacklisted Chat Commands (default: rp, remove, bank, shop, event, rw, home, trade)** -- the list of commands players are not allowed to use while in a match
- **Broadcast Defeat To All Players (default: true)** -- show defeat messages to everyone on the server that hasn't specifically toggled this off by using /duel chat
- **Building Block Extension Radius (default: 20.0)** -- Minimum is 10.0. This prevents players from raid towering into dueling zones. This should be left at the default or increased, as players who do raid tower in will not be able to build out.
- **Bypass Naked Check And Strip Items Anyway (default: false)** -- It is NOT advised to enable this unless you're using this plugin on an arena server.
- **Disable Requirement To Allow Duels (default: false)** -- Allows or disallows players to duel without first enabling /duel allow
- **Duel Command Name (chat: duel)** -- the command name used for 1v1
- **Immunity Time (default: 10)** -- the time in seconds players have before they're allowed to engage in combat. This should never be decreased since players must load the map around them while teleporting into the zone.
- **Kits (default list: see config)** -- the kits to be used from the Kits plugin, or the names of Custom Kits if using the next two options
- **Kits Least Used (default list: see config)** -- the kits to be used from the Kits plugin for use with the next option, or the names of Custom kits if using the previous and next option
- **Kits Least Used Chance (default: 0.25)** -- the chance that **Kits Least Used** will be randomly chosen
- **No Movement During Immunity (default: false)** -- allow/prevent player movement during their immunity timer
- **No Stability On Structures (default: true)** -- disable stability on all structures with no owner, or belonging to an admin. Useful if pasting a structure into a dueling zone, or building in one
- **Player Health After Duel [0 = disabled] (default: 100.0)** -- the amount of health a player is given when defeated
- **Queue Command Name (default: queue)** -- the chat command players must use to queue for a random 1v1
- **Reset Temporary Ladder Each Wipe (default: true)** -- wipes the win/loss/ratios on the ladder when a map wipe is detected
- **Respawn Dead Players On Disconnect (default: true)** -- force a dead player to respawn if they disconnect after being defeated. By default, players do not die.
- **Respawn Zone Walls On Death (default: false)** -- respawns any zone wall which is destroyed or killed. This is useful for Decay plugins which subtract entity health, instead of dealing decay damage. The former is not handled unless this is enabled.
- **Scale Damage Percent (default: 1.0)** -- the damage modifier for players in matches
- **Show Warning Message (default: false)** -- warns players they are invisible to others but can still see projectiles from all players
- **Time To Duel In Minutes Before Death (default: 10)** -- the time in minutes players have to defeat their opponent(s) before they're executed by the server.
- **Use Invisibility (default: true)** -- makes players in 1v1 invisible to everyone else
- **Use Random Skins (default: true)** -- randomize skins on custom kit items
- **Whitelist Commands (default: false)** -- if enabled then players will only be allowed to use the following commands while in a zone
- **Whitelisted Chat Commands (default: report, pm, r, help)** -- players will only be allowed to use these commands in a zone if the above option is enabled

**Spawns:**

- **Auto Remove On Zone Removal (default: false)** -- remove custom spawn points in the area of a zone when it is removed
- **Draw Time (default: 30.0)** -- the amount of time in seconds that spawn points are drawn on the users screen
- **Remove All Distance (default: 50.0)** -- the maximum distance custom spawn points are removed from the user when using /duel spawns removeall
- **Remove Distance (default: 10.0)** -- the maximum distance custom spawns points are detected when using **/duel spawns remove**

**User Interface:**

- **Auto Enable GUI For Players (default: false)** -- shows the GUI for all players when they connect to the server if set to true
- **Chat Command (default: dui)** -- the chat and console commands to access the GUI
- **Show Close Button (X) (default: true)** -- enables/disables drawing of the close button
- **Use Cursor (default: false)** -- Removes the necessity to press **ENTER** to access the GUI by forcing the mouse to be used when the GUI is opened.

**Zone:**

- **Avoid Creating Automatic Spawn Points In Water (default: true)** -- if enabled the spawn points will not be created when the depth of water prevents players from attacking
- **Create Least Amount Of Walls (default: false)** -- by default walls are evened off at the highest point of the arena. This option, if enabled, will only create the minimum required number of external walls
- **Create New Zone Every X Duels [0 = disabled] (default: 10)** -- the number of duels required to automatically remove a zone and relocate it elsewhere randomly on the map. This keeps zones fresh and provides the most challenging terrain for players.
- **Extra High External Wall Stacks (default: 2)** -- the number of extra walls to build once the zone walls have been created. This should never be less than 2. If you experience issues with boosting over a wall then increase this number by 1.
- **Max Zones [Min 1] (default: 1)** -- the maximum number of zones allowed to be created automatically and manually. For arena servers the number can be safely set above 100.
- **Maximum Incline On Hills (default: 40.0)** -- The maximum incline allowed from the lowest and highest points of terrain for every zone. Decrease this number to use flatter terrain.
- **Players Per Zone [Multiple Of 2] (default: 10)** -- the maximum number of players allowed per zone. If this number is not a multiple of 2 then it will be automatically adjusted for you.
- **Players Visible To Admins (default: true)** -- allows admins to see invisible players in matches. Useful when disabled if admins like to play matches without seeing everyone.
- **Use Arena Wall Generation (default: true)** -- automates the process of creating walls around a zone. This should not be disabled unless you protect your zone using other means.
- **Use Wooden Walls (default: false)** -- by default all external walls are stone. This allows them to be wooden instead. The protection is the same.
- **Zone Radius (Min: 50, Max: 300) (default: 50.0)** -- the radius for every zone created automatically or manually. This number should not be increased without gradually testing it. Setting this number too high will break the plugin.

## Frequently Asked Questions

**Steps to creating a quick bind for the Duelist GUI:**
1. Press F1, go to Console
2. bind u dui
3. Press U to toggle the Duelist GUI

**How Team Deathmatch works:**

- Players are not invisible in Team Deathmatch.
- Friendly Fire can be set on or off in the config.
- Once all players of the enemy team have been killed the match will end. This is not score based yet.
- First a match must be created. To do this use '/tdm playername' to challenge a player
- Once a player has used '/tdm accept' to accept your challenge the match will be opened for private invitation and codes will be sent to the host of each team
- Private invitation requires players joining to either 1) be a friend of a host, or 2) provide a code to join a team. The plugin uses its own code to decide if a player is a friend or not. See 'How betting protection works'.
- To join private matches players must use '/tdm any' to join any team which is hosted by a friend, or '/tdm code' where code is the 5 digit code specific to your team
- Toggle your match for public invitation by using /tdm public. If a match is public any player may use '/tdm any' to join it.
- You may use '/tdm cancel' to cancel your match so long as it hasn't started
- You may use '/tdm leave' to leave a match that you have joined
- To set a specific size for your match use '/tdm size 3' where 3 will make it a 3v3 so long as the match hasn't started
- TDM takes precedence over 1v1 duels and will lock a zone from use while a match is in progress. This also means that a TDM cannot start until a zone is free of all duelists. (This can be altered under Advanced Options in the config and by using custom spawn points. 'Create New Zone Every X Duels' must be set to 0 (zero) if using advanced options.)
- Use /tdm for more information.

**How zone creation works:**

- Duelist will scan the map for a suitable area which must meet these requirements: be away from all player structures and deployables, not be covered by more than 25% water, and not be on extremely steep hills.
- When this is completed the plugin will then create it's own spawn points within the dueling zone.
- Afterwards, an admin may type '/duel on' to enable dueling. Typing '/duel off' will disable duels and remove all duelers from the dueling zone.
- A new zone is automatically created after every 10 duels to keep the terrain fresh for players so they never tire of the same dueling location. This will stall until all current duels finish. This provides the most challenging locations for players to fight in.

**How protection works:**

- Players cannot do damage to structures, deployables or other players other than to the player(s) in their match.
- Players cannot loot any containers, or drop any items other than throwing weapons. This is useful for server owners who want the zone in a custom defined location (use '/duel custom' to spawn the zone at the location you are looking at)
- Players cannot build inside of the dueling zone unless configured.
- The dueling zone is surrounded by arena walls evened off at the top
- Animals that attack players inside of the dueling zone will either be put to sleep, flee, or be killed depending on your config setting.
- All duelers have invisibility to everyone except the person they are dueling until their duel is finished. This means zones can be shared by multiple players except if in use by a TDM match.
- Players have 10 minutes to finish their match before they are executed by the server.
- If for any reason the dueler dies then the opposing dueler will win the duel.
- Duelers are immune to cold and drowning in the dueling zone

**How arena wall generation works:**

- Must be enabled to prevent players from leaving dueling zones. Optional if you use other means.
- Generates automatically when a dueling zone is created.
- Arena walls will automatically be removed from zones which are deleted as a result of lowering 'Max Zones' in the config
- Walls conform to the highest and lowest points of terrain
- Will only be created if no arena walls around the dueling zone exist
- Walls are removed when the dueling zone is removed
- Walls are not removed when the plugin is unloaded. You must manually delete the zone to have the walls removed
- Walls level off at the top at the same height above the highest point of terrain. This amount can be adjusted in the config under 'Extra High External Wall Stacks'
- Walls are immune to all damage including decay
- If walls are not at the desired height then increase the Extra High External Wall Stacks amount
- Use '/duel remove_all_walls' to remove all high external stone walls on the server which have an owner ID greater than 0 but are not owned by any player.

**How spawn points work:**

- A random spawn point is assigned to the first dueler, and the second dueler will be spawned away from this player at a safe distance.
- Players are given temporary immunity to damage (10 seconds) to get themselves situated in their match. This time starts once they begin teleporting.
- Spawn points are generated each time the plugin is loaded, and when a dueling zone is created/initialized.
- Spawn points are located around the circumference of each zone, viewable by using '/duel spawns'

**How betting works:**

- Once enabled players may make bets towards their next duel under the condition that the player they duel has the same bet.
- You are not allowed to request duels while having an active bet if the player you are requesting does not have the same bet.
- If joining the queue with a bet then you will only win the bet if the player you defeat has the same bet as you and is not associated as a friend.
- Bets must be multiples of 500 if above 500 in the total amount bet. This reduces operator error between two players placing bets.
- Protection is in place to prevent friends from betting other friends. This prevents abuse of the betting system.
- You can add or edit the available bets by viewing **Settings -> Bets** in the configuration file.
- Use '/duel bet' in game.

**How betting protection works:**

- 5 unique methods are used to check if 2 players are friends.
- Are they in the same clan?
- Are they authorized on any cupboard together?
- Are any of their sleeping bags within proximity of each other?
- Are they sharing any codelocks together?
- Have they built anything together in the same location?
- If any of these are true then they're friends and the bet cannot be won.

**How queuing works:**

- Simply type /queue and wait for another player to join the queue. Once two players are queued they will instantly teleport to a dueling zone to begin their match. The queuing system is first come first serve. This removes the need to directly request a duel with another player.
- Players are instantly teleported back to the position from which they joined when their match is over or they have been defeated. If a bet was won then an announcement will be made to the winner.

**How the ranked ladder works:**

- Type '/duel ladder' to view it. Shows wins, losses and win/loss ratios.
- Resets each wipe except the lifetime ladder.
- Permissions and groups are assigned to the top 3 players for use with plugins that give titles based on permissions or groups after each map wipe.
- Permission Name: duelist.dd
- Group Name: duelist

**How creating custom spawn points work:**

- This feature is completely optional. Spawn points will be automatically generated if none exist.
- Can be added anywhere on the map as they will only be used if found inside of a dueling zone.
- Are not removed when a dueling zone is removed unless configured to do so.
- Are automatically wiped when a server wipe is detected.
- Added spawn points will be indicated by a green +S marker for 30 seconds.
- Removed spawn points will be indicated by a red -S marker for 30 seconds.
- Spawn points can be added, removed or wiped at any time.
- Minimum of two (2) spawn points are required if using custom spawn points.
- Will be automatically used without any special requirements. Add, remove or wipe at any time.

**Kits:**

- Two types of Kits are available. Custom Kits and kits created with the Kits plugin.
- Users may opt to use their own kits created with the Kits plugin by including their names into the Kits and Kits Least Used fields in the configuration file.
- Custom Kits will be used if no kit names are configured.
- To add another Custom Kit simply copy and paste from an existing one and modify it to your needs. Once you're finished use a JSON Validator to ensure there are no formatting errors.
- The plugin does output to the server console if a Custom Kit was not added properly.
- Kits are randomly chosen. Kits have priority over Kits Least Used based on the Kits Least Used Chance.
- You may put Custom Kit names into the Kits and Kits Least Used sections to take advantage of the Kits Least Used Chance setting.

**/duel remove_all_walls:**

- You may use this command, and reload the plugin to apply configuration changes.
- Walls will automatically be created for each zone if NO walls are found when the plugin is reloaded.
- This does not remove walls which are pasted in using CopyPaste.
- This does not remove walls which belong to players.
- The OwnerID of a wall must be greater than 0 (zero) and not belong to a player to be destroyed using this command.
- This is intended to remove walls which were created by Duelist.

**/duel walls** - removed in 1.1.0


