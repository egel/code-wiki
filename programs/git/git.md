<img src="img/git_logo.png" title="Git - free and open source distributed version control system" width="100" />

# Git

  - origin = main remote server that where you push your commits

## Table of contents

  * Problems:
    - Branch:
      - Branch miss track with origin/master
      - Remove branch (local and remote)
    - Tags:
      - Add tag
      - Remove tag (local and remote)
    - Others:
      - Sign `^M`


### Git branch

#### <a name="">Branch miss track with origin/master</a>
We notice that we don't see how many commits we're ahead/behin with origin (remote repository)

Below command set acctual branch we're currently into and set it to track `origin/master`

    git branch --set-upstream-to=origin/master


#### <a name="">Remove branch (local and remote)</a>
In local repository:

    git branch -d

For origin (remote) - push the "delete" changes to origin:

    git push --delete origin <branchName>


### Git tags

#### <a name="">Add tag</a>
Add new tag to accual branch, and for specific revision:

    $ git tag -a v1.4 -m 'my version 1.4'

or

    $ git tag -a v1.2 -m 'version 1.2' 9fceb02


#### <a name="">Remove tag</a>
Remove tag from local repository:

    git tag -d 12345

Remove tag for origin (remote) repository:

    git push --delete origin 12345


#### <a name="">Push tags</a>
Push all tags from local repo to origin:

    git push --tags

Push all tags from one (or more) specyfic branch to origin:

    git push --tags production

Push specyfic tag to remote repo

    git push origin <tag_name>


#### <a name="">Clone tags</a>
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


#### <a name="">Git - delete tag</a>

    git tag -d 12345
    git push origin :refs/tags/12345

or

    git push origin --tags --force


#### <a name="">git config --global push.default</a>
**Warning**: `push.default` is unset; its implicit value has changed in
Git 2.0 from 'matching' to 'simple'. To squelch this message
and maintain the traditional behavior, use:

    git config --global push.default matching


To squelch this message and adopt the new behavior now, use:

    git config --global push.default simple


When push.default is set to 'matching', git will push local branches
to the remote branches that already exist with the same name.

Since Git 2.0, Git defaults to the more conservative 'simple'
behavior, which only pushes the current branch to the corresponding
remote branch that 'git pull' uses to update the current branch.

See 'git help config' and search for 'push.default' for further information.
(the 'simple' mode was introduced in Git 1.7.11. Use the similar mode
'current' instead of 'simple' if you sometimes use older versions of Git)

### Other

#### <a name="sign-m">Sign ^M</a>
This problem occures when someone not converting their line-ending character correctly.
I assume it's the Windows folk as they love their CRLF. Unix loves LF and Mac loved CR until it was shown the Unix way.

To fix it install `dos2unix` program then:

    $ dos2unix <filename>

After this operation all `^M` signs should disappear.


## Contribute
Feel free to contribute this project. Any commit or push request are welcome :)

  - Issues, typos, enhancements please report [here][repo_issues]


 [repo_issues]: https://github.com/revolunet/sublimetext-markdown-preview/issues
