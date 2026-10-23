# Paul Dal Pozzo

**Student ID:** s214527809  
**Email:** s214527809@deakin.edu.au  
**Intern Position:** Usability Tester & Bug Hunter  
**Focus Bear Account:** paul_dal_pozzo@hotmail.com  
**GitHub Repo:** https://github.com/pdalpozzo/paul-dalpozzo-focusbear-intern-repo/blob/main/IssueWork/first_time_user_experience.md

# Issue 8

Below are some points of feedback that I have from the initial experience of using Focus Bear.

## Blocking Websites
### Suggestion
I followed the setup wizard and was doing the step where I need to add websites to the block list. My natural instinct was that I would be able to select some bookmarks from my default browser. I am not going to remember the sites that distract me most, but I would definitely have them bookmarked for easy access.

### What is this trying to solve?
It will help smooth out the difficulty of adding websites to block. I personally avoided it because I knew I had a lot to block if I did it right. Most web browsers have the ability to export the bookmarks, so maybe Focus Bear can get that and show a list or folders where the user can select things to block.

Something similar already exists with the application blocking. It seems to list applications that appear in the control panel installed list. 

### Screenshot
Taken during setup wizard  
![](Issue8Images\decorativeimagecoveredframe.png)

Taken after setup wizard  
![](Issue8Images\blockingwebsite-issues.png)

## Decorative Image covered the frame
### Issue
I was on the page 'Which apps do you want to block' and the bear image was coming from the right side of the window. The speech bubble from the bear was reaching the frame of where my focus was. I thought it could be hiding a button. 

### Cause
This was caused by the size of the window. As I made the window larger, I saw that the speech bubble was no longer covering the frame. It was not covering any user interaction options, but it still gave me that feeling that it could be.

### Possible Solution
Allow the user to move the bear image, or do more testing for where things are placed when the window is at its minimum size

### Screenshot
It appears on two scenes  
![](Issue8Images\decorativeimagecoveredframe.png)  

![](Issue8Images\decorativeimagecoveredframe2.png)

## The Bear
### Suggestion
I think the bear mascot is cool. He should be more interactive. Maybe clicking on him multiple times quickly could play a short animation. Maybe let the user pat his head. Maybe let a click remove the speech bubbles. You can teach the user this interaction during the set up wizard. The wizard could start off with the bear looking at a computer screen and the user is told to 'Poke the bear' to get his attention. Then this plays into the whole story of the bear and the user helping each other with focus.

### What is this trying to solve?
The mascot idea is already trying to get a rapport with the user and appear as a friend. Making it interactive will build that relationship and connection. I don't think this idea solves anything, but it just makes the app more friendly and less 'focus on structure'.

### Notes
I have since installed the app on my phone and the bear is much more animated and interactive. This is what I imagined.

## Setting up Block Sessions - Difficult Layout and Imaginary Overlapping
### Issue
During the setup, the 'Set Block Details' page appeared. I had never seen it before because I skipped the setup on my first install. This is a feature that I had been looking for. So I spent some time setting up some blocks.
I set up a 'Morning Work' block. I expected it to appear in the day plan, but it wasn't there.
I set up an 'Afternoon Work' block. I have to set up different time blocks for different days. Monday and Wednesday I have to pick up my son from school, so my work day ends around 2:30pm. Tuesday my son is at my in-laws and I can work until 5:30pm to 6:00pm. Thursday and Friday I have to pick up my son from the bus stop and the bus comes at 4:10pm. As I was setting up these blocks, I was getting told that the blocks have overlapping schedules. 

### Cause
I assume the cause is from the day plan not really understanding which day it is allocated.

### Suggestion
Show the user a full week of planning slots. I saw this feature in the Cold Turkey Blocker research. Most people roughly know how their week is going to be planned out. It makes sense to allow them to allocate blocks for these times. Also, show these blocks in the day view. Show them at a scale where you can show time progressing. Not to add pressure, but to make the user aware of how much of the allocated time has been used. 
To clarify, I am not suggesting these blocks to be sessions. Just predictive blocks. Most people know their work hours and can plan ahead. But then during those blocks, the user can start a focus session and the block/allow lists will automatically apply unless specified otherwise.

Something like I did for the [internship time plan](https://github.com/pdalpozzo/paul-dalpozzo-focusbear-intern-repo/blob/main/IssueWork/internship_time_plan.md) (Issue 2) OR below

![](Issue8Images\coldturkeydaily_scheduleplanner.png)

### Screenshot
This screenshot shows the warning of overlapping schedules  
![](Issue8Images\scheduleconflict-warning.png)

This screenshot shows the result of clicking the 'Save Anyway' button. Where is the overlap? It clearly shows one schedule with Mon-Fri 0900 to 1230 and another Monday only 1300 to 1430 (I converted the times to 24 hour to better see.)  
![](Issue8Images\scheduleconflict-noactualconflict.png)

## Seeing Blocked Sessions and Time Progress on Day View
### Suggestion
The Day View should show session blocks. It should also show the progress though the day. Right now the Day View doesn't work as I expected. The time on the Deep Work section keeps changing. It doesn't seem to match the current time or the time I started the session. I started the session around 0900, it is currently 1053 and the day view is showing 1037. It's really odd. I expected my Morning Work block to appear there.

Morning Blocking  
![](Issue8Images\scheduleconflict-noactualconflict.png)

Day View with no Morning Blocking  
![](Issue8Images\dayview-nosessionblocks.png)


Nothing shows me that I can drag a task from the list on the side to the Deep Work area. Doing so updated the time for me to the current time 1053. Then the task just shows a number value for the time it will take. It should show a block of time progressing. 

This is a quick mockup of what I am suggesting, and basically how I was expecting this feature to work. It is obviously not to scale, but it is just a mock up. The tasks should also appear in it. If task focus is switch, it should show it in the day view.  
![](Issue8Images\dayview-progressIdea.png)

### What is this trying to solve?
This suggestion is trying to give the user feedback and show that their time used to organize things is actually working and paying off.  

***Feedback it could give:*** 
- time progressing through the day
- time spent in a task
- time allocated to a task
- any previous set blocking sessions
- it could work with the meetings features - showing the allocated time
- it could work with a larger break feature - like lunch breaks
- it can show micro-breaks and how regular they occur/offered/completed/delayed/etc

It really is a great place to show everything that has been set in the app. It would create a much easier to understand visual feedback and show how all the features work together.

## Habits in Setup Wizard
### Issue
When setting up the habits through the wizard there where two scenes that confused me and they were back to back.  

First, was the 'Set up habits to focus better'. It has this cool image that looks like a card for each habit. Each card has a title and an image of the bear doing the habit. It looks like a scrolling selection tool. I tried to interact with it that way. I was surprised it wasn't because it has everything is needs apart from the interactions. Instead, this scene does nothing and is just an extra button click.

![](Issue8Images\missedopportunity-scrollingbears.png)

Then, the next scene is the 'Need some fresh ideas for habits?'. I went from thinking 'I was selecting from some pre-made habits' in the previous scene to 'now I am selecting if I want to add my own habits or select from some pre-made habits'. It feels backwards. Why not blend these together?

![](Issue8Images\extraclick-nothinggained.png)

### Suggestion
Make it all one scene.  
![](Issue8Images\scrollingbearsIdea.png)

It is much cleaner. Less steps. More interactive. More visually leading.

### Other Issues
This section actually confuses me further. If you click 'Aye - Give me some ideas, Cap'n' button, the application starts to load what looks like a website. This removes the user from the app. It breaks the flow and adds time to the initial use of the app.

## Goals creating duplicate habits
### Issue
In my initial set up of Focus Bear I set my goals on the 'What are your goals?' page. I think I chose three:
- Boost Productivity
- Improve mental well-being
- Focus on health & fitness

I think this gave my duplicate habits. 'Make my bed' appeared twice. '3 min evening snack' appeared 3 times.

***I think this issue might be out of date. I tried this same sequence again today and the whole scene is different.***

## Time from Creating an account to being allowed to use the app
### Issue
I tested this on PC last week (15th October). It took around 16 minutes to complete the whole setup. It's too long. 

### Suggestion
Allow the QA team to create fake new accounts that go through the setup and time it. Create a graph/tree that tracks time spent on each page, number of clicks, what the result of the page is and some other details. Then you can have actual knowledge of how long setup takes and how to reduce it.

### What is this trying to solve?
One of the major issues on the app is onboarding. Having a long set up is like clicking 'Start Game' and waiting for the 30 minutes of lore to finish. The user wants to see the app. They want to explore it to see if it is worth the time to set things up. This also is part of my next issue/suggestion. 

## Feature dump
### Issue
There are so many features in Focus Bear. So many that even after 2 weeks of using I am still finding and learning more. More features isn't the problem here, its the pace they are given to the user and even how easy they are to find/use. A new user comes along and has no real idea about what the app does or how they can use it to benefit them. And the app just goes 'here is like 30 features, go nuts'. I thought we were making an app for people that can get overwhelmed? This is straight up bad.

It directly affects the two major concerns of the development team: onboarding and retention.
- If there is too much to take in, the user gets overwhelmed, leaves the app, never uses it again.
- If a feature is missed or not explained, the user thinks the app is lacking a feature or is too complex, leaves the app, never comes back.
- Or like me, I have been wanting to suggest a feature and after a week I find a feature that sort of matches what I want but it doesn't quiet work as I expected.

### Suggestion
Pace out the features. How? Well, we already have a progress/levelling system in place. It's hidden, but its there. Use this to allow the user to get used to a feature. Make the levels track time and use of a feature. Make level ups give access to more features.

This brings up the next logical questions:
- What if the user wants to use a feature that is locked?
- Why spend all this time on a feature then lock it?
- What is this actually going to accomplish?

***What if the user wants to use a feature that is locked?***  
Easy solution for this. They can go to the progression page to see when the feature is unlocked. Clicking on the feature will give a brief description of the feature and give them a 'Hold to Unlock Now' button, that requires a 5 second hold. The unlock button will bring up a skip-able tutorial about that feature only.  

What we show:
- the progress needed to unlock the feature
- a description of the feature
- freedom to unlock the feature
- no accidental unlocking of the feature
- a specific tutorial of the feature

***Why spend all this time on a feature then lock it?***  
The whole point of locking the feature is to reduce the initial overwhelm of the app. It doesn't take away the worth of the feature, it just gives the user more time to advance at their own pace. Simple progression like:
- lock the 'Advance' view of the Focus Session tab until a 20 minute focus session has been completed
- lock micro-breaks until a session reaches over 30 minutes
- show the focus log after the first session is completed and it is logged
- unlock Day Plan once there are blocking sessions in place
- unlock Late No More when a calendar is added to the account
- lock adding a calendar to the account until day 2 of using the app

***What is this actually going to accomplish?***  
The goal of this is to slowly introduce new features to the user. It will: 
- reduce the amount of overwhelm when starting
- give the user long term progression goals
- allow them to explore the app at their own pace
- get the tutorial on a feature they want, when they want
- allow the user to focus on a single feature at a time and build that into their routines

All of this together should reduce the amount of users that turn away after a short time, reduce the onboarding time, increase daily use, and increase their understanding of each individual feature.  
Think of video games, each mechanic has its own introduction and usually comes with some small dialogue and a situation where the mechanic help the player advance. It's usually a well tailored event to focus on that mechanic. Giving the player a chance to understand the mechanic before being able to explore how it interacts with other mechanics.  

### Screenshot
The leveling system is already in place  
![](Issue8Images\progresslevels.png)

## Dark Mode
### Issue
This happened to me on the PC version. It was set to 'Never use Dark Mode'. I always use dark mode. It took me like 3 days to find this setting. It's a bit embarrassing. But then, I install the device app on my phone and it automatically is set to 'Use system setting'. I did not even notice that it was in dark mode until I read my notes here and saw I had an issue with it on PC. Which begs the question: why is it not fixed on PC if it is fixed on devices?

This is classic case of 'people only notice when things don't work'. Dark mode was working on my phone and it took me over 30 minutes to realize it was something I didn't need to worry about.

### Suggestion
Set the default to use system settings, or ask the user. Preferably at the start of the initial set up. We are making an app that wants to invite people to use it. What people prefer visually is a major part of that. It is a very important step.

## Habit editing requires reset
### Issue
Changing any habit settings requires the app to reset. It breaks flow. It is tedious for small changes. The reset is very jarring. I will spend a minute setting up my tasks and focus session. Then when I make a change to a habit, I lose some of that set up. My active tasks are gone from my session. My session time resets while keeping the remaining duration. Although, it seems to not work correctly. The focus log does eventually show the time spent, but there is a delay and feels like that time and effort is lost.

### Suggestion
I do not know how the inner workings of this feature work. But The flow is broken. From what I see I assume:
- there is a authentication handshake to the habit editing website
- a fetching of the users habits
- then it loads all the data

I'm not sure there is a way to bypass this. An alternative is a bit more risky and more likely to get out of sync. You could load this data when loading the application. Have a temporary local version. Then when changes are made, save them behind the scenes. If something needs to reload, do it in the background while leaving the main focus session functionality working. Or you could have a queue of changes that process the next time the application loads or shuts down.

This might bring up issues about syncing across multiple devices. I'm sure there is something that will break. But, the user will most likely be using one device more often than another. If I am mostly interacting with the PC app, then I am probably on my PC working. If I am interacting with the device app, then I am probably going about my free time.

I don't know if there is a good solution here, I just know that it breaks flow and messes up some of the features.

### Screenshots
The focus session before a habit reset (4 mins of 2 hr 30 min)  
![](Issue8Images\beforehabitreset.png)  

The pop up when saving a habit change  
![](Issue8Images\resetpopup.png)  

The focus session after a habit reset (0 sec of 2 hr 24 min)  
![](Issue8Images\afterhabitreset.png)  

The focus session losing duration time instead of gaining time past (0 sec of 2 hr 19 min)  
![](Issue8Images\focussessionlosingtime.png)  

## Focus Button
### Issue
I want the focus button to be purchasable in the application. With that, we could promote the purchase of the focus button. After a week of using the app, tell the user about the focus button. But, instead of just having a close button for the pop up, have 'Buy Now', 'Remind me later' and 'Not Interested' buttons. The reminder button can just activate a weekly/monthly reminder about the button.

There is also a minor issue when purchasing the focus button on the website.

### Screenshots
This shows where I expected to be able to buy the focus button through the app. I don't really want to go to an external website. Just let me purchase it here.   
![](Issue8Images\shouldhavebuyoptionhere.png)  

This shows the close button not being anchored at the top of the focus button purchase popup  
![](Issue8Images\focusbuttonpurchasepopup-noclosewhenscrollingdown.png)  

## Habit Export/Import
### Suggestion
I made a new account for this issue. But I really like the habits I have set up on this account. Maybe habits could have an import and export system. You could share habits, get community made habit packages and maybe even extend the feature to share session block times and block lists.

### What is this trying to solve?
Nothing. I just think this is cool.

## Friends List
### Suggestion
It would be nice to have a friends list. Maybe I want to see them on the leaderboard or share habits with them. Maybe I want to organize a meeting or a free time session with them. I could brag about my level and habit streaks. You could ask your friends to control the breakout password for that session.

### What is this trying to solve?
Nothing. I just think this is cool.

## Sign up and Log in
### Issue
I always have an issue with these pages. I understand that there are some differences to the tasks and pages. But, let's try to make something better. Both pages are the same, in fact, there are 2 lots of 2 pages that are all the same. They could be all on the single page.

### Sign In and Sign Up Screenshots
The sign in page (existing user)  
![](Issue8Images\signin.png)  

The sign up page (create user)  
![](Issue8Images\signup.png)  

Both of these pages hold the same fields and details. A bit of simple logic when the button is pressed will allow us to make these the same page and allow the user to not worry about which page they are on exactly. The password rules are fine to show on a sign in page. so many times I have made accounts where I have forgotten the rules of the password and cannot log in.
- If the email address is in use, assume it is an existing user. Check the password. If its incorrect, alert the user that the email address already has an account and the password does not match.
- If the email address does not exist, then create the account with the password.  

I don't see this as bad feedback or too much feedback that can be used as a brute force hack. The password rules are available for anyone to see. Knowing the email is already in use doesn't change anything. A user could type in every combination of emails to find that out. Knowing the password is incorrect doesn't give any more information to a hacker, but it gives a real account user more information.

### Sign In and Sign Up Screenshots
The existing user page  
![](Issue8Images\existingaccount.png)  

The create user page  
![](Issue8Images\createaccount.png)  

They are the same page. A bit od simple logic on each button could handle each scenario.

### Suggestion
This page could handle all cases that the 4 pages above could handle. Less clicks, less worries.  
![](Issue8Images\accountidea.png)  

## Time Tracker
### Issue
This feature is so good at showing how distracted the user gets. It gives all the information that I was expecting to see in the Day View page. And it is hidden. It's so well hidden that I found it 2 weeks into using Focus Bear, then couldn't even find it a week later. This feature can be used to show good and bad habits, how the user improves the productivity over time. Why not show it to them.

This is what makes the whole app work. It tracks everything. Why isn't it shown to the user? Why is it so hidden?

Note: You can find it here: Settings > Advanced > Time Tracker

### Suggestion
This pretty much blends into the suggestion I made above with the Day View stuff. But it can be taken further. You can do a weekly rundown in graph form. Allow the graph to be interactive. Maybe show it to the user as a colour coded bar graph for each day: green for deep work, red for distracted, blue for breaks. Then let them interact. Offer a habit/session/distraction total time bar graph, or even a pie graph if they want to see the percentage of the week. 

![](Issue8Images\weeklytrackergraph.png)     ![](Issue8Images\timespentgraph.png)  

## Tab Audit
### Issue 
This feature is cool but is there a point to it? I have been using the application on PC for 3 weeks and I have never used it. Maybe I need to have a rabbit hole experience for it to become useful?

I feel like this is a function a programmer would use but a normal person would be like 'What is URLs and CSV?' Unless it can be converted into a visual for simple minds to understand it immediately, it is probably best outside of the hands of the user.

### Suggestion
No real suggestion here. Just that more consideration needs to be put into why the feature exists, and how people can use it to get a benefit. Right now, it just seems like a cool way to list tabs on a browser and in a form that is not really inviting to a non-programmer.

## Have Tutorial Focus Sessions
### Suggestion
This one is pretty cool idea. The user should be able to use the app to trigger a tutorial of the app. This sounds confusing, so let me explain.

A first time user installs the app. The app opens to the Focus Session page. Everything else is locked. The page has a few options: 
- Tutorial of Focus Bear
- My First Focus Session
- I've done this before, Don't baby me.

***I've done this before, Don't baby me.***  
Simple. This button is pressed and it removes all the tutorial stuff. The user can now interact with Focus Bear like an experienced user.

***My First Focus Session***  
Starts a Focus Session for 20 minutes. Removes all tutorial stuff.

***Tutorial of Focus Bear***  
Provides a step by step guide on how to use Focus Bear. Obviously, it will start with the hero of the application; focus sessions. Steps through the focus session page, explaining each button. Guides the user through setting a session time, how to set an active task, how to switch up the tasks and how to end a session. When the user gets to the end of the tutorial, they can be prompted about the Block List tutorial. They can end the tutorial if they want and have access to the tools they know, or they can continue and unlock Block Lists.  
The tutorial is a session block with tasks and goals. When the user activates it, the app loads that scenario and guides the user through the new feature. Allowing us to provide more specific tutorials at a shorter duration. And allowing the user to choose when to activate the tutorial.

## Bugs I have Reported
I have reported a single bug at the moment. This is evidence that I know how to do it and will eventually log all these issues/suggestions from this document. I will do it, but it will take time, maybe a few days next week.

Its ID is 3YQAYX  
![](Issue8Images\bugreported.png)  
