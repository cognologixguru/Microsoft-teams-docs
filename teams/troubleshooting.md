# Troubleshooting Microsoft Teams Apps


## Tabs 
### Tabs disappear

During the developer preview, any tabs that you created, and uploaded to a team, may have expired after 29 days.  This expiration issue has since been addressed, but you will have to [sideload](sideload.md) the tab again for it to appear in your Tab Gallery.  

Tabs may also disappear during the roll out of a new process for sideloading tabs.  Please check [here](sideload.md) to determine if you need to use this process.

### Blank tab screen

If you are not seeing your content in the tab view, it could be:
* your content cannot be displayed in an `<iframe>`.
* the content domain is not in the [`validDomains`](schema.md#validdomains) list in the manifest.

### The Save button isn't enabled on the settings dialog
Be sure to call `microsoftTeams.setValidityState(true)` once the user has input or selected all required data on your settings page to enable the save button.

### After selecting the Save button, the tab settings cannot be saved.
When adding a tab, if you click the save buttons but are presented with an error message indicating the settings cannot be saved, the problem could be one of two classes of issues.

### The save success message was never recieved
If a save handler was registered using `microsoftTeams.settings.registerOnSaveHandler(handler)`, the callback must call `saveEvent.notifySuccess()`. If the callback doesn't call this within 30 seconds or calls `saveEvent.notifyFailure(reason)` instead, this error will be shown.

If no save handler was registered, the `saveEvent.notifySuccess()` call is automatically made immediately upon the user selecting the save button.

### The provided settings were invalid
The other reason the settings may not be saved is if the call to `microsoftTeams.setSettings(settings)` provided an invalid settings object, or the call wasn't made at all.

Common problems with the settings object:

* `settings.entityID` is missing. This field is required.
* `settings.contentUrl` is missing. This field is required.
* `settings.contentUrl` or the optional `settings.removeUrl`, or `settings.websiteUrl` are provided but not valid. The urls must be https urls and also must either be the same domain as the settings page or specified in the manifest's `validDomains` list.

### Can't authorize the user or display your auth provider in your tab
Unless you are doing silent authentication, you must follow the authentication process provided by the [Microsoft Teams Tab Library](jslibrary.md).  

Also note: due to changes introduced in July, we require all auth flow to start and end on your domain, which must be whitelisted in the `validDomains` object in your manifest.

For more information about authentication, please see [Authenticating a user in your Microsoft Teams pages](auth.md).

### Static tabs not showing up
There is a known issue where updating an existing bot app with a new or updated static tab will not show that tab change when accessing the app from a 1:1 bot conversation.  To see the change, you should test on a new user or test instance, or access the bot from the Apps flyout.

---
## Bots
###  Can't add my bot

Apps must be enabled by the Office 365 Tenant admin for them to be loaded by end users.  Note that in some cases, the O365 Tenant may have multiple SKUs associated with it, and for bots to work in any, they must be enabled in all SKUs.  See [here](https://msdn.microsoft.com/en-us/microsoft-teams/setup#enable-sideloading-of-bots-and-tabs) for more information.


### Can't add bot as a member of a team

Bots must first be sideload into a team before it is accessible within any channel of that team.  Please review [Sideloading your app in a team](sideload.md) for more information on this process.

### My bot doesn't get my message in a channel

Bots in channels only receive messages when they are explicitly @mentioned, even if you are replying to a previous bot message.  The only exception where you might not see the bot name in a message is if the bot receives an imBack action as a result of a CardAction that it originally sent.

### My bot doesn't understand my commands when in a channel

Since bots in channels only receive messages when they are @mentioned, all  messages that your bot receives in a channel will have that @mention in the text field.  It is a best practice to strip the bot name itself out of all incoming text messages before passing along to your parsing logic.  Review [Bots in Channels: Mentions](botsinchannels.md#mentions) for tips on how to handle this case.

---

## Packaging and Sideloading

### Error while reading manifest.json

Most  manifest errors will provide a hint at what specific field is missing or invalid. However, if the json file cannot be read as json at all, this generic error message is used.

Common reasons for manifest read errors:

* Invalid json. Use an IDE such as [Visual Studio Code](https://code.visualstudio.com) or [Visual Studio](https://www.visualstudio.com/vs/) that automatically validates the json syntax.
* Encoding issues. Use UTF-8 for the manifest.json file. Other encodings, specifically with the BOM, may not be readable.
* Malformed Zip package.  The manifest.json must be at the top level of the zip file.  Note that default Mac file compression may place the manifest.json in a subdirectory, which will not properly load in Microsoft Teams.

>Note: there is a current issue with [Description.Long field in the manifest](schema.md#developer) that causes a loading error with a string longer than 256 character.

### Another extension with same id "&lt;id&gt;" exists
If you're attempting to re-upload an updated package with the same id, use the 'Replace' icon at the end of the tab's table row rather than the 'Upload' button again.

If you're not re-uploading an updated package, ensure the id is unique.


