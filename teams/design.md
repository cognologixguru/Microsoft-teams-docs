# Design a great Microsoft Teams app

Microsoft Teams places content in the middle of everyday conversations.  Take a look at some ideas you can use to showcase your brand within Microsoft Teams.

>For more details and full guidance, complete with style guides and examples, please review our full [Design guidelines site](http://aka.ms/microsoftteamsdesignguidelines).

# Building a great Tab 

Tabs give your app a dedicated canvas at the center of a team’s workflow, allowing teams to jump between conversations and your experience.  While it's relatively easy to adapt a web app to become a Microsoft Teams tab, you should consider which experiences and functionality in your app will work most effectively.

## Select relevant app functionality

Teams add configurable tabs to channels. A channel is a specific topic or purpose that the team has. Find the concept(s) in your app that best fit this context.  Users will be more likely want to add these as a tab. For example, the Planner tab for a channel contains a single plan.  The Power BI tab maps to a specific report.

Use static tabs for your single user experience.  For example, if your service is a notetaking app, add a tab that holds personal notes.  That way, a user can refer to their own notes without having to share them with an entire team.

## Scope and focus the user experience

Once configured, configurable tabs should drill down to the relevant context and not let the user navigate outside of it within the tab. For example, the Power BI tab doesn't enable the user navigate to other Power BI reports in situ.  However, like many tabs based on an existing web app, it does enable the **Go To Website** button that launches the report in the main Power BI website.

## Integrate with the Microsoft Teams user experience

Your tab experience should feel integrated into Microsoft Teams. If you are adapting an existing web app, do not include your usual web app chrome, or display navigational dead ends. 

## Streamline access 

Consider how to enable access permissions for your tab. Microsoft Teams is based on [Office Modern Groups](https://support.office.com/en-us/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2), so consider supporting permissions for them. At a minimum, you should make it easy for each new user to request access when they visit the tab. Or consider if you can make the content generally available without requesting additional permissions.

# Building a great Bot

Bots are conversational apps that perform a narrow or specific set of tasks. They give you an opportunity to communicate with users, respond to their questions, and proactively notify them about changes. They're a great way to reach out.

## Be responsive

In general, your bot must respond to every message, especially common questions like "help" and "hello."  Your bot should also be able to handle the following types of queries and inputs: 

* Recognized questions - These are the “best case scenario” questions you’d anticipate from users.
* Recognized non-questions - Queries about unsupported functionality, random pieces of information, or when someone wants to curse at your bot.
* Unrecognized questions - Unintelligible inputs (i.e., gibberish).

## Say hello

Leverage the [bot event messages](botevents.md) to make sure your bot introduces itself when added to a team, or first accessed in one-on-one.  This is an opportunity to tell the user what value you bring to their workday.

# Building a great Compose Extension

Compose extensions allow you to share rich cards in a conversation. A card can hold instructions to complete a complex task or a simple GIF. Microsoft Teams comes equipped with several compose extensions already. If you look below the compose box, you’ll see a "GIF" icon. Click it, and you’ll see a menu with options to select a featured GIF or search for a specific one—that’s a compose extension! These extensions are one of the best ways to create shareable content and serve information quickly.

## Optimize your search results

A snappy compose extension will return an easily digestible list of search results. We recommend including an image and no more than two lines of text.

## Optimize your cards

Each compose extension culminates in a card. Since it’s the last thing your user will see, make sure your cards are useful, good-looking, and easy to share.
