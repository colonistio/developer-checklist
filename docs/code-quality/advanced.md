# Advanced

## Table of contents
- [Advanced](#advanced)
	- [Table of contents](#table-of-contents)
	- [Large Update Rules](#large-update-rules)
	- [Add Comments](#add-comments)
	- [Write Tests](#write-tests)
	- [Force Push](#force-push)
	- [Don't Overengineer](#dont-overengineer)
	- [Use Existing Code](#use-existing-code)
	- [Understand Impact](#understand-impact)
	- [Suggesting A Library](#suggesting-a-library)
	- [Knowing What You Don't Know](#knowing-what-you-dont-know)
	- [Aware of Impact](#aware-of-impact)

## Large Update Rules

Any issue that requires more than 10 commits or 50 lines of code can be considered a large update (unless it is pure refactor)

1. If you're doing a big feature, first create a branch and do a rough version of the feature that works, without worrying much about commit readability and architecture
2. Push that branch to Github as a draft PR
3. Review your commit at PR UI from the eye of reviewer 
4. Give yourself stuff to fix, like change var name, separate variables, split function into multiple, do better architecture, etc..
5. Then create a todo list, and how could the architecture have been done cleanly
6. Create a new branch
7. Start moving code to new branch and rewrite everything but in a clean, final way
8. If this feature will require multiple PRs, then create a main PR, then write code in parts in the PRs.
	- Example: https://prnt.sc/2011xo4
	- Video explanation: https://www.loom.com/share/703185b81607482ea304838064d34578
9. If a code/logic is hard to understand first create a PR that refactors that part of the code, once its approved create the new feature
10. If you have to merge development branch please make sure to follow following. It will help to track commits properly
    - squash merge them
	- merge it in the main branch only
	- if you need development in sub branch, merge it in the main branch first and then create a sub branch from it
	- Bad example: https://prnt.sc/9gbezql7iQ0P

## Add Comments

We try to avoid comments as much as possible but under certain circumstances they need to be added.
Temporary, Optional & Confusing codes need explanation.
Leave a comment like this: https://prnt.sc/20125e9

## Write Tests

Complex logic should always be tested 
Examples: https://prnt.sc/20127k6 https://prnt.sc/20127s7

## Force Push

- Do not force push on branches that have received feedback
- Instead fork your previous branch, create a new feedback branch and do the updates there and merge into your original branch. https://www.loom.com/share/9bf9e79e21bc442498182571c6d62517

## Don't Overengineer

We're trying to solve problems we have right now. We don't want to solve theoretical problems or solve wide variety of problems that open source libraries have to do. 

Example conversation of overengineering: https://prnt.sc/o2fSYom1C3tq
## Use Existing Code

When you're writing a new code, ask yourself if there could be anything like this in the codebase. Search for it and use that one. We don't want duplicate logic.

## Understand Impact

Make sure you are always working on the most impactful task you can work on. Here are some questions to make it easier.

- Are the tasks you're choosing helping move the needle?
- Are you able to increase our metrics with this task? 
- Are you solving an important problem? 

## Suggesting A Library

Each dependency creates extra headaches. 
Examples:
- We use Digital Ocean instead of our own servers -> Twice a year site stops working. Players complain. We spend hours debugging. Turns out it's DOs fault.
- We use Cloudflare instead of building our own -> Once a year site stops working. Players complain. We spend hours debugging. Turns out it's Cloudflare's fault.
- We use PIXI instead of vanilla canvas -> Once a year players complain. The game doesn't work for some people. Turns out Chrome pushed a code which breaks the PIXI version we use.

99% of the dependencies we've added has caused problems. Which is why we avoid external libraries like they are plagues.
As long as the library is something we can avoid, we try to avoid it.

When suggesting a library, consider the following points:
- Ensure that the library you're suggesting addresses a specific problem or significantly improves the existing codebase in terms of functionality, maintainability, or performance.
-  Investigate the library's history, reputation, and community support. Check if it's actively maintained, if it has frequent updates, and if it has an active community. High levels of user adoption mean that there is a community out there that can help when you run into trouble.
-  Weigh the benefits of using the library against the potential drawbacks. Consider both the immediate impact and the long-term consequences.
-  Implement a small demo or a proof of concept that showcases how the library can be used in the project. This will provide evidence of the library's value.
-  Make it clear how the library can improve the project and why it's worth the potential risks.

https://qz.com/646467/how-one-programmer-broke-the-internet-by-deleting-a-tiny-piece-of-code

## Knowing What You Don't Know

A good developer knows stuff.
A wise developer knows what they don't know.

While the good developer will seek to merge their code. The wise developer will know what PRs 
- doesn't need review (100% safe)
- needs normal review (mostly safe)
- needs review from a specific person (requires a unique information)
- needs through analysis (very risky)

When submitting riskier PRs, a wise developer will break it up into its core elements so its very easy for the expert to evaluate the solution.
A wise developer will also tag the right people to keep them informed about the changes. Example: https://prnt.sc/0Z0aXo_-5_La

Example of a wise developer: 
- Demi is an experienced frontend developer. He works on both familiar and unfamiliar areas.
- He is responsible for ensuring high-quality code across all areas.
- For familiar frontend tasks, Demi confidently merges the PRs without requesting reviews, but he tags team members to inform them of the changes. For unfamiliar areas like database-related changes, he seeks reviews and doesn't merge PRs until he's certain the code is correct. He also tags QA, suggesting areas to focus on during testing.
- Demi's approach results in 99% accuracy on both familiar and unfamiliar tasks. This makes his work reliable and boosts the team's confidence in his ability to merge PRs without extensive oversight.

More info: https://i.imgur.com/3se5aKq.png
  - In our organization the people who get merge access to branches have this trait. The others all need reviews.
  - These people know what they don't know
  - Example(good): 
  - Example(bad): When a junior codes a project. They may not request reviews. They might assume its okay. They might not be able to think 2nd 3rd order effects etc. 
  - Example(design): A trustworthy designer will know what parts of the designs is obviously good and what parts need user testing. They'll make sure to get user testing. They'll also make sure to ask team mates hey I see this in the previous design was there a monetization etc. need? Same as dev. They know they are missing information there and get review from the right person. When they fail at making something thats up to standard, they admit it, ask another designer for help or turn to their friends, network etc.. making sure when they submit it will be up to our standard.
  - Example(bad): They design something and submit it. They get feedback to do polls, user testing, more iterations, retention, monetization or any other metric considerations. These people will not get promoted. Since we can never trust them to deliver a 110% safe work.

## Aware of Impact

Spend time on higher impact issues.

Some refactors take 5 hours but expected to save future developers 5 minutes per month. If 3 devs look at those files, it will save 30 minutes per month where the break even occurs at 20 months. 
Some refactors take 5 hours but expected to save future developers 1 hour per month. If 2 devs look at that file, break even occurs at 2.5 months.

Basic Impact Layers:
- 1% of players will see and it effects UX slightly. [example](https://prnt.sc/2Mz3h5vsJD39)
- 100% of players will see and it effects UX slightly.
- 100% of players will see and it effects UX significantly.