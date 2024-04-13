========================================================================
                        Indev+ Server Stable
========================================================================

### !!!IMPORTANT!!! ###

In order to properly set up a server using a docker container, make sure that the server is listening to the same port that the container is mapped to!!!
Also, if you want people to join your server using a hostname, make sure to add it to the server.properties' hostname field! Otherwise, the server will expect people to connect using IP instead.
Currently there is no way to have both hostname and IP connectivity. 
Lastly, if you want to join your own online server, localhost or local IP won't work for the reasons above. Use the public IP or hostname instead. 
None of this applies if you run your server with verify-names turned off!  

### INTRODUCTION ###

To run a server, make sure you have port forwarding enabled in your router. Then, simply open the jar file. 
You can use admin commands directly from the console, or say hi to active players!
In order to change server settings, edit the server.properties file with a text editor. Keep in mind you must restart the server for the changes to take effect! 
To close the server, simply close the window. 

### SERVER PROPERTIES ###

The following is a list of server properties and what each one does: 

online-mode: Enforces people to be logged in in order to join the server. Highly recommended to leave this on.
server-ip: Used to set a custom ip or hostname. 
server-port: Specify the port of the server to use. Clients can connect to other ports with IP:PORT. Default is always 25565.
server-name: Self explanatory. 
server-motd: Message of the day.
funmessage-enabled: Enables/disabled fun messages, which are sent to everyone on the server after a set amount of time. You can add those in the funmessages.txt.
funmessage-minutes: Controls how many minutes the server needs to wait before sending a fun message. 
funmessage-whenjoin: Toggles whether or not a fun message is sent to the client when joining the server. 
max-players: Player slots for the server. 
spawn-protection-radius: Defaults to -1 (off). Controls the radius of spawn protection (blocks it extends from the initial spawn point). 
spawn-animals: Controls whether or not passive mobs will spawn. 
spawn-monsters: Controls whether or not hostile mobs will spawn. 
pvp: Toggles pvp (player versus player) combat (survival only).
difficulty-setting: Controls the server's difficulty. 
current-level: Sets the current server level to the provided name. If it doesn't exist, the server will generate a new one under the same name automatically. 
level-name: Sets the name of the newly generated level.
custom-width: Set a custom width for the generated level.
custom-depth: Set a custom depth for the generated level.
custom-height: Set a custom height for the generated level.
level-theme: Controls what theme the level is on.
level-type: Controls what type a newly generated level is on.
level-size: Sets the level size to one of several size variants (like in vanilla indev). Overridden by the custom values. 
level-seed: When generating a new level, the seed in this field will be used. 
season: Determines what season a level generates in. 
seasons: Toggles whether or not season progression is enabled 
weather: Toggles whether or not weather updates should be executed. 
blood-moons: Toggles blood moons on/off.
survival-world: Determines what gamemode the level is in. 
autosave-interval-ticks: Controls how often the server should save the current level.
allow-flight: Enables/disables flight when the level is in creative mode. 
close-server-on-fatal-exception: When enabled, the server will kill itself if it encounters a ciritical error.
white-list: Automatically kicks anyone not in the white list file when enabled. 
server-owner: Specify who is the owner of the server by username. 
send-heartbeat: Sends a heartbeat when enabled.
betacraft-heartbeat: Sends a heartbeat to Betacraft when enabled (useful for making server display on the betacraft launcher)

### FILES ###

You may have noticed the server spewed out some files after the first launch. THESE ARE VERY IMPORTANT! If you remove one, you will have to reconfigure it!
Here's a quick rundown of them: 

server.properties: Main settings file. Controls the aforementioned server settings. 
server.log: A full chatlog of the server since it was started. 
ops.txt: List of admins for the server. Simply add/remove their Minecraft username. 
banned-players.txt: List of banned users. 
banned-ips.txt: List of users with banned IP's. 
muted-players.txt: List of users that have been muted from the chat. 
players-joined.txt: Lists all currently connected players.
funmessages.txt: Put messages here for the server to send if the fun-messages property is enabled. 
rules.txt: Server will send all the contents from this file to everyone's chat when joining or viewing rules via the command. 
white-list.txt: If the property is enabled, the server will kick anyone who joins except players from this list. 

World files can be found in the levels folder. Each world has its own sub-folder, which contains a list of players, the level file itself, a backup of the level file as well as a properties file. 

### COMMANDS ###

Below is a list of commands that admins can use. Some commands can only be used via the console, whilst others only in-game:

/help - Shows a list of all the commands. 
/list - Shows all currently connected players.
/serverinfo - Shows server information. 
/stop - Shuts the server down. 
/save-all - Forces a server-wide level save.
/save-off - Disables level saving.
/save-on - Enables level saving. 
/op <name> - Sets the named user as an admin. Admins have purple names in-game. 
/deop <name> - Remvoes the named user from the admin list (if applicable)
/kick <name> - Kicks the named user from the server.
/ban <name> - Bans the named user from connecting to the server indefinitely. 
/ban-ip <name> - Bans the named user's IP from connecting to the server, but they can still connect using a different IP.
/pardon-ip <IP> - Unbans the IP.
/pardon <name> - Unbans the player. 
/freeze <name> - Freezes the specified player in place. 
/unfreeze <name> - Unfreezes the player.  
/say <message> - Send a text message to everyone in the server. 
/broadcast <message> - Same as /say. 
/tell <player name> <message> - Sends a direct message to the specified player that only they can see. 
/setspawn - Sets the world spawn. Can only be used in-game. 
/tp <first-player> <second-player> - Teleports the first player to the second one. Can also be used with exact coordinates. 
/bring <name> - Brings the specified player to your location. 
/solid - Toggles between placing normal and unbreakable stone. 
/mute <name> - Mutes the specified user from the chat for an indefinite amount of time. 
/moderate - Disables the entire chat. 
/give <player name> <block/item id> <count> - Gives the specified player the chosen block (if valid) and count. Note: count must be 99 or below! 
/spawn <mob name> - Spawns a mob of the specified type nearby. Can also be used with exact coordinates. 
/time <add/set> <amount> - Sets the level time (0-24000)
/whitelist <add/remove/on/off/reload> <name> - Adds/removes the specified player to the whitelist or toggles it. 
/settheme - Can be used to set the theme, fog, sky and cloud colors and default liquids/block at the world border.
/setrule - Controls different game rules. Valid entires include: blood-moons on/off, daynight-cycle on/off, survival-world (gamemode) on/off, explosions on/off and spawn-protection-radius in numbers. 
/season - Used to change or lock season. Accepts season name or "on/off" state.  
/setrule - Adds a new rule to the rules list in the server settings.
/spawn-protection - Toggles spawn protection on/off. 
/physics - Toggles server physics on/off. 
/heal <player> <amount> - Heals the specified player for the set amount. 
/difficulty - Sets the level difficulty. 
/me - Appends * around your message. 
/kill - Kills the player who used it. 
/home - sends the player who used it back to world spawn. 
/fixsync - Teleports the player that used it to their last known locatrion on the server to fix their desync. 
/wood - Gives the player 4 wood. 
/iron - Gives the player 4 iron. 

### FUTURE PLANS ###

Eventually, there are plans to make the server support loading of multiple worlds and achievements/statistics, in order to be in-line with the single player experience (world hopping) 

### CHANGELOG ###

v1.0: Initial release
v1.0.1: Improved block updates and added support for doors and signs. 
v1.1: Added support for seasons, weather, blood moons and some of the misc items (golden tools, spears, battleaxes, quivers, hellfire lighters and arrows, moon watch)
v1.2: Added charms, machines, containers, item NBT and minecarts to the server. Fixed some serious crash and lockup issues. 
v1.3: Made creative and "hardcore" modes work on the server, added support for crawling, laying and sitting, a lot of bug fixes and stability improvements. 
v1.3_01: Fixed some hitbox problems with crawling. 
rev. 20230626: First stable revision. Fixed a plethora of issues from the previous version
rev. 20230628: Fixed mobs burning during rain and player swimming. 
rev. 20230701: Fixed blood moons on the server not sending packets to the clients properly. 
rev. 20230703: Fixed minecarts falling through blocks on some y levels and furnaces consuming buckets. 
rev. 20230807: Nerfed apple drop rates on the server and added leaf piles
rev. 20230810: Fishing and mooshroom changes
rev. 20230812: Fixed swimming desync issues on the server. 
rev. 20230818: Tweaked thunderstorm frequency 
rev. 20230831: Nerfed snowfall during winter 
rev. 20231127: Added giant flowers and bone blocks 
rev. 20242002: Added tall grass, changes to marshland generation