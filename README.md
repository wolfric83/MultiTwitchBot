# MultiTwitchBot - Wolfrickeystonebot

MultiTwitchBot is an IRC based multi-room raffle bot developed to operate with the Twitch network.

  - Raffles across multiple rooms
  - Invite bot to additional rooms - Authorizations required to comply with twitch bot ToS
  - Magic happens

# Features!

  - Allow single entries per person, or multiple - one for each room they enter from
  - Internal Mods list (possible future option for any channel mod to perform _-some-_ actions)
  - Good Luck Protection - Host Selectable winner exclude system - exclude X previous winners from draw
  - Sub Luck
  - Bad Luck Protection
  - Roll method is: 1-1000 (streamer selectable) with luck increasing the minimum roll number
      - eg: Sub with 30% bonus plus 20% BLP would roll 501-1000
       - fresh non-sub would roll 1-1000
  - More features to be added by demand...


## How to use

MultiTwitchBot is python based, run from cloud based virtual hosting in the US. Access on demand to the web console provided by Wolfric83

It is recommended (but not required) to grant mod permission to the bot to prevent dropped messages.

### Typical use:
Streamer invites additional hosts with **_!invitehost -TwitchName-_**

Additional participating streamers accept with **_!acceptinvite_** (Must be the most recently invited host)

Participating streamer types **_!startraffle_**

Viewers on any stream type \<Keyword\>
  
... time passes as viewers enter (Bot continues to send notices to channel - these are not new raffles)
  
Participating streamer types **_!closeraffle_** (optional)
  
Participating streamer types **_!draw_**
  
  Bot announces winner into streams
  
Rinse and Repeat from **_!startraffle_**



### Viewer Commands:
* **_!reportme_** - Outputs multipliers applied to -your- rolls
* **_!announcerooms_** - Outputs URLs to participating streams

### Streamer Commands:
* **_!resetrafflebot_** - Leaves all rooms, and resets raffle bot to listen to only default user's commands
    * _Notifies all rooms_
* **_!invitehost -TwitchName-_** - posts message to current channel requesting response to invite the bot to -TwitchName-
* **_!acceptinvite_** - Required by additional hosts to bring bot into their channel.
* **_!raffleleave_** - Asks RaffleBot to leave your channel
#####
* **_!startraffle_** - Resets the current Raffle list, listens for saved keyword for entry to raffle
* **_!startraffle -NewKeyWord-_** - Resets the current Raffle list, changes keyword and listens for entries to raffle
* **_!closeraffle_** - Stops listening for raffle keywords. saves everything to DB
* **_!draw_** - Stops listening for raffle keywords. saves everything to DB. Draws one winner and reports to all chats. 
* ~**_!clearsession_** - Resets session list and past winners list~
* **_!undo_** - Undos the last !draw, reverting the BLP for the last drawn winner. 
* **_!redraw_** - Combines !undo and !draw. reverts previous winners BLP, removes that entry from draw, and Draws one winner and reports to all chats. 
* **_!reopenraffle_** - starts accepting additional entries when typed after a !draw. 

#####
* **_!changekeyword -Keyword-_** - Changes raffle keyword to -Keyword-
* **_!changenotice -NoticeText-_** - Change the Notice text (what is being raffled) 
    * Example: **_!changenotice Free Gift Sub_**
    * changes repeating notice to: Now Raffling: Free Gift Sub. Enter by typing: -Keyword-
    * will send initial notice: Next raffle draw: Free Gift Sub. by -yourname-
#####
* **_!singleraffle_** - Turn on Single Entry mode
* **_!multiraffle_** - Turn on Multi entory mode (one per User/Channel combination)
* **_!raffleannounceon_** - Turn on periodic Raffle announcements 
* **_!raffleannounceoff_** - Turn off periodic Raffle announcements 
* **_!enableblp_** - enables Bad Luck Protection
* **_!disableblp_** - disables Bad Luck Protection
* **_!enablesubluck_** - enables Sub Luck
* **_!disablesubluck_** - disables Sub Luck
* **_!setsubluck <X>_** - Sets subluck to <X>
* **_!setblp <X>_** - Sets Bad Luck Protection bonus to <X> per loss
* **_!addblp <twitchUser> <X>_** - Adds <X> Bad Luck Protection the the specified Twitch user
* **_!checkblp <twitchUser>_** - Outputs the Base BLP value for a given Twitch user. Does not include Sub Luck.
* **_!wolfricversion_** - Outputs the version number of the currently running instance of WolfricKeystonBot 
* **_!enableblpoverflow_** - Enables BLP Overflow - When someone wins with BLP adding up to more than 100, overflow is re-added to them.
* **_!disableblpoverflow_** - Disables BLP Overflow

#####
* **_!pastwinnersexclude -Number-_** - exclude -number- past winners from draws
#####
* **_!noticetime -Number-_** - change notice timeout to -Number- seconds (Minimum 30, default 30)
* **_!reportsettings_** - Outputs to chat configured settings (BLP, Subluck, Max Roll, Notice Time, Past winner exclude settings)

#####
* **_!quitrafflebot_** - Terminates bot completely
* **_!savevarstosql_** - Saves modified settings (Notice Text, keyword, notice time etc.) to database
  


#### Default settings
* Channel list: Wolfric83 (Will be updated to Zatcharygaming when ready for proper use)
  * Additional hosts must be invited by an existing owner of a channel the bot is currently in by _!invitehost_
* Keyword: "metime"
* Entry Type: Multi Entry Mode (each user can enter once from each channel)
* Past Winners Ignored: 5
* Notice Text: testing raffle system
* Notice Time: 30 seconds
* Draw type: Roll
* Starting roll: 1-1000
* BLP: +1% (added to minumum)
* SubLuck: 30% (added to minimum)

## ToDo:
* ~~change to Rolls instead of random pick~~
  * ~~Reroll on draw~~
* ~~option to add BLP to roll each time someone doesn't win --- in testing~~
* RaffleGroups - ability to have multiple raffle groups (far future)
* ~~Long term storage of BLP (future)~~
* ~~Sub Luck  --- in testing~~
* startup UI?
* SingleChannel Mode?
* Change Defaults
  * Roll type Picking
  * Sub luck on
  * past winners ignored 5
  * Multi-Entry Mode
  * BLP Mode

## BLP Thoughts (Not Yet Implemented)
Base random roll starts at 1000 --- in testing
Optional BLP Factor - Selectable percentage (or add?) - default 1%?
Optional Sub Factor - Selectable percentage (or add?) - default 25%?

BLP and Sub factor combine? (5 missed wins for subscriber = 30% added to max roll number?)
