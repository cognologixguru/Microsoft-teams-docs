# Submit your solutions to the Office Store

>Note: While we have enabled the ability for Microsoft Teams apps to be published in the Office Store, the in-app discovery experience will be available at a future date.

>**Important - Your Microsoft Teams app must use the [latest schema](schema.md) and follow [current packaging guidelines](createpackage.md).**

Microsoft Teams Apps can now be published in the Office Store.  Teams will soon provide an in-app gallery for users to find or discover [high-quality Teams apps](http://aka.ms/microsoftteamsdesignguidelines) powered by the Office store.  To have your solution available in this gallery, you must publish your solution through the Office Store process.  

The Office Store provides a convenient location for you to upload your Microsoft Teams app, as well as other Office 365 extensibility types such as Office Add-ins and Sharepoint Add-ins.  To include you solution in the Office Store, you submit it to the Seller Dashboard.  You will need to create an individual or company account if you have not already done so for other Windows apps or Office extensibility types.

>**Note**: by developing and submitting a Microsoft Teams app, you are subject to the Bot Developer Framework [Terms of Use](https://aka.ms/bf-terms), [Privacy Policy](https://aka.ms/bf-privacy), and [Code of Conduct](https://aka.ms/bf-conduct) for bot, tab, and compose extension functionality within your app.  If your app contains O365 Connector functionality, separate terms may also apply as part of your Connector Registration on the [Connector Developer Portal](https://aka.ms/publishconnector).

## Register as an app developer

Microsoft Store participation is based on registration within the [Microsoft/Windows Dev Center](https://developer.microsoft.com/).  If you have already registered in the Microsoft Store ecosystem, either by distributing a Windows UWA via the Windows Store or an Office or Sharepoint Add-in via the Office Store, you should use this account to distribute your Microsoft Teams app.  Otherwise, you must first [register as an app developer](https://developer.microsoft.com/en-us/store/register) to create your publisher identity in the Microsoft Store ecosystem.  Account registration allows you to secure your company identity and triggers validation checks by the Microsoft Store team to ensure your are who you say you are.

Account management in the Microsoft Store ecosystem relies on a [Microsoft Account](https://account.microsoft.com/account).  To create a new Dev Center / Seller Dashboard account, you'll need to create a new Microsoft account or use an existing one.  Note that this identity will be the main administrator/owner of the Store experience.  For more information, please review [Opening a developer account](https://docs.microsoft.com/en-us/windows/uwp/publish/opening-a-developer-account) and the [Developer program FAQ](https://developer.microsoft.com/en-us/store/register/faq).

>Tip: We recommend you create a new Microsoft account specifically for your Office Store / Dev Center account, e.g. contoso-store-account@outlook.com.  Keep this account and password confidential, and shared with your release team only.

>Note:  while you may have leveraged the Windows Store's AAD support for Windows Store account management, the Office Store Seller Dashboard requires you to use a Microsoft account, not an AAD account.  Please use your original owner Microsoft Account sign-in information for the seller dashboard.

>**Important - If you've developed with a trial developer O365 account, do not use this for your Store identity.**  Create a new Microsoft account instead.

## Register in the Seller Dashboard to submit to the Office Store

There is a second approval process that happens after your Dev Center account has been created:  you need to create your identity in the Office Seller Dashboard.  While the content here should be similar to your Dev Center details, this extra step ensures the Office Store has all the required information, and your identity in that storefront accurately reflects your business.

If you've already submitted other product types for Office Store, this additional registration may not be necessary.

To start the process, click on the "Continue" button under Office.

![Office Seller Dashboard entry point](images/submission/SellerDashboardOfficeEntry.PNG)

## Use the Seller Dashboard to submit to the Office Store
After your account is approved, you can submit your solution to the [Seller Dashboard](http://go.microsoft.com/fwlink/?LinkId=248605).  Add a new Application of type Team App to initiate the submission process.

![Office Seller Dashboard add an app](images/submission/SellerDashboardAddApp.PNG)

You will need to upload a [Submission Package](createpackage.md) and provide the required metadata for the product listing page, including information such as app logo, description, screenshots and other information.  Please review our [Submission and Manifest Metadata Checklist](submissionchecklist.md) for more information.

Note that all information in the package manifest must match the metadata information you enter into the product listing.

For more general information on the Seller Dashboard, see [Use the Seller Dashboard to submit your solution to the Office Store](https://dev.office.com/officestore/docs/use-the-seller-dashboard-to-submit-to-the-office-store).  For more Teams-specific help, see [Submitting your Microsoft Teams app in the Seller Dashboard](submissionguidance.md).

## Teams app approval process

Teams app approval is a free service provided by the Office Store that validates that your app works as described, contains all appropriate metadata, and provides content that would be valuable to an end user.

For your Teams app to be approved:
* It must not contain inadmissible or offensive material.
* It must be stable and functional.
* Any material that you associate with your experience, such as descriptions and support documentation, must be accurate. Use correct spelling, capitalization, punctuation, and grammar in your descriptions and materials.
* It must pass all current [Office Store validation policies](https://dev.office.com/officestore/docs/validation-policies) for Teams tabs and bots.  Please note that these policies are subject to change.
* For tabs, it must provide value in to users outside of what is possible by simply pinning your website into Teams.  This means at minimum, it must remove extraneous chrome and disallow navigating outside the configured context. See the [Microsoft Teams Design Guidelines](https://aka.ms/microsoftteamsdesignguidelines) for more guidance.

When the validation process is complete, you will receive a message to let you know that either your Teams experience is approved, or it fails one of the stated policies.  You can also follow these steps to check the approval status in the Seller Dashboard:
1. Sign in to the Seller Dashboard.
2. On the manage tab, your submission status appears under the submission name.
* If the status is pending approval, your submission is still being verified. When it is in this state, you can't update or resubmit it.
* If the status is approved, your submission is approved to be listed in the appropriate marketplaces.
 
>Note: After your submission is approved in the Seller Dashboard, there might be a delay before it is published in a store. After approval, a submission typically appears in the store within 24 hours.

* If the status is changes requested, your submission needs changes in order to be approved. Choose your submission, and then on the summary page, choose "View the add-in report" for details about the required changes.

Failures will be explained and have appropriate policy violation references. All failures must be addressed before resubmission.

>**Note** If you make changes to an approved Teams experience, specifically as it relates to core functionality or the manifest, it must go through the approval process again.  For all other changes to your service, for example addressing issues or adding new features, resubmission is not required.

## Tips for rapid approval

* Don't use "Teams" or "Microsoft" in your app name, as in all contexts that extra clarification is superfluous.
* If your product requires an account on your or another service, list that in the description.
* If your product requires additional purchases to properly function, list that in the description.
* For your Tab config page, make sure you provide About links and proper guidance - this page will be the first thing the user sees, so make sure a new user understands what to do.
* Make sure your Bot provides appropriate responses when @mentioned in a channel as well as in 1:1 conversations as needed.  If your bot does not provide meaningful context within the personal or teams scope, [disable that scope via the manifest](schema.md#bots).
* Provide the requisite Terms and Privacy policy links in the manifest and the Seller Dashboard, that properly resolve to the correct documentation.  For bots, you must provide this same information in the Bot Framework registration page under the Submission section.
* Ensure metadata in the manifest roughly matches metadata in the Seller Dashboard, and for Bots, the Bot Framework registration.  Note: your Seller Dashboard should contain a more detailed and formatted description for use in the Office Store product page.
* Check your manifest for completeness and accuracy.  Then check it again.
* Make sure you include detailed testing notes and a valid working test account with appropriate prepopulated data.
