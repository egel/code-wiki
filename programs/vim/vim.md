<img src="img/Vim_logo.png" title="Vim - The ultimate text editor" width="150" />

# Vim
Vim is just a text editor. There is a version for LUI (Linear User Interface) and GUI (Graphical User Interface). You can also install this program at any popular operating system.

Many people after the first "clash" with the program usually asks:

> Why it is such a great tool? It's ugly, unpleasant and even ... @#$%^&!

..., its power hides with his versatility of usage and outstanding modularity :)


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


## <a name="#installation-and-configuration">Installation and configuration</a>
For Debian/Ubuntu/Mint:

    $ sudo apt-get install vim


**Configuration:**

You should make friends with the file `~ / .vimrc`, and this is why the file that stores all the basic settings that are automatically let off every time you run vim.

Clone sample confirutation to your PC.

    $ cd ~/ && git clone --recursive git@github.com:egel/dot-files.git &&
      ln -s /home/$USER/dot-files/.vimrc &&
      ln -s /home/$USER/dot-files/.vim

More information can be found at: [https://github.com/egel/dot-files](https://github.com/egel/dot-files)

**Reload .vimrc in Vim without restart**
Into command mode:

    :source ~/.vimrc


## <a name="#quick-installation">Quick introduction</a>

    :! php %

  * execute `:`
  * command `!`
  * name of the command `php`
  * my name of the file `%`


## <a name="#useful-shortcuts">Useful shortcuts</a>
Below you can find many useful shortcuts that will drive your work with vim into the ligthspeed.

#### <a name="#undo-and-redo">Undo & Redo</a>

  * `undo` - click <kbd>u</kbd> (command mode)
  * `redo` - click <kbd>Ctrl</kbd>+<kbd>r</kbd> (command mode)


#### <a name="#copy-and-paste">Copy & Paste</a>

  - into command insert press <kbd>v</kbd> or <kbd>Ctrl</kbd>+<kbd>v</kbd>
  - select lines that you want to copy, then press <kbd>y</kbd>
  - finally paste copied fragment before cursor (<kbd>P</kbd>) or after cursor <kbd>p</kbd>

If you you want to using system clipboard on your Linux distro consider to look at my [vim dot-files](egel-dot-files-repo)


#### <a name="#save-file-as-root">Save file as root</a>
After open and make some changes into the file you can't save this changes, because you don't have permission to save it. You can simply:

    :w !sudo tee %


#### <a name="#search-and-replace">Search and replace</a>
To see more combination see [http://vim.wikia.com/wiki/Search_and_replace](http://vim.wikia.com/wiki/Search_and_replace)

`:%s/foo/bar/g` - Find each occurrence of 'foo' (in all lines), and replace it with 'bar'.

`:%s/foo/bar/gc` - Change each 'foo' to 'bar', but ask for confirmation first.


#### <a name="#split-window">Split window</a>

<kbd>Ctrl</kbd>+<kbd>W</kbd>, <kbd>S</kbd> for horizontal splitting

<kbd>Ctrl</kbd>+<kbd>W</kbd>, <kbd>V</kbd> for vertical splitting

<kbd>Ctrl</kbd>+<kbd>W</kbd>, <kbd>Q</kbd> to close one

<kbd>Ctrl</kbd>+<kbd>W</kbd>, <kbd>Ctrl</kbd>+<kbd>W</kbd> to switch between windows or also

<kbd>Ctrl</kbd>+<kbd>W</kbd>, <kbd>arrow keys</kbd>

<kbd>Ctrl</kbd>+<kbd>W</kbd>, <kbd>J</kbd> (xor <kbd>K</kbd>, <kbd>H</kbd>, <kbd>L</kbd>) to switch to adjacent window (intuitively up, down, left, right)


#### <a name="#autocomplete-text">Autocomplete text</a>

<kbd>Ctrl</kbd>+<kbd>n</kbd> next hint (insert mode)

<kbd>Ctrl</kbd>+<kbd>p</kbd> previous hint (insert mode)


#### <a name="#find-current-word">Find current word</a>
Simple as click <kbd>#</kbd> on the search term (in command mode)


#### <a name="#tab-multiple-lines">Tab multiple lines</a>

1. Select multiple lines for example with:

    <kbd>Shift</kbd>+<kbd>v</kbd>

2. then when text is marked (visual mode) press:

    <kbd>></kbd> to increase indent

    <kbd><</kbd> to decrease indent


<!-- General links -->
 [egel-dot-files-repo]: https://github.com/egel/dot-files
