# Fundamentals

## Table of contents
- [Fundamentals](#fundamentals)
  - [Table of contents](#table-of-contents)
  - [Importance of reading the material](#importance-of-reading-the-material)
  - [Naming Conventions](#naming-conventions)
    - [Branch Naming](#branch-naming)
    - [PR Naming](#pr-naming)
    - [File And Folder Naming](#file-and-folder-naming)
    - [Class And Function Naming](#class-and-function-naming)
    - [Variable Naming](#variable-naming)
  - [Dividing The Code Into Commits](#dividing-the-code-into-commits)
    - [Commit Too Big](#commit-too-big)
      - [Bad Example:](#bad-example)
    - [Commit Dependencies in the Correct Order](#commit-dependencies-in-the-correct-order)
    - [Refactoring: Duplicate Commit](#refactoring-duplicate-commit)
  - [Imitate Existing Solutions](#imitate-existing-solutions)
  - [Simplify Complex Expressions](#simplify-complex-expressions)
  - [Delete Unused Material](#delete-unused-material)
  - [Don't Hoard Issues](#dont-hoard-issues)
  - [Don't Use Magic Numbers](#dont-use-magic-numbers)
  - [Avoid Code Repetition](#avoid-code-repetition)
  - [Avoid Tight Coupling](#avoid-tight-coupling)
  - [Iterate Before Opening a PR](#iterate-before-opening-a-pr)
  - [Resolving Conversations](#resolving-conversations)
  - [When to Merge PR](#when-to-merge-pr)

## Importance of reading the material

-  Most people who skim through the reading materials fail to become long term contributors. The key to passing is reading the developer docs during each PR for the first 2 weeks, until you've internalized them. And read them again each month to realign.

## Naming Conventions

### Branch Naming

- `your_short_name/feature-description`
- Ex: `goktug/main-ejs-env-system`
- Follow https://mirrors.edge.kernel.org/pub/software/scm/git/docs/git-check-ref-format.html, and don't use any special characters like `'`.

### PR Naming

- `your_short_name/<PR Name>`
- Ex: `muhammad/Disable Spectator Trade Options`

### File And Folder Naming

The correct file naming convention depends on the file type

- `.ejs` and `.scss` files use snake_case naming (e.g. `style.scss`, `content_disable_ad_block.ejs`)
- `.ts` files use PascalCase naming (e.g. `Api.ts`, `UIProfileFriendsController.ts`)

Folders use snake_case naming

### Class And Function Naming 

- Functions use camelCase naming. 
- Make sure each function has a specific purpose. If you can't name a function easily, it is doing too many things
- Make sure function names capture the purpose of the function

Since functions perform an action, it's often useful to start a function name with a verb. Some common verbs used are `add`, `set`, `update`, `create` and `remove`)

```typescript
function addToList(list: number[], item: number) {
  list.push(item)
}

function createList(item1, item2) {
  return [item1, item2]
}
```

Classes use PascalCase naming, all properties and functions within the class should use camelCase.

```typescript
import {PascalCaseClass} from './code/snake_case_folder/PascalCaseFile.ts'

class PascalCaseClass {

        camelCaseVariable: string

        camelCaseFunction(): void {
        
        } 
}
```

Each class is kept in its own file, which must have the same name as the class (e.g. `class MyClass` saved to `MyClass.ts`)

Don't save multiple classes in the same file. If you need to create many classes for a feature, they should all be saved in their own folder.

```
.
└── my_feature/
    ├── MyFeatureClass1.ts
    └── MyFeatureClass2.ts
```

### Variable Naming

- Prefer specific names instead of typical loop variable names like x, i, j, k
- Shift names from CS naming to meaning (e.g: statusFlag to isValidDatabaseEntry)
- Make sure class names defined for HTML should always use kebab case. For example `singleton-page-container` is the correct class convetion while `singleton_page_container` is not. If you find such cases, please create PRs with the fix
- The generic/parent word should come first
  Example: `MenuItemText` instead of `MenuTextItem`, menu has item, item has text

The way to name the variable:
1. Explain what the variable does to someone
2. Use that explanation as the name
   
Examples:
- https://curc.readthedocs.io/en/latest/programming/coding-best-practices.html
- https://www.loom.com/share/75692b3f08ce4d1da51e067268618d86

## Dividing The Code Into Commits

### Commit Too Big

Break down your commits into the smallest commit that represents a `single` change in a build-able state. Ideally only 1 operation should happen in a commit.

Creating big commits result in

- Extending review time
- Possibility of missing a problem during review
- Lower code quality
- Reviewer being [overwhelmed](https://www.tiktok.com/@kg.codes/video/6899212872841202949) and not merging your PR, asking you to do it again

#### Bad Example: 

- https://gyazo.com/3e4635022a00a125a71cbc24ba3bf226

This commit can be broken down into:

- Renaming the function
- Moving function elsewhere
- Changing where it was called from
- Cleaning it up
- Writing a patch-note

Never do such commits: 
- https://prnt.sc/2011v5r 
- https://gyazo.com/b9e30de2869e6ea5decc11f94767f1d1 

### Commit Dependencies in the Correct Order

Always create and commit code elements in dependency order - dependent elements first. This keeps your code functional and simplifies code reviews.

Example: https://prnt.sc/vQZcWSvCkIcS

### Refactoring: Duplicate Commit

When you want to move a certain code from one place to another never separate the commit into `add commit` and `remove commit`. They should be in a single commit which is a `move commit`

When the developer does an `add commit` in hopes of deleting the original code in the future, what they are actually doing is a `duplicate commit`. This makes the reviewers job harder by making them need to jump back and forth increasing the likely hood of them missing a potential flaw. This results in a bad code quality overtime resulting in bad product.

Bad Example: 
- https://www.loom.com/share/e7c1ae338eb743fdbe1065da210d53cd

## Imitate Existing Solutions

There is a high chance that a problem similar to the one you're currently trying to solve exists in the codebase. Try to find components that might have had similar problems, understand its logic, and adapt the existing solution into your specific problem.

Example: https://prnt.sc/oCdql_NaawK0

## Simplify Complex Expressions

When creating complex expressions or calculations, it is recommended to divide the calculations or assignments into simpler lines. This enhances readability and makes it easier to understand and maintain the code.

Example: 

- Before:
```ts
const response = await axios.get<DiscordPurchases[]>(`${DISCORD_API_URL}/${KatanServerConfigs.discordAuthClientId()}/entitlements?user_id=${userId}`, {headers: headers})
```
- After: 
```ts
const goodVarName = `${DISCORD_API_URL}/${KatanServerConfigs.discordAuthClientId()}/entitlements?user_id=${userId}`
const response = await axios.get<DiscordPurchases[]> (goodVarName, {headers: headers})
```

## Delete Unused Material

After refactoring, some code or resources may become unused. It's important to check if this is the case, and if so, delete unused material to keep the code clean, organized, and easy for others to work with.

Example: https://www.loom.com/share/f99d5206b7394e96b132026863fe409a

## Don't Hoard Issues

* Assign one issue at a time. Once you open a PR and wait for review you can assign a new issue
* There is a possibility the issue you assigned can take 3-5x the time you envisioned. If you have assigned multiple issues, it means you're keeping the other ones from being completed.

## Don't Use Magic Numbers

Read: https://stackoverflow.com/questions/47882/what-is-a-magic-number-and-why-is-it-bad

## Avoid Code Repetition

* To prevent duplicating code, implement functions, loops, or modular components whenever possible. This approach simplifies our codebase and makes it more maintainable, efficient, and easier to understand for others.

Bad example: https://www.loom.com/share/6d4df641659940ab8f3ab33c2fb50eed

## Avoid Tight Coupling

* Tight coupling occurs when changing a part of the code requires changes to the design of another part.
* It causes the code to break in once place due to changes made in another place.
* Avoid creating tight coupling, which may break in the future when someone modifies another part without realizing its consequences.
* Ensure that your code is loosely coupled, and it remains independent from changes in different modules.

Concept explanation: https://stackoverflow.com/a/37993102  
Related part of suggested reading material: https://github.com/trantuyen1998/clean-code-javascript#solid

## Iterate Before Opening a PR

* Before submitting your first implementation as a PR, take the time to iterate and refine it. Aim for 2 or 3 iterations to achieve a better solution with each attempt.
* By iterating and refining your implementation, you increase the chances of your PR being approved faster and with fewer requested changes.

## Resolving Conversations

In your PRs, you'll get a bunch of reviews. There are a few actions you should take
1. If you agree, 
  - Leave a thumbs up
  - Add the conversation link to your commit message
  - Resolve conversation
  - Do not comment saying you did it, the reviewer gets extra notification https://i.imgur.com/Q4IRFsO.png 
2. If you disagree,
  - Explain why you disagree and what you propose
3. If you're unsure,
  - Ask follow up questions

## When to Merge PR

- Merge -> Get approval from 1 QA and 1 Dev
- Not Merge -> Get approval from 2 QAs
- Not Merge -> Get approval from 2 devs
- Not Merge -> Get approval from 1 designer, 1 dev
