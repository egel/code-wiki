<img src="img/Vim_logo.png" title="Vim - The ultimate text editor" width="150" />

# Vim
Vim is just a text editor (with SuperPowers!). There is a version for almost any Operating System that exsist with LUI (Linear User Interface) and GUI (Graphical User Interface).

* * *
[Egel Vim Cheat Sheet (PDF)](http://bit.ly/1wqcChS)
* * *

Many people after the first "clash" with the program usually asks:

> Why it is such a great tool? It's ugly, unpleasant and even ... @#$%^& ... aaaahhh!

Cool down a bit..., its powers hides with his versatility of usage and outstanding modularity :)


## Table of Contents
  * [Installation and configuration](#installation-and-configuration)
  * [Quick introduction](#quick-introduction)
  * [Useful shotcuts](#useful-shortcuts)
    - [Undo & Redo](#undo--redo)
    - [Copy & Paste](#copy--paste)
    - [Save file as root](#save-file-as-root)
    - [Search and replace](#search-and-replace)
    - [Split window](#split-window)
    - [Autocomplete text](#autocomplete-text)
    - [Find current word](#find-current-word)
    - [Tab multiple lines](#tab-multiple-lines)
    - [NERDTree reload new files](#nerdtree-reload-new-files)
  * [Useful subjects](#useful-subjects)
    - [Manage working directory](#manage-working-directory)


## Installation and configuration
For Linux Debian/Ubuntu/Mint:

    $ sudo apt-get install vim


**Configuration:**

If you wants to configure your vim like a boss, then you should make friends with the file `~/.vimrc`. This file stores all the basic settings that are automatically let off every time you run vim.

If you new to vim you should try some already configuration (like for example mine: [https://github.com/egel/dot-files/](https://github.com/egel/dot-files/)). Clone this sample confirutation to your PC and give it a try! ;)

    $ cd ~/ && git clone --recursive git@github.com:egel/dot-files.git && \
      ln -s /home/$USER/dot-files/.vimrc && \
      ln -s /home/$USER/dot-files/.vim

**Reload .vimrc in Vim without restart**
Into command mode:

    :source ~/.vimrc

More information about above configuration can be found at [https://github.com/egel/dot-files](https://github.com/egel/dot-files) where I store my **vim** settings - give it a try ;)


## Quick introduction

    :! php %

  * execute `:`
  * command `!`
  * name of the command `php`
  * my name of the file `%`


## Useful shortcuts
Below you can find many useful shortcuts that will drive your work with vim into the ligthspeed.

#### Undo & Redo

  * `undo` - click <kbd>u</kbd> (command mode)
  * `redo` - click <kbd>Ctrl</kbd>+<kbd>r</kbd> (command mode)


#### Copy & Paste

  - into command insert press <kbd>v</kbd> or <kbd>Ctrl</kbd>+<kbd>v</kbd>
  - select lines that you want to copy, then press <kbd>y</kbd>
  - finally paste copied fragment before cursor (<kbd>P</kbd>) or after cursor <kbd>p</kbd>

If you you want to using system clipboard on your Linux distro consider to look at my [vim dot-files](egel-dot-files-repo)


#### Save file as root
After open and make some changes into the file you can't save this changes, because you don't have permission to save it. You can simply:

    :w !sudo tee %


#### Search and replace
To see more combination see [http://vim.wikia.com/wiki/Search_and_replace](http://vim.wikia.com/wiki/Search_and_replace)

`:%s/foo/bar/g` - Find each occurrence of 'foo' (in all lines), and replace it with 'bar'.

`:%s/foo/bar/gc` - Change each 'foo' to 'bar', but ask for confirmation first.

`:%s/\<foo\>/bar/gc` - Change only whole words exactly matching 'foo' to 'bar'; ask for confirmation.

#### Split window

<kbd>Ctrl</kbd>+<kbd>W</kbd>, <kbd>S</kbd> for horizontal splitting

<kbd>Ctrl</kbd>+<kbd>W</kbd>, <kbd>V</kbd> for vertical splitting

<kbd>Ctrl</kbd>+<kbd>W</kbd>, <kbd>Q</kbd> to close one

<kbd>Ctrl</kbd>+<kbd>W</kbd>, <kbd>Ctrl</kbd>+<kbd>W</kbd> to switch between windows or also

<kbd>Ctrl</kbd>+<kbd>W</kbd>, <kbd>arrow keys</kbd>

<kbd>Ctrl</kbd>+<kbd>W</kbd>, <kbd>J</kbd> (xor <kbd>K</kbd>, <kbd>H</kbd>, <kbd>L</kbd>) to switch to adjacent window (intuitively up, down, left, right)


#### Autocomplete text

<kbd>Ctrl</kbd>+<kbd>n</kbd> next hint (insert mode)

<kbd>Ctrl</kbd>+<kbd>p</kbd> previous hint (insert mode)


#### Find current word
Simple as click <kbd>#</kbd> on the search term (in command mode)


#### Tab multiple lines

1. Select multiple lines for example with:

    <kbd>Shift</kbd>+<kbd>v</kbd>

2. then when text is marked (visual mode) press:

    <kbd>></kbd> to increase indent

    <kbd><</kbd> to decrease indent

#### NERDtree reload new files

You could simply hit `r` to refresh the current directory's listing or `R` to refresh the root directory's listing .

More generally, many plugins have a thorough documentation that you can access with `:help <pluginame>`.



### Useful subjects

#### Manage working directory
Working directory is a very useful thing, especially when you writing or renameing multiple file:

**Check current working directory**

    :pwd

To change to the directory of the currently open file (this sets the current directory for all windows in Vim):

    :cd %:p:h

You can also change the directory only for the current window (each window has a local current directory that can be different from Vim's global current directory):

    :lcd %:p:h

In these commands, % gives the name of the current file, %:p gives its full path, and %:p:h gives its directory (the "head" of the full path).



**Bibliography**

  - [Vim wiki](http://vim.wikia.com/wiki/Vim_Tips_Wiki)

<!-- General links -->
 [egel-dot-files-repo]: https://github.com/egel/dot-files
