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

## Dark Mode
### Issue
This happened to me on the PC version. It was set to 'Never use Dark Mode'. I always use dark mode. It took me like 3 days to find this setting. It's a bit embarrassing. But then, I install the device app on my phone and it automatically is set to 'Use system setting'. I did not even notice that it was in dark mode until I read my notes here and saw I had an issue with it on PC. Which begs the question: why is it not fixed on PC if it is fixed on devices?

This is classic case of 'people only notice when things don't work'. Dark mode was working on my phone and it took me over 30 minutes to realize it was something I didn't need to worry about.

### Suggestion
Set the default to use system settings, or ask the user. Preferably at the start of the initial set up. We are making an app that wants to invite people to use it. What people prefer visually is a major part of that. It is a very important step.

## Habit editing requires reset
resetting after habit editting breaks flow and control - even minor changes and saves cause a reset

## Focus Button
x to close should always be visible - focus button purchase
purchasing the focus button could maybe be in the app? it should also be suggested to the user after a week of using the app.

## Habit Export/Import
i made a new account for this experience - but i really like the habits i have set up - maybe needs an import and export system for habits
or maybe you can explore your friends habits and copy them? is there a friends list? would that be too distracting?

## Friends List

## Sign up and Log in
sign up and log in pages are exactly the same - why not just assume if the email is existing and the password is correct that the user is trying to log in?

## Time Tracker
Settings > Advanced > Time Tracker
enable focus bear time tracker - is this the feature tht i think it is? will this allow me to see my bad habits and time spent doing things? why isn't it mentioned anywhere? why isnt it in graph format?

## Tab Audit
tab audit - i removed this from my pc app, but it appears when i log in on the laptop
tab audit is a cool idea, but no normal user will know what urls to csv is, they will never click it, it is too uninviting

## Have Set Focus Sessions
there should be a focus session that gives a tutorial through the whole app or maybe one feature at a time. it should be easy to click and should be able to be viewed however many times the user wants.

## Stats Page
the stats page needs to be more accessible and presentable it has a lot of good information
habit stats is really good, i like the bars - but i have drink water at 75% in most consistent habit and drink water at 0% in least consistent habit - are they at different times? should the habit be consolidated? maybe the habit should only be added once and then added to breaks and routines so that the data stays in the correxct places.




