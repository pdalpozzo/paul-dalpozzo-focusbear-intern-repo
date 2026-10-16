# Paul Dal Pozzo

**Student ID:** s214527809  
**Email:** s214527809@deakin.edu.au  
**Intern Position:** Usability Tester & Bug Hunter  
**Focus Bear Account:** paul_dal_pozzo@hotmail.com  
**GitHub Repo:** https://github.com/pdalpozzo/paul-dalpozzo-focusbear-intern-repo/blob/main/IssueWork/AI-Usage-Guidelines.md

# Issue 10

## Research & Learn
**What AI tools are typically used for your role?**  
Because I have no idea where to start with this task and I don't want to spend hours researching, I used Google's Gemini AI in Chrome to help me find products. It gave me a list of AI tools used for each part of my role; Usability Testing and Bug Hunting

***AI Usability & Visual UX Testing Tools***
- Applitools Eyes - $677/month ($8,124/year) - Pure AI testing for visual validation.
- Maze - Free with limited access to its tools - Offers tester recruiting. Uses AI to analyze videos.
- PlaybookUX - $5,400/year - Offers tester recruiting. Uses AI to analyze videos.
- testRigor - Free with limited access to its tools - Uses AI to turn English into step by step tests.

***Bug Hunting & QA Automation Tools***
- Mabl - Verifies your code works, eliminates maintenance and produces audits as proof.
- Testim - AI driven testing that takes English commands to create tests.
- Momentic - An AI QA tester. It explores the code for bugs and gives a report on how to reproduce them.

**What are the benefits and risks of using AI in a professional setting?**  
***Benefits***
- Speed - AI allows us to produce and test code so much faster
- Accuracy - AI can produce code that is more efficient and more accurate at reaching the goals given
- Less Bugs - Using multiple agents allows users to test code and search for bugs much faster
- Data Capture - AI can capture much more data and analyze it

***Risks***
- Lack of Context - Using AI incorrectly can produce code that lacks context of the project and its goals
- A Black Box - AI generate code can become a 'black box' where the developer doesn't know or understand what the code does
- Hallucinations - AI can get stuck on things and loop around on itself. This usually happens when it is trying to keep a large context
- Security - not just lack of security in the code, but giving models access to sensitive information can cause a form of data leaking

**What types of information should never be entered into AI tools?**  
Anything that is sensitive. This includes confidential information about the company or users. Things like passwords, addresses, future projects, user habits and anything that could cause an ethical issue.

**How can you fact-check and validate AI-generated content to ensure accuracy?**
Ask the AI for links to its sources. Explore the sources to increase your understanding of what the AI is using to base its assumptions. Generate proper tests to test whatever has been produced by AI. Ask the AI to breakdown what it has done in a step by step line by line way. Ask the AI to create documentation for the task it completed.

With my experience of using AI I have found that you want to:
- create documents to hold hard decisions. A file it can refer to in multiple chats, like a memory.
- use multiple shorter chats instead of a single large chat. This not only reduces the tokens used, but reduces the chances of hallucination
- get AI to 'interview' you about the task/feature/mechanic you want it to produce.
- specifically tell the AI to never assume things and to always ask for you to make decisions.
- create documents of what has been produced and any reasons behind that feature.

## Reflection
**When should you use AI for assistance, and when should you rely on your own skills?**  
It is ok to ask AI for assistance anytime. But do not ever give it the full picture and never give it sensitive data. AI is a good tool to start a task when you have no idea how to start or have too many options on where to start. Relying too much on AI will result in your own skills being under developed. This will not help you in the long run.

I find it comforting to ask AI how a task is typically done. I usually do this after I have created my own idea of the task in pseudocode. Then I start asking it questions to see if my assumptions cause any issues and how it differs from what it claims is the typical way of doing things.

In the end, you need to test and understand what the AI has done. So, you need your skills to keep up with the AI. This is why it is always best to try implement things yourself before asking AI to do it for you. Or if you do ask AI for assistance, only give it part of the problem so that you cannot just copy and paste its solution. Getting only part of the solution will require you to understand the full context that the AI wasn't given and you will learn things while implementing the full solution.

**How can you avoid over-reliance on AI while still benefiting from it?**  
- Lay down some foundation rules and keep them in a document for the AI to look up for each chat.
- Never allow it to assume anything. Make sure the AI asks you questions and verify them before any code gets done.
- Create tests.
- Read through what the AI produced.
- Never give the AI the full context or permission to change many things.
- Keep the changes small and with little spread so that AI doesn't seep into all parts of the code.
- Come up with the solutions yourself and understand the skills needed for the solution so you can check the work that AI does

**What steps will you take to ensure data privacy when using AI tools?**  
I will never use real data from my usage or any data from a real database. I would set up a test set of data that I can use and that way no real data will ever get leaked.

## Task
**Identify one task you can improve using an AI tool, and try it out.**  
I have recently been making a game prototype with AI. I have been getting the AI to code and commit changes to the prototype. This has sped up the speed of my production. Things that would take days or weeks, now take a few hours.

**Review the AI-generated output critically—did it require editing or fact-checking?**  
I review and play test every update before I sign off on the mechanic. I always play test any changes no matter how minor. As for fact-checking or editing, I don't really need to do that in my process. I have a document that is maintained and added to after every mechanic is signed off. This document keeps the AI in line and allows me to avoid hallucinations. It also keeps me in check as the AI can point out conflicting methods that I have already told it not to do.

**Document one best practice you will follow when using AI tools at Focus Bear.**  
I will never copy and paste from AI. I know that I have stated above that I trust it for some things. But this is a job and many people will be affected by anything I do. I will not risk that. Plus I am here to learn. I will ask AI for ideas on how tasks are typically done and use that as a way to explore implementation of ideas, but I will not ask it to create something and will never ask it to look at the repository or code base directly.

Of course, I will always try to solve the issue myself before turning to AI. You cannot learn if you do not at least attempt it.