# Coding
## General Rules

1. Never work on the master or staging branches
2. Always work on a custom branch dedicated to your feature
5. Try to play around the code and discover how it works by yourself as much as possible
7. If you just remembered a line of code that should've been added to the last commit, you should amend that line to last commit here: https://prnt.sc/v0t4ld

## Code Complete Tips

Program defensively: recognize that mistakes will be made and program in such a way that catches and handles those mistakes as quickly as possible
- Anticipate change
- Aim to reduce complexity so that the code chunk you are working on can be handled in memory easily 
- Limit for/if/completion nesting to three levels
- Use familiar widely accepted conventions
- Avoid global data
- Consider multiple designs before settling on one, don’t go with the first

Ways to manage complexity:
- Prioritize read time over write time
- Make sure each function has a specific purpose, if naming is hard, function is bad
- Think hard about public interfaces
- Think about parts that are likely to change and hide the details away through an interface
- Hierarchy (when possible, structure code in such a way that the more general code sections cover more specific parts. e.g: data stores class, which includes db connector objects to mysql, redshift, etc)
- Separate conceptually different parts into different code sections (like ui, db, etc.)
- Modularize more
- Try to shift names from cs internal implementations to semantic meaning (valid_db_entry > status flag)
- Make sure routine names holistically capture the purpose of the method
- When possible, prefer specific names instead of typical loop variable names (index > i)

## Other Resources
- [Clean Code](https://github.com/trantuyen1998/clean-code-javascript). A summarized version of the Clean Code book adapted to JavaScript.
- [Pull Requests and Commits](https://faun.pub/the-art-of-a-well-composed-pull-request-3815fc7e9610). Read this if you're having difficulty with commits or pull requests.