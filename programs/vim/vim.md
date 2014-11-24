<img src="img/Vim_logo.png" title="Vim - The ultimate text editor" width="150" />

# Vim
Vim is just a text editor. There is a version fro LUI and GUI. You can also install almost any operating system more popular.

Many people after the first "clash" with the programi usually asks:

> But why is it like that great? It's ugly, unpleasant and even ... @#$%^&!

Its power hides with versatility of usage and outstanding modularity.


## Table of Contents
  * [Useful shotcuts](#useful_shortcuts)
  * [Quick introduction](#quick_introduction)
  * [Installation and configuration](#installation_and_configuration)


## <a name="#installation_and_configuration">Installation and configuration</a>
For Debian/Ubuntu/Mint:

    $ sudo apt-get install vim


**Configuration:**

It should make friends with the file `~ / .vimrc`, and this is why the file that stores all the basic settings that are automatically let off every time you run vim.

Clone sample confirutation to your PC.

    $ cd ~/ && git clone --recursive git@github.com:egel/dot-files.git &&
      ln -s /home/$USER/dot-files/.vimrc &&
      ln -s /home/$USER/dot-files/.vim

More information can be found at: [https://github.com/egel/dot-files](https://github.com/egel/dot-files)

## <a name="#quick_introduction">Quick introduction</a>

    :! php %

  * execute `:`
  * command `!`
  * name of the command `php`
  * my name of the file `%`


## <a name="#useful_shortcuts">Useful shortcuts</a>

#### Undo & Redo

  * `undo` - click `u` (command mode)
  * `redo` - click <kbd>Ctrl</kbd>+<kbd>r</kbd> (command mode)


#### Copy and Paste

  - Wciskamy w trybie polecenia <kbd>v</kbd> lub <kbd>Ctrl</kbd>+<kbd>v</kbd>
  - zaznaczamy linijki które nas interesuja
  - potem klikamy <kbd>p</kbd> aby wkleić tekst


#### Save file as root
After open and make some changes into the file you can't save this changes, because you don't have permission to save it. You can simply:

    :w !sudo tee %


#### Autocomplete text

<kbd>Ctrl</kbd>+<kbd>n</kbd> (insert mode)

