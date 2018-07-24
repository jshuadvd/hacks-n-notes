# Oh-my-zshell config file

## ~/.zshrc

[Theme powerlevel9k](https://github.com/bhilburn/powerlevel9k)

```sh
plugins=(
  git
  npm
  vi-mode
)

source $ZSH/oh-my-zsh.sh

# aliases
alias npmr="npm run"
alias zs="source ~/.zshrc"

# include Z
. /usr/local/etc/profile.d/z.sh

# ctrl-r starts searching history backward
bindkey '^r' history-incremental-search-backward
bindkey '^P' up-history
bindkey '^N' down-history

export NVM_DIR="$HOME/.nvm"
  . "$(brew --prefix nvm)/nvm.sh"

# open terminal in code directory
cd /Users/jorge/Code

# Power Level theme - Settings
ZSH_THEME="powerlevel9k/powerlevel9k"
POWERLEVEL9K_MODE='nerdfont-complete'
POWERLEVEL9K_LEFT_PROMPT_ELEMENTS=(os_icon dir rbenv vcs)
POWERLEVEL9K_RIGHT_PROMPT_ELEMENTS=(vi_mode status root_indicator background_jobs history time)

# Or for hyper-star-wars using Hyper https://github.com/klauscfhq/hyper-star-wars/blob/master/readme.md
```

### Themes

#### Power Level Theme

```bash
# Power Level theme - Settings
ZSH_THEME="powerlevel9k/powerlevel9k"
POWERLEVEL9K_MODE='nerdfont-complete'
POWERLEVEL9K_LEFT_PROMPT_ELEMENTS=(os_icon dir rbenv vcs)
POWERLEVEL9K_RIGHT_PROMPT_ELEMENTS=(vi_mode status root_indicator background_jobs history time)

# Or for hyper-star-wars using Hyper https://github.com/klauscfhq/hyper-star-wars/blob/master/readme.md
```



#### hyper star wars \(using Hyper\)

> [hyper-star-wars](https://github.com/klauscfhq/hyper-star-wars/blob/master/readme.md)

```
# ~/.zshrc

ZSH_THEME=""

# initialize pure prompt https://github.com/sindresorhus/pure
autoload -U promptinit; promptinit
prompt pure
```

## npm autocomplete

Then append [npm completion](https://docs.npmjs.com/cli/completion) to have autocomplete.

```
npm completion >> ~/.zshrc
```



