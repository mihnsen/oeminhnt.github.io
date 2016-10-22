---
layout: post
title: Commit Guide
---

# Commit Guide - Version 0.0.1

General rules for commit

### Structured split of code changes
There should be only one 'logical change' per commit.  
DO NOT:
  * **_Mixing whitespace changes (or any change not related to code) with functional code changes._**  
    _Solution_: Create 2 commit, one with whitespace changes, another with functional code changes.(Order is not important but i prefer whitespace commit first)
  * **_Mixing 2 unrelated functional changes._**  
    Harder to search or identify. Risk of bug creation.  
    _Solution_: Create 2 commit of course.
  * **_Sending large feature in a single giant commit._**  
    The basic rule to follow is:
    > If a code change can be split into a sequence of patches/commits, then it should be split.

### Recommended commit flow
_It isn't *hard-rules* but should be followed._
  1. Reviewing your changes.  
    Use whatever you want. :)  
    **_Preferred_**: [git diff][git diff link], [git difftool][git difftool link]
  2. 'Whitespace-commit' first.  
    Check for all unrelated changes like space, indentation, debug code (console.log, var_dump, ...), code comments,... then commit first.  
    **_One of the best_**: [git add -p/git add --patch][git add link]
  3. Commit the rest follow above.  
    Keep it in mind `one logical change per commit`  
    **_Again, your best friend is_**: [git add -p/git add --patch][git add link]


### Commit messages
This is underestimated (or even dismissed) by many developers. If you're working as a part of a team, a group or a community it's better to learn writing commit messages responsibly as soon as possible.

_Instruction below is NOT *hard-rules* but recommended. It can be changed a little bit based on requirement of each project._

#### SYNTAX - _base on Karma convention_:
```
<Commit-type>: <Commit-subject>
<blank line>
<Commit-body>
<blank line>
<Commit-footer>
```
##### _Type_

> \<Commit-type\> - Mandatory. It should be one of type below:
>   * Feature: create/modify/delete feature
>   * Fix: fix bugs - with fix type reference should be include
>   * Docs: create/modify/delete documentation
>   * Test: create/modify/delete test
>   * Refactor: refactoring code
>   * Format: any changes NOT related to code changes (whitespace, semicolon,...)
>   * Build: modify build task (gulp, circleCI,...)
>   * Init: special type, just use for initial commit

##### _Subject_

> \<Commit-subject\> - Mandatory. It should follow some basic rules:
>   * Capitalize the subject line
>   * DO NOT end the subject line with a period/full-stop (.)
>   * Limit to 72 characters (include commit-type)  
>     If you work with github projects, the limit should be 69  
>     _The best_: 50
>   * Use imperative, present tense  
>     Use `Add abc`, `Change xyz`,...  
>     Do not use `Adds abc`, `Added abc`,...

##### _Body_

> \<Commit-body\> - Optional but *HIGHLY RECOMMENDED*.
>   * Use body to explain `what`, `why` and `how`
>   * Each paragraph begin with blank line
>   * Wrap body at 72 characters.

##### _Footer_

> \<Commit-footer\> - Optinal.
>   * Referencing issues  
>     Bug/Open issues/Close issues reference
>   * Breaking change  
>     Google for more information.


[git diff link]: https://git-scm.com/docs/git-diff
[git difftool link]: https://git-scm.com/docs/git-difftool
[git add link]: https://git-scm.com/docs/git-add
