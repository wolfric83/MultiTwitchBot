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
  - More features to be added by demand...


## How to use

MultiTwitchBot is python based. If you are using the pre-packaged exe, you don't have any pre-requisites other than the exe. (To be provided at a later date - currently executed manually by Wolfric83)

It is recommended to grant mod permission to the bot to prevent dropped messages.

### Typical use:
Streamer invites additional hosts with **_!invitehost -TwitchName-_**
Additional participating streams accept with **_!acceptinvite_** (Must be the most recently invited host)
Participating streamer types **_!startraffle_**
Viewers on any stream type <Keyword>
... time passes as viewers enter 
Participating streamer types **_!closeraffle_** (optional)
Participating streamer types **_!draw**
  Bot announces winner into stream
Rinse and Repeat



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
* **_!startraffle_** - Resets the current Raffle list, waits for saved keyword for entry to raffle
* **_!closeraffle_** - Stops listening for raffle keywords. saves everything to DB
* **_!draw_** - Stops listening for raffle keywords. saves everything to DB. Draws one winner and reports to all chats. 
    * todo: fix roll draws to remove all of winners entries from raffle
* **_!clearsession_** - Resets session list and past winners list 
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
#####
* **_!pastwinnersexclude -Number-_** - exclude -number- past winners from draws
#####
* **_!noticetime -Number-_** - change notice timeout to -Number- seconds (Minimum 30, default 30)
#####
* **_!quitrafflebot_** - Terminates bot completely


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
* BLP: +1%
* SubLuck: 30%

## ToDo:
* ~~change to Rolls instead of random pick  --- in testing~~~
  * ~~Reroll on draw --- in testing~~
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
