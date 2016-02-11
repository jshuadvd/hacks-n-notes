# Vimrc

> `.vimrc` Configuration file for vim editor in Unix.

## Preview

![](vim-preview.png)

## Configuration

### Package manager

First install [Vundle](https://github.com/VundleVim/Vundle.Vim)

### Fonts & Symbols

- In OSX, install [powerline symbols](https://powerline.readthedocs.org/en/latest/installation/linux.html#font-installation) for Airline plugin 
- In iTerm, set non-ASCII font to Powerline.

### Setup `.vimrc` file

Usually found in `~/.vimrc`

> Replace your current `.vimrc` file content with the following blob.


```
set nocompatible              " be improved, required
filetype off                  " required

" Vundle is the package manager

set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()

" alternatively, pass a path where Vundle should install plugins
" call vundle#begin('~/some/path/here')

" let Vundle manage Vundle, required
Plugin 'VundleVim/Vundle.vim'

" Color theme
Plugin 'crusoexia/vim-monokai'

" NERDTREE
Plugin 'scrooloose/nerdtree.git'
" close vim if NERDTREE is the only window left
autocmd bufenter * if (winnr("$") == 1 && exists("b:NERDTree") && b:NERDTree.isTabTree()) | q | endif 


" Ctrl-P to search/open files
Plugin 'ctrlpvim/ctrlp.vim.git'
let g:ctrlp_map = '<leader>p' " Map :CtrlP
let g:ctrlp_cmd = 'CtrlP' " Map :CtrlP
let g:ctrlp_custom_ignore = {
  \ 'dir':  '\v[\/](\.git|node_modules|build)$',
  \ 'file': '\v\.(exe|so|dll)$',
  \ }

" Syntaxis checker
Plugin 'scrooloose/syntastic.git'
set statusline+=%#warningmsg#
set statusline+=%{SyntasticStatuslineFlag()}
set statusline+=%*
let g:syntastic_always_populate_loc_list = 1
let g:syntastic_auto_loc_list = 1
let g:syntastic_check_on_open = 1
let g:syntastic_check_on_wq = 0

" JS syntax highlighting
Plugin 'pangloss/vim-javascript'

" JSX highlighting. Depends on 'pangloss/vim-javascript'
Bundle 'mxw/vim-jsx'
let g:jsx_ext_required = 0 " to enable jsx in .js files
" Use eslint
let g:syntastic_javascript_checkers = ['eslint'] 

" Inserts pairs of quotes, brackets, braces
Plugin 'jiangmiao/auto-pairs.git'

" Cool status bar
Plugin 'vim-airline/vim-airline'
" use powerline symbols
let g:airline_powerline_fonts = 1

" EditorConfig
Plugin 'editorconfig/editorconfig-vim'

" All of your Plugins must be added before the following line
call vundle#end()            " required
filetype plugin indent on    " required

" Put your non-Plugin stuff after this line

set number
set tabstop=2
set shiftwidth=2
set expandtab
set autoindent
set smarttab
set colorcolumn=80,100,120
set ruler
let mapleader = "-"
nnoremap <leader>w <c-w>
nnoremap <leader>n :NERDTreeToggle<CR>
syntax on
set t_Co=256
colorscheme monokai
```

## Vundle

> Vundle is the plugin/package manager

To ignore plugin indent changes, instead use:
`filetype plugin on`

commands | description
-------- | -----------
`:PluginList` | lists configured plugins
`:PluginInstall` | installs plugins; append `!` to update or just `:PluginUpdate`
`:PluginSearch foo` | searches for foo; append `!` to refresh local cache
`:PluginClean` | confirms removal of unused plugins; append `!` to auto-approve removal

See `:h vundle` for more details or wiki for FAQ

## Plugins installed in this `.vimrc`


name | source | description
---- | ------ | -----------
Monokai | `crusoexia/vim-monokai` | Color theme like SublimeText
NerdTree | `scrooloose/nerdtree.git` | Navigator side-bar
Ctrl-P | `ctrlpvim/ctrlp.vim.git` | File opener
Syntastic | `scrooloose/syntastic.git` | Syntax highlighting
Vim Javascript | `pangloss/vim-javascript` | JS highlighting
Vim JSX | `mxw/vim-jsx` | JSX support
Auto Pairs | `jiangmiao/auto-pairs.git` | Automatically closes `{}`,`[]`, `""`, `''`, etc.
Airline | `vim-airline/vim-airline` | Cool status bar
Editor Config | `editorconfig/editorconfig-vim` | Enables text editor rules in `.editorconfig`


## Troubleshooting

1. When *copy-pasting* this config for the second time, the autopair plugin can insert `"` where there
shouldn't be.  That might comment out code that you need.
2. Also the long command for the **NERDTREE** might be split by the *copy-paste*. Make sure it is in one single line.
3. If tern server fails, make sure you run `npm i` in the bundle directory.