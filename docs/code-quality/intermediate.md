# Intermediate

## Table of contents
- [Intermediate](#intermediate)
  - [Table of contents](#table-of-contents)
  - [Consider All Screen Sizes](#consider-all-screen-sizes)
    - [Phones](#phones)
    - [Tablets](#tablets)
    - [Responsive Desktop Screens](#responsive-desktop-screens)
    - [Unique Screen Formats](#unique-screen-formats)
  - [Consider All Screen States and Scenarios](#consider-all-screen-states-and-scenarios)
    - [States](#states)
    - [Scenarios](#scenarios)
    - [Game Modes](#game-modes)
    - [Player Types](#player-types)
    - [Questions To Ask](#questions-to-ask)
  - [Consider Languages](#consider-languages)
  - [Competitive Analysis](#competitive-analysis)
  - [Fits Colonist Artistic Style, Branding and Vision](#fits-colonist-artistic-style-branding-and-vision)
  - [Fits Colonist Vision \& Pillars](#fits-colonist-vision--pillars)
  - [Understanding Users](#understanding-users)
    - [Polling](#polling)
  - [Review](#review)

## Consider All Screen Sizes

### Phones
- Always consider phone nooks
- Use 390x844px(2.16x), 360x800(2.22x), 360x640(1.77x) wherever necessary 
  - You should use the other 2 sizes wherever necessary. Example: https://www.loom.com/share/baa49bf5daea418b91302a4fc8ac45c7
  - All other mobile phone sizes are multiples of these 3 sizes https://i.imgur.com/fVCAPtQ.png
- We don't design specifically for Apple/Android devices. Instead we accommodate the smallest screen sizes used by a significant number of users.

### Tablets
- Always design in Portrait(Vertical) for the mobile app.
- Use 640x1024(smallest recommended tablet size for testing) and 768x1024(most popular tablet size) wherever necessary
     - https://developer.android.com/docs/quality-guidelines/large-screen-app-quality
     - https://www.hobo-web.co.uk/best-screen-size/#:~:text=Design%20for%20desktop%20displays%20from,962%20through%201280%C3%97800
     - most popular screen resolutions: https://gs.statcounter.com/screen-resolution-stats 

### Responsive Desktop Screens
- Desktop: 1440x900

even if [1920x1080 is the most widely desktop screen today](https://www.altamira.ai/blog/common-screen-sizes-for-responsive-web-design/)we should still be designing for 1440x900. Reason for this is that some players are playing in a smaller browser screen compared to their desktop and its a good practice to [design in a small screen and make it bigger](https://thewhitelabelagency.com/recommended-screen-resolution-for-web-design/) compared to designing it big and making it responsive to a smaller screen

Consider different screen sizes: https://prnt.sc/w0vSLSNHRTLk

### Unique Screen Formats
- Discord Game Labs (https://prnt.sc/RqNuctEblZ0A)doesn't allow full screen so we shouldn't do our usual format of 1440x900. Its better to design in a smaller format of 1280x720.

We might design some other screen with unique formats in the future. Keep in mind that it should be responsive and workable on that format

## Consider All Screen States and Scenarios

### States
To know about screen states: [See This](https://xd.adobe.com/ideas/process/ui-design/designing-interactive-buttons-states/)

You need to think and show what happens in different screen states. some examples: 
- Disconnections
- Page refreshing
- Page Loading
- Hovering
- When the user is signed vs Guest
- User is subscribed vs free
- Slow internet

### Scenarios
To know about scenarios: [See This](https://www.interaction-design.org/literature/topics/user-scenarios#:~:text=User%20scenarios%20are%20detailed%20descriptions,needs%20and%20behaviors%20of%20users.)

Scenarios are based on the states. 

Ex. Leaderboards

some samples for scenarios inside the Leaderboards are:
- When a player clicks on a country/state/region tab
- When a player clicks on another player details
- When a player hovers an info icon
- When a player scrolls up/down the list
- When a player searches for another player in the leaderboard search bar

You should also consider edge cases such as:
- when a player's name is too long. will it exceed the space given or cut it out?

### Game Modes
This is the [current in-game screen](https://prnt.sc/gbMYZkWCJpo0)

Consider the below game modes. Accommodate future game modes as well.

- Base
- 5-6 & 7-8 player
- C&K
- SF
- SF, C&K, 7-8 player

### Player Types

- New player who doesn't know Catan
- New player who knows Catan but not Colonist
- New player who knows Catan & Colonist but hasn't played for a while
- Player who plays weekly (casual)
- Player who plays daily (hardcore)
  - These players prefer speed. Want to do stuff faster
  - These players have high familiarity and muscle memory

### Questions To Ask
- https://uxplanet.org/98-questions-ux-designers-must-ask-9b6984c6bd67?gi=66ccaed81478
- What will this design make people do more?
- How will it change behavior?
- What will be the consequences of those behaviors?
- Is that something we want?
- What do we want players to do?
- How often will the player use this with respect to rest of the items on the screen? Should we hide it or show it more?
- What other parts of the app can this be used with? Should designs be done changing parts?

_Note: some questions may not be applicable to certain tasks. You should be able to differentiate what is effective and what is not_

## Competitive Analysis
- You should have an eye for detail when it comes to how other games do a particular feature.
- Create an understable research format. something like this (https://prnt.sc/zHvH8tMuaQQj) and write your own insights
- Check https://www.gameuidatabase.com/ for a library of 500+ games to look at. Feel free to use whatever resource you have, be it using screenshot on a youtube video or you trying out the game or website itself. 

## Fits Colonist Artistic Style, Branding and Vision
All designs must fit Colonist artistic style. If you want to suggest a new artistic style make sure to show it separately than the UX changes.

Traverse Colonist.io to get a feel for our style.

## Fits Colonist Vision & Pillars

For every element designer should ask why until hitting one of our [Pillars](https://prnt.sc/WZfNIlQO8LlG) or [Values](https://prnt.sc/YdIQhovDbO2i)
If there are no pillars to direct the design decision a new pillar or guide should be suggested
No design should be subjective. All designs should be objective & scientific.

## Understanding Users
Your design is probably wrong if you don't know what the user wants. Here are a few ways of understanding users.

1. Check https://colonist.featureupvote.com for any related suggestion.
2. Post in public channels on Discord.
3. DM players who seem interested to give feedback
4. Making a prototype and observing testers interact with it

### Polling

It's a good way to gather certain insights on users.
Here is an example way of creating a poll: https://www.loom.com/share/7c891b3adb194764923bab235d9d3a0b 

## Review

- You need to be reviewing at least the amount of work you’re creating
- You should make sure the design is perfect, you should increase the quality of your peers and expect more from them

Good Example: https://i.imgur.com/BrAistC.jpg 20+ comments
