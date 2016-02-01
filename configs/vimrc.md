# Vimrc

`.vimrc` Configuration file for vim editor in Unix.


```shell
set nocompatible              " be iMproved, required
filetype off                  " required

" set the runtime path to include Vundle and initialize
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()
" alternatively, pass a path where Vundle should install plugins
"call vundle#begin('~/some/path/here')

" let Vundle manage Vundle, required
Plugin 'VundleVim/Vundle.vim'

" Color theme
Plugin 'crusoexia/vim-monokai'

" plugin on GitHub repo
Plugin 'tpope/vim-fugitive'

" NeerdTree
Plugin 'scrooloose/nerdtree.git'

" Ctrl-P to search/open files
Plugin 'ctrlpvim/ctrlp.vim.git'
let g:ctrlp_map = '<c-p>' " Map :CtrlP
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
```
