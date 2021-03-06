# Automod

!!! info
    It's **Highly** recommended to use the dashboard for setting up automod. [https://carl.gg/](https://carl.gg)

### General Settings

???+ tldr "General Settings"

	| Name | Example | Usage |
	| :--- | :--- | :--- |
	| **[am\|automod]** | !am | Shows an overview of the current automod settings |
	| **automod drama &lt;channel&gt;** | !automod drama \#watcher |  Lets you set up a channel where mods can make decisions on rule breakers through reactions. This channel should obviously not be made public. |
	| **automod log &lt;channel&gt;** | !automod log \#automod |  Automod actions are pretty different in nature compared to normal modlogs, so with this command you can set the command where automatic actions go. |
	| **automod [media\|mo] &lt;channels...&gt;** | !am mo \#show-off | Some servers have channels where you're just meant to post images/links, this command lets you enforce that. |
	| **automod [unmedia\|umo\|unmo] &lt;channels...&gt;** | !am umo \#show-off | Removes the media-only restriction from one or more channels. |
	| **automod [whitelist\|wl] &lt;roles/channels&gt;** |  !am wl mods \#bilderberg | Whitelists roles and or channels so that automod ignores messages posted in/by them. |
	| **automod [unwhitelist\|unwl] &lt;roles/channels&gt;** | !automod unwl \#bilderberg | Undoes what the above command does. |
	| **deletefiles**  | !deletefiles |  Toggles between deleting files and not. "Safe" formats include png, jpg, jpeg, webm, mp4, gif, bmp, pdf, txt, tif, svg, webp, mp3, flac, wav |
	
???+ example "Punishments"

    The punishments available are:

    * **delete** - Deletes the message 
    * **warn** - Warns the offender 
    * **tempmute &lt;duration&gt;** - Temporarily mutes for the duration, format the time like 3h42m
    * **mute** - Indefinitely mutes 
    * **kick** - Kicks the offender 
    * **tempban &lt;duration&gt;** - Temporarily bans the offender for the duration 
    * **ban** - Bans the offender 
    * **defer** - Sends the context to the drama channel and lets mods vote on it 
    * **message** - Sends a message to the channel warning the member 
    * **dm/pm** - Sends a private message to the offender

    You can add more than one punishment by separating them with commas.
	
### Warn Threshold
	
???+ tldr "Warn Threshold"
	Warns do not automatically expire. Managing warns is detailed on the [Moderation](https://docs.carl.gg/moderation/moderation/) page. The warn threshold determines how Carl-bot reacts when a user receives a new warning and their new total number of warnings exceeds a set limit. Unless a user's warnings are reset or reduced manually, this punishment will trigger each time a user receives a new warning while their total number of warnings is above your server's set limit. Set to 0 to turn off.

	| Name | Example | Usage |
	| :--- | :--- | :--- |
	| **automod [warn\|threshold] &lt;limit&gt;** | !am warn 5 |  Sets the warn threshold for a punishment to be made |
	|  **automod [warnpunish\|wp] &lt;punishments...&gt;** | !am wp kick |  Sets the punishment for hitting the threshold |
	

### Spam Settings

!!! tldr "Spam Settings"

	=== "Message"
		Message spam will not be active without setting a rate limit of at least 1+ messages in 1+ seconds first.
		
		| Name | Example | Usage |
		| :--- | :--- | :--- |
		| **[sm\|slowmode] [rate] [per]** | !slowmode 5 25 | Rate is the number of messages you can post in each time frame. Per is the timeframe. If you only supply one value, it sets that value as the per. \(1/x\) |
		| **slowmode [punishment\|punish\|p] &lt;punishments...&gt;** | !sm p delete, tempmute 20m | Sets the punishment\(s\) for hitting the rate limit. |
		
	=== "Attachments"
		Attachmentspam will not be active without setting a rate limit of at least 1+ files in 1+ seconds first.
		
		| Name | Example | Usage |
		| :--- | :--- | :--- |
		| **attachmentspam [rate] [per=1]** | !attachmentspam 3 5 | Rate limits the number of attachment a member can post in a specific timeframe |
		| **attachmentspam punishment &lt;punishments...&gt;** | !attachmentspam p mute, defer | Sets the punishment\(s\) for hitting the rate limit. |
		
	=== "Mentions"
		Mentionspam will not be active without setting a rate limit of at least 1+ mentions in 1+ seconds first.
		
		| Name | Example | Usage |
		| :--- | :--- | :--- |
		| **mentionspam &lt;rate&gt; [per=1]** | !mentionspam 25 5 | Enables the bot to automatically punish mentionspammers. By default this action is muting, but it can be changed using the next command. |
		| **mentionspam punishment &lt;punishments...&gt;** | !mentionspam p tempban 20h | Sets the punishment\(s\) for hitting the rate limit. |
		
	=== "Links"
		Linkspam will not be active without setting a rate limit of at least 1+ links in 1+ seconds first.
		
		| Name | Example | Usage |
		| :--- | :--- | :--- |
		| **linkspam &lt;rate&gt; [per=1]** | !linkspam 1 1 | Sets the link rate limit. Use the example command to block all links. |
		| **linkspam punishment &lt;punishments...&gt;** | !linkspam p delete, mute, defer | Sets the punishment\(s\) for posting links. |
		| **linkspam** | !linkspam | Shows the current settings |
		| **linkspam bl &lt;links...&gt;** | !linkspam bl reddit.com twitter.com | Blacklists one or more links. |
		| **linkspam wl &lt;links...&gt;** | !linkspam wl discordapp.com facebook.com | Whitelists one or more links |
		| **linkspam unbl &lt;links...&gt;** | !linkspam unbl reddit.com | Removes one ore more links from the blacklist |
		| **linkspam unwl &lt;links...&gt;** | !linkspam unwl discordapp.com | Removes one or more links from the whitelist |
		| **linkspam clearwl** | !linkspam clearwl | Clears the whitelist |
		| **linkspam clearbl** | !linkspam clearbl | Clears the blacklist |
		| **linkspam block** | !linkspam block | Block means it punishes all non-whitelisted links |
		| **linkspam off** | !linkspam off | Off means it only punishes blacklisted links |
		| **linkspam norole** | !linkspam norole | Like on except it only punishes those without roles |
		
	=== "Invites"
		Invitespam will not be active without setting a rate limit of at least 1+ invites in 1+ seconds first.
		
		| Name | Example | Usage |
		| :--- | :--- | :--- |
		| **invitespam &lt;rate&gt; [per=1]** | !invitespam 1 1 | Sets the link rate limit. Use the example command to block all invites. |
		| **invitespam punishment &lt;punishments...&gt;** | !invitespam p mute, delete, defer, message | Sets the punishment\(s\) for posting invites. |
		| **invitespam** | !invitespam | Shows the invitespam settings. |
		| **invitespam bl &lt;invites...&gt;** | !invitespam bl discord.gg/wow | Adds the server the invite goes to to the blacklist. |
		| **invitespam wl &lt;invites...&gt;** | !invitespam wl discord.gg/xd | Adds the server the invite goes to to the whitelist. |
		| **invitespam unbl &lt;invites...&gt;** | !invitespam unbl discord.gg/xd discord.gg/wow | Removes the servers the invites point to from the blacklist |
		| **invitespam unwl &lt;invites...&gt;** | !invitespam unwl discord.gg/xd discord.gg/wow | Removes the servers the invites point to from the whitelist |
		| **invitespam clearbl** | !invitespam clearbl | Removes all servers from the blacklist |
		| **invitespam clearwl** | !invitespam clearwl | Removes all servers from the whitelist |
		| **!invitespam [on\|block]** | !invitespam on | Block means it punishes all non-whitelisted invites |
		| **invitespam off** | !invitespam off | Off means it only punishes blacklisted links. |
		| **invitespam norole** | !invitespam norole | Same as setting it to 'on' except it only affects members without roles. |
		
	=== "Bad Words"
		Bad Words detection is case insensitive, looks for substrings, and ignores punctuation. Censoring "ass" would cause Carl-bot to punish any user that said "class".
		
		| Name | Example | Usage |
		| :--- | :--- | :--- |
		| **censor &lt;words...&gt;** | !censor dick | Adds one or more words to the list of blacklisted words |
		| **censor add &lt;words...&gt;** | !censor add dick | Same as above |
		| **censor remove &lt;words...&gt;** | !censor remove dick | Removes a word from the blacklist |
		| **censor list** | !censor list | Lists all censored words |
		| **censor clear** | !censor clear | Clears all censored words |
		| **censor punish &lt;punishments...&gt;** | !censor p mute, delete, defer |  Sets up punishments for the words. Defaults to delete and defer |
		
	=== "Caps Limit"
	
		| Name | Example | Usage |
		| :--- | :--- | :--- |
		| **capslimit &lt;percentage&gt;** | !capslimit 70 | Punishes messages with x% of its characters being uppercase. The message has to be at least 6 characters long. |
		| **[capspunish\|capsp\|capspunishment] [punishments]** | !capsp delete, warn | Sets the punishment for sending a message which hits the threshold |