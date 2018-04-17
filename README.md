# MultiTwitchBot - Wolfrickeystonebot

MultiTwitchBot is an IRC based multi-room raffle bot developed to operate with the Twitch network.

  - Raffles across multiple rooms
  - Invite bot to additional rooms - Authorizations required to comply with twitch bot ToS
  - Magic happens

# Features!

  - Allow single entries per person, or multiple for each room they enter from
  - Internal Mods list (possible future option for any channel mod to perform _-some-_ actions
  - Good Luck Protection - Host Selectable winner exclude system - exclude X previous winners from draw
  - More features to be added by demand...


## How to use

MultiTwitchBot is python based. If you are using the pre-packaged exe, you don't have any pre-requisites other than the exe. (To be provided at a later date - currently executed manually by Wolfric83)

It is recommended to grant mod permission to the bot to prevent dropped messages.


Commands:
* **_!resetrafflebot_** - Leaves all rooms, and resets raffle bot to listen to only your commands
    * _Notifies all rooms_
* **_!invitehost -TwitchName-_** - posts message to current channel requesting response to invite the bot to -TwitchName-
* **_!acceptinvite_** - Required by additional hosts to bring bot into their channel.
* **_!raffleleave_** - Asks RaffleBot to leave your channel
 
* **_!startraffle_** - Resets the current Raffle list, waits for saved keyword for entry to raffle
* **_!changekeyword -Keyword-_** - Changes raffle keyword to -Keyword-
* **_!startraffle_** - Resets the current Raffle list, waits for saved keyword for entry to raffle
* **_!draw_** - Draws one winner and reports to all chats. removes winner from list. multiple !draw commands will pull unique winners until none remain in the current list.
* **_!singleraffle_** - Turn on Single Entry mode
* **_!multiraffle_** - Turn on Multi entory mode (one per User/Channel)
* **_!pastwinnersexclude -Number-_** - exclude -number- past winners from draws
* **_!changenotice -NoticeText-_** - Change the Notice text (what is being raffled) 
    * Example: **_!changenotice Free Gift Sub_**
    * changes repeating notice to: Now Raffling: Free Gift Sub. Enter by typing: -Keyword-
    * will send initial notice: Next raffle draw: Free Gift Sub. by -yourname-
* **_!noticetime -Number-_** - change notice timeout to -Number- seconds (Minimum 30, default 30)

#### Default settings
* Channel list: Wolfric83, wolfrickeystonebot (Will be updated to Zatcharygaming when ready for proper use)
  * Additional hosts must be invited by an existing owner of a channel the bot is currently in by _!invitehost_
* Keyword: "keytime"
* Entry Type: Single Entry Mode
* Past Winners Ignored: 3
* Notice Text: M+15 keys
* Notice Time: 30 seconds

## ToDo:
* change to Rolls instead of random pick
* option to add BLP to roll each time someone doesn't win
* RaffleGroups - ability to have multiple raffle groups (far future)
* Long term storage of BLP (future)
* Sub Luck
* startup UI?
