# Authenticating a user in your Microsoft Teams pages

>**NOTE: Recent breaking change for Tab authentication:**
>
> To address a security concern, we have made a change that may impact existing tab auth flows:
>
>Before our July update, we were incorrectly allowing tabs to pop up auth windows to any arbitrary domain and listening to messages from that window as if they came from the domain of the tab content frame. This is no longer permitted.
> 
>We've seen developers commonly use the unintentional behavior to do things like launch an auth popup directly to AAD, redirect back to their tab content's domain, then call notifySuccess. While this is a legitimate scenario, it can also allow a pop-up to a phishing site.
> 
>The recommended approach instead is to direct the auth popup to a page on your domain, redirect to AAD (or whatever login provider), then as normal have that redirect back to your domain. Basically the auth popup has to start and end on your domain.
>
>Since `navigateCrossDomain` isn't supported in the auth window, we recommend your auth start and end domains be the same as your content domain, and listed in the manifest's `validDomains` list.  Note that in the future, we will make changes to allow the auth start and end domains be separate from the content, but for future compatibility, we recommand you put all on the same domain.


---



The tab [configuration](createconfigpage.md) and [content](createcontentpage.md) pages run in iframes.  Azure Active Directory (Azure AD), and other identity providers that you may use, do not usually allow their sign in and consent pages to be hosted within an iframe.  Because of this, your app will need to authenticate the user in a pop up window.  You must use the [Microsoft Teams Tab Library](jslibrary.md) to do this, so that it works successfully in both the web and desktop apps for Microsoft Teams.  

1. Add UI to your configuration or content page to enable the user to sign in when necessary.  You should not drive the authentication pop up without user action, since this is likely to trigger the browser's pop-up blocker.
2. Add the domain of your auth URL to the [`validDomains`](schema.md#validdomains) section of the manifest.  Failure to do so may result in an empty pop up.
3. You can [obtain user context information](getusercontext.md) to help build authentication requests and URLs.  For example, you can use the user's name (upn) as the 'login_hint' for Azure AD sign in, which means the user may need to type less, or even that sign in will complete with no user action at all.  Note that you should **not** use this context directly as proof of identity. For example, an attacker could load your page in a 'malicious browser' and provide it with any information they want.

4. When the user selects to sign in, call `microsoftTeams.authentication.authenticate({url: <auth URL>, width: <width>, height: <height>, successCallback: <successCallback>, failureCallback: <failureCallback>})`.
	
	This launches the pop-up window for the specified identity provider, so the user can sign in. Once the user has completed their authentication, the pop-up window will be redirected to the callback page you specified for your app. 
5. In your app's callback page, call `microsoftTeams.authentication.notifySuccess()` or `microsoftTeams.authentication.notifyFailure()`.
	
	This will result in a callback to the successCallback or failureCallback function that you registered in step two, inside the original configuration or content page.  
6. If successful, you can now refresh or reload the page and show the configuration or content relevant to the now-authenticated user. If authentication fails, display an error message.
7. Your app can set its own session cookie in the usual way so that the user need not sign in again when they return to your tab on the current device.


