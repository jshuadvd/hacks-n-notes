# Oh-my-zshell config file

## File name

`.zshrc`

## File content

```sh
plugins=(git vi-mode)

source $ZSH/oh-my-zsh.sh

# Preferred editor for local and remote sessions
 if [[ -n $SSH_CONNECTION ]]; then
   export EDITOR='vim'
 else
   export EDITOR='vim'
 fi
 
# aliases
alias npmr="npm run"


# ctrl-r starts searching history backward
bindkey '^r' history-incremental-search-backward
bindkey '^P' up-history
bindkey '^N' down-history

export NVM_DIR="$HOME/.nvm"
  . "$(brew --prefix nvm)/nvm.sh"
  
# open terminal in code directory
cd /Users/jorge/Code

export PATH="$PATH:$HOME/.yarn/bin"

# to be able to run local npm packages as global
# eg. `gulp`  instead of `./node_modules/.bin/gulp`
export PATH="$PATH:$HOME/.yarn/bin"
```

Then append [npm completion](https://docs.npmjs.com/cli/completion) to have autocomplete.

```
npm completion >> ~/.zshrc
```



