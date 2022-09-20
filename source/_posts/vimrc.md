---
title: vimrc_ubuntu1305
date: 2018-08-04 14:52
---
这是 ubuntu1305 的 vim 配置信息。我比较习惯这种风格，特此保存。
<!-- more -->

---

set nu
syntax on
set guifont=DejaVu\ Sans\ Mono\ 12
set softtabstop=4
set shiftwidth=4
set expandtab
set guioptions-=T
set nobackup
set formatoptions=tcrqn
set cindent
set smartindent
set incsearch
set autoindent
set encoding=utf-8
set fileencodings=ucs-bom,utf-8,chinese


"Show matching bracets
set showmatch
"
""Get out of VI's compatible mode
set nocompatible

if has("cscope")
    set csprg=/usr/bin/cscope
    set csto=0
    set cst
    set nocsverb
    " add any database in current directory
         if filereadable("cscope.out")
             cs add cscope.out
    "             " else add database pointed to by
    "             environment
                     elseif $CSCOPE_DB != ""
    cs add $CSCOPE_DB
endif
set csverb
set cscopetag
set cscopequickfix=s-,g-,c-,d-,t-,e-,f-,i-
nmap <C-c><C-s> :cs find s <C-R>=expand("<cword>")<CR><CR>
nmap <C-c><C-g> :cs find g <C-R>=expand("<cword>")<CR><CR>
nmap <C-c><C-c> :cs find c <C-R>=expand("<cword>")<CR><CR>
nmap <C-c><C-t> :cs find t <C-R>=expand("<cword>")<CR><CR>
nmap <C-c><C-e> :cs find e <C-R>=expand("<cword>")<CR><CR>
nmap <C-c><C-f> :cs find f <C-R>=expand("<cfile>")<CR><CR>
nmap <C-c><C-i> :cs find i <C-R>=expand("<cfile>")<CR><CR>
nmap <C-c><C-d> :cs find d <C-R>=expand("<cword>")<CR><CR>
endif

"Have the mouse enabled all the time
"set mouse=a
"
""Set to auto read when a file is changed from the outside
set autoread

"Enable filetype plugin
filetype plugin indent on
colo desert
set hlsearch

"let Tlist_Ctags_Cmd = '/usr/bin/ctags-exuberant' 

nnoremap <silent> <F9> :TlistToggle<CR>
"let Tlist_Use_Right_Window=1
colorscheme delek 
"colorscheme evening
set ruler

