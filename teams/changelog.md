# Microsoft Teams developer platform changelog

This changelog covers what's changed in the Microsoft Teams developer platform and documentation, including updates to the APIs as well as new features and tools available to developers.

## August 2017
|**Category**|**Description**|**Link**|
|-|-|-|
|Bots|Added `localTimestamp`; similar to `timestamp` but uses the sender's time zone.|[Sending and receiving messages](botsconversation.md#receiving-messages)|

## July 2017
|**Category**|**Description**|**Link**|
|-|-|-|
|Bot APIs|The Fetch Roster command no longer requires tenant ID in the X-MsTeamsTenantId HTTP request header.  New helper function in Teams Extension SDK.|[Bot APIs](botapis.md#fetching-the-team-roster)|
|Bots|Bots menus are now in Public.|[Bot Menus](botmenu.md)|
|Debugging|Added a new page on debugging tools and techniques.|[Running and Debugging](debugging.md)|
|Samples|Added more information on running samples, and added a new sample for running new Microsoft Teams Graph APIs.|[Sample applications](samples.md)|
|Sideloading|Add updated troubleshooting guidance for errors when sideloading a package.|[Troubleshooting Microsoft Teams Apps](troubleshooting.md#error-while-reading-manifestjson)|
|Tabs|Update auth breaking change, now published.|[Authenticating a user in your Microsoft Teams pages](auth.md)| 

## June 2017
|**Category**|**Description**|**Link**|
|-|-|-|
|Bots|Fetch Channel API call now returning General channel id.|[Fetching the list of channels in a team](botapis.md#fetching-the-list-of-channels-in-a-team)|
|Bots|Added note on creating a deep link to launch a bot in 1:1|[Adding a bot for 1:1 chat only](botsadd.md#adding-a-bot-for-11-chat-only)|
|Compose Extensions| Updated supported layout types. | [Compose Extensions (Preview)](composeextensions.md)|
|Compose Extensions| Update to call out that only one command is supported currently. | [Compose Extensions (Preview)](composeextensions.md)|
|Packaging| Remove 2k limit on icon sizes that prevented sideloading - no restrictions on size now. | [Icons](createpackage.md#icons)|
|Packaging| Changed recommendation to use a Microsoft App ID as the main Manifest ID | [Schema](schema.md#id)|
|Submission|Clarify Dev Center / Seller Dashboard account requirements.|[Register as an app developer](submission.md#register-as-an-app-developer)|
|Tabs|Update on Tab authentication implementation - **breaking change**|[Authenticating a user in your Microsoft Teams pages](auth.md)|
