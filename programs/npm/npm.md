# NPM

## Table of Contents

*   [Setup](#setup)
    *   [Install npm via nvm](#install-npm-via-nvm)
*   [List your all global npm packages](#list-your-all-global-npm-packages)

## Setup

### Install npm via nvm
Install reference page of orginal nvm repo [nvm install][github-nvm-install]

```bash
wget -qO- https://raw.githubusercontent.com/creationix/nvm/v0.32.0/install.sh | bash
nvm install 5 # install the latest v5
nvm alias default 5
nvm use 5
```

Might be handy to add below handy script to you shell script (add to one of: `.bashrc`, `.zshrc`, or any other) use programs installed globally via nvm.

```
# Node version manager config
#export NPM_CONFIG_PREFIX="/usr/local"
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && . "$NVM_DIR/nvm.sh"  # This loads nvm
[[ -r $NVM_DIR/bash_completion ]] && . $NVM_DIR/bash_completion

# add current node (+ node programs installed globally) to PATH
# NOTE: nvm have to be configured to works
CURRENT_NODE_VERSION=$(node --version)
if [[ $PATH != *"nvm"* ]]; then
  PATH=$PATH':'$HOME'/.nvm/versions/node/'$CURRENT_NODE_VERSION'/bin'
fi
```


***

### List your all global npm packages

```bash
npm list -g --depth=0
```

[github-nvm-install]: https://github.com/creationix/nvm#install-script
