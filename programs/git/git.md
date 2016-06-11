<img src="img/git_logo.png" title="Git - free and open source distributed version control system" />

# Git

## Legend

  - origin = main remote server that where you push your commits


## Table of contents

  * Problems:
    - Branch:
      - [Clone all branches](#clone-all-branches)
      - [Branch miss track with origin/master](#branch-miss-track-with-originmaster)
      - [Remove branch (local and remote)](#remove-branch-local-and-remote)
    - Tags:
      - [Add tag](#add-tag)
      - [Remove tag](#remove-tag)
      - [Push tag](#push-tag)
    - Rebase:
      - [Change order of commits](#change-order-of-commits)
    - Commit:
      - [Change author of last commit](#change-author-of-last-commit)
      - [Show changes for single file](#show-changes-for-single-file)
    - Stash:
      - [List stash](#list-stash)
      - [Move current changes to stash](#move-current-changes-to-stash)
      - [Show particular stash](#show-particular-stash)
      - [Apply into code the most recent stash and remove it from list](#apply-into-code-the-most-recent-stash-and-remove-it-from-list)
      - [Clear whole stash stack](#clear-whole-stash-stack)
      - [Clear particular stash](#clear-particular-stash)
    - Remote:
      - [Add origin repository (first time)](#add-origin-repository)
      - [Change origin repository](#change-origin-repository)
    - Submodule:
      - [Update all submodules to the newest versions](#update-all-submodules-to-the-newest-versions)
    - SSH keys:
      - [How to generate SSH key?](#how-to-generate-ssh-key)
    - Others:
      - [Sign `^M`](#sign-m)


<!-- ====================================================================== -->
### Git branch

#### Clone all branches
How do I clone all remote branches with Git?

Check branches:

    $ git branch -a
    * master
      remotes/origin/HEAD
      remotes/origin/master
      remotes/origin/v1.0-stable
      remotes/origin/experimental

and next...

    $ git checkout origin/experimental


finishing create local branch

    $ git checkout -b experimental origin/experimental


#### Branch miss track with origin/master
We notice that we don't see how many commits we're ahead/behin with origin (remote repository)

Below command set acctual branch we're currently into and set it to track `origin/master`

    $ git branch --set-upstream-to=origin/master


#### Remove branch (local and remote)
In local repository:

    $ git branch -d

For origin (remote) - push the "delete" changes to origin:

    $ git push --delete origin <branchName>



<!-- ====================================================================== -->
* * *
### Git tags

#### Add tag
Add new tag to accual branch, and for specific revision:

    $ git tag -a v1.4 -m 'my version 1.4'

or

    $ git tag -a v1.2 -m 'version 1.2' 9fceb02


#### Remove tag
Remove tag from local repository:

    $ git tag -d 12345

Remove tag for origin (remote) repository:

    $ git push --delete origin 12345


#### Push tags
Push all tags from local repo to origin:

    $ git push --tags

Push all tags from one (or more) specyfic branch to origin:

    $ git push --tags production

Push specyfic tag to remote repo

    $ git push origin <tag_name>


<!-- ====================================================================== -->
* * *
### Rebase

#### Change order of commits
The simplest way is to run below command into repository:

    $ git rebase -i HEAD~4

then simply switch order of below result

    pick 9d2de86 remove test settings for super tab; add gui settings for Win/Unix/Mac
    pick c07dc4c add realtime updates to GitGutter plugin

    # Rebase c58999c..c07dc4c onto c58999c
    #
    # Commands:
    #  p, pick = use commit
    #  r, reword = use commit, but edit the commit message
    #  e, edit = use commit, but stop for amending
    #  s, squash = use commit, but meld into previous commit
    #  f, fixup = like "squash", but discard this commit's log message
    #  x, exec = run command (the rest of the line) using shell
    #
    # These lines can be re-ordered; they are executed from top to bottom.
    #
    # If you remove a line here THAT COMMIT WILL BE LOST.
    #
    # However, if you remove everything, the rebase will be aborted.
    #
    # Note that empty commits are commented out


and change it to:

    pick c07dc4c add realtime updates to GitGutter plugin
    pick 9d2de86 remove test settings for super tab; add gui settings for Win/Unix/Mac

    # Rebase c58999c..c07dc4c onto c58999c
    #
    # Commands:
    #  p, pick = use commit
    #  r, reword = use commit, but edit the commit message
    #  e, edit = use commit, but stop for amending
    #  s, squash = use commit, but meld into previous commit
    #  f, fixup = like "squash", but discard this commit's log message
    #  x, exec = run command (the rest of the line) using shell
    #
    # These lines can be re-ordered; they are executed from top to bottom.
    #
    # If you remove a line here THAT COMMIT WILL BE LOST.
    #
    # However, if you remove everything, the rebase will be aborted.
    #
    # Note that empty commits are commented out

Then the order of those commit will changed.



<!-- ====================================================================== -->
* * *
### Commit

#### Change author of last commit

    $ git commit --amend --author="John Doe <john.doe@example.com>"


#### Show changes for single file
To show list of commits where searched file is changed run:

    $ git lg -- filename

To show list of changes into files (diff) run:

    $ git lg -p filename


<!-- ====================================================================== -->
* * *
### Stash
- `<stash id>` = `stash@{0}` or `stash@{1}`

#### List stash
```bash
$ git stash list
```

#### Move current changes to stash
```bash
$ git stash
```

#### Show particular stash
```bash
$ git stash show -p stash@{1}
```

#### Apply into code the most recent stash and remove it from list
```bash
$ git stash pop
```

#### Clear whole stash stack
Cleat all elements from stash stack.
```
$ git stash clear
```

#### Clear particular stash
```bash
$ git stash drop stash@{0}
```

<!-- ====================================================================== -->
* * *
### Remote

#### Add origin repository

    git remote add origin <repository>

#### Change origin repository

    git remote set-url origin <repository>



<!-- ====================================================================== -->
### Submodule

#### Update all submodules to the newest versions
The simplest way is to run below command into repository:

    $ git submodules foreach git pull



<!-- ====================================================================== -->
* * *
### SSH keys

#### How to generate SSH key?

First generate par of keys (private and public) by run below command:

    $ ssh-keygen -t rsa -C "your_email@example.com"

then copy your `~/.ssh/*.pub` key to any place to confirm your identity.



<!-- ====================================================================== -->
* * *
### Other

#### Sign ^M
This problem occures when someone not converting their line-ending character correctly.
I assume it's the Windows folk as they love their CRLF. Unix loves LF and Mac loved CR until it was shown the Unix way.

To fix it install `dos2unix` program then:

    $ dos2unix <filename>

After this operation all `^M` signs should disappear.
