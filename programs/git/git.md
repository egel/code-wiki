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
    - Submodule:
      - [Update all submodules to the newest versions](#update-all-submodules-to-the-newest-versions)
    - Others:
      - [Sign `^M`](#sign-m)


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

### Submodule

#### Update all submodules to the newest versions
The simplest way is to run below command into repository:

    $ git pull --recurse-submodules

### Other

#### Sign ^M
This problem occures when someone not converting their line-ending character correctly.
I assume it's the Windows folk as they love their CRLF. Unix loves LF and Mac loved CR until it was shown the Unix way.

To fix it install `dos2unix` program then:

    $ dos2unix <filename>

After this operation all `^M` signs should disappear.


## Contribute
Feel free to contribute this project. Any commit or push request are welcome :)

  - Issues, typos, enhancements please report [here][repo_issues]


 [repo_issues]: https://github.com/revolunet/sublimetext-markdown-preview/issues
