# WarfaceBotCommands
## Avaible commands:
### ACTONS:
!add <i>pickup</i>[ <i>pickup</i> ..]] or +<u>pickup</u>[ <i>pickup</i> ..]] - adds you to specified pickups.   
!add or ++ - adds you to all active pickups.    
!remove <i>pickup</i>[ <i>pickup</i> ...] or -[<i>pickup</i>[ <i>pickup</i> ..]] - removes you from specified pickups.   
!remove or -- - removes you from all pickups.   
!expire <i>time</i> - Sets new time delay after you will be removed from all pickups, example: '!expire 1h 2m 3s'.   
!default_expire <i>time</i> or 'afk' - Set your personal default !expire time or set autoremove on afk status.   
!sub - request sub for last game.   
!allowoffline or !ao - gives you immune from getting removed by offline or afk statuses until a pickup with you starts. (done for mobile devices users).   
!subscribe <i>pickup</i>[ <i>pickup</i> ..]] - adds the promotion role of specified pickup(s) to you.   
!unsubscribe <i>pickup</i>[ <i>pickup</i> ..]] - removes the promotion role of specified pickup(s) from you.   

### INFO:
!who [<i>pickup</i>[ <i>pickup</i> ...]] - list of users added to a pickups.   
!pickups - list of all pickups on the channel.   
!pickup_groups - list of pickup groups configured on the channel.   
!expire - shows you how much time left before you will be removed from all pickups.   
!lastgame [<i>@nick</i> or <i>pickup</i>] - show last pickup, or last pickup by specified argument.   
!top [<i>pickup<i>] [weekly or monthly or yearly] - shows you most active players.   
!stats [<i>nick</i> or <i>pickup</i>] - shows you overall stats or stats for specified argument.   
!ip [<i>pickup</i> or default] - shows you ip of last pickup or specified pickup.   
!map <i>pickup</i> - print a random map for specified pickup.   
!maps <i>pickup</i> - show all maps for specified pickup.   

### TEAMS PICKING:
!cointoss or !ct [heads or tails] - toss a coin.   
!pick <i>@nick</i> - pick a user to your team.   
!put <i>@nick</i> alpha or beta - put player in specified team (availible only for users with moderator or admin rights).   
!subfor <i>@nick</i> - become a substitute for specified player.   
!capfor alpha or beta - become a captain of specified team.   
!teams - show teams for current pickup.   

### MODERATION:
!noadd <i>@nick</i> [<i>time</i>] [<i>reason</i>] - disallow user to play pickups.   
!noadds - show list of users who are disallowed to play pickups.   
!forgive <i>@nick</i> - allow user from noadds list to play pickups.   
!phrase <i>@nick</i> <i>text</i> - set specified reply for specified user after !add command.   
!remove_player <i>@nick</i> - remove specified players from all pickups.   
!reset - removes all players from all pickups.   
!start <i>pickup</i> - force a pickup to start with deficient players count.   
!cancel_match <i>match_id</i> - cancel an active match, match_id can be found at the beginning of pickup start message.   

### CONFIGURATION:
!enable_pickups - turn on the pickup bot on the channel.   
!disable_pickups - turn off the bot and delete all configurations/stats on the channel. <b>Warning, this action is irreversible!</b>   
!add_pickups <i>name</i>:<i>players</i>[ <i>name</i>:<i>players</i> ...] - create new pickups.   
!remove_pickups <i>pickup</i>[ <i>pickup</i> ...] - delete specified pickups.   
!add_pickup_group <i>group_name</i> <i>pickup</i>[ <i>pickup</i>...] - create a pickup group wich will contain specified pickups.
!remove_pickup_group <i>group_name</i> - delete specified pickup group.   
!reset_stats - delete all channel statistics.   
!cfg - show global channel configuration variables.   
!pickup_cfg <i>pickup</i> - show specified pickup configuration variables.   
!set_ao_for_all <i>name</i> 0|1 - allow/disallow offline for all users of specific pickup kind.

!set_default variable value - set a global variable value. Availible variables: admin_role, moderator_role, captains_role, prefix, default_bantime, ++_req_players, startmsg, submsg, ip, password, maps, pick_captains, pick_teams, promotion_role, promotion_delay, blacklist_role, whitelist_role, require_ready.   

!set_pickups <i>pickup</i>[ <i>pickup</i>...] variable value - set variables for specified pickups. Availible variables: maxplayers, startmsg, submsg, ip, password, maps, pick_captains, pick_teams, pick_order, promotion_role, blacklist_role, whitelist_role, captains_role, require_ready.   

##### CONFIGURATION VARIABLES:
* For any variable set 'none' value to disable.
* admin_role <i>role_name</i> - users with this role will have access to configuration and moderation commands.
* moderator_role <i>role_name</i> - users with this role will have access to moderation commands.
* captains_role <i>role_name</i> - random captains will be preffered to this role, also '!capfor' command will be only availible for users with this role if its set.
* prefix <i>symbol</i> - set prefix before all bot's commands, default '!'.
* default_bantime <i>time</i> - set default time for !noadd command.
* ++_req_players <i>number</i> - set minimum pickup required players amount for '++' command or '!add' command without argument, so users wont add to 1v1/2v2 pickups unintentionally. Default value: 5.
* startmsg <i>text</i> - set message on a pickup start. Use %ip% and %password% in <i>text</i> to represent ip and password.
* start_pm_msg <i>text</i> - set private message on a pickup start. Use %pickup_name%, %ip%, %password% and %channel% to represent its values.
* submsg <i>text</i> - set message on !sub command. Use %pickup_name%, %ip%, %password% and %promotion_role% to represent its values.
* ip <i>text</i> - set ip wich will be shown in startmsg, submsg and on !ip command.
* password <i>text</i> - set password wich will be shown in startmsg, submsg and on !ip command.
* maps <i>map_name</i>[, <i>map_name</i>...] - set maps.
* pick_captains 0 or 1 - set if bot should suggest captains.
* pick_teams <i>value</i> -  set teams pick system the bot should use. Value must be in 'no_teams', 'auto' or 'manual'.
 * no_teams - bot will only print players list and captains if needed.
 * auto - bot will print random teams.
 * manual - users will have to pick teams using teams picking commands.
* pick_order <i>order</i> - force specified teams picking order. Example value: 'abababba'.
* promotion_role <i>role_name</i> - set promotion_role to highlight on !promote and !sub commands.
* promotion_delay <i>time</i> - set time delay between !promote and !sub commands can be used.
* blacklist_role <i>role_name</i> - users with this role will not be able to add to specified pickups.
* whitelist_role <i>role_name</i> - only users with this role will be able to add to specified pickups.
* require_ready none or <i>time</i> - if set users will have to confirm themselves using '!ready' command.
* help_answer <i>text</i> - set an answer on !help command.
