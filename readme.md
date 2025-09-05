# Vim + LaTeX snippets setup

These snippets are based on Gilles Castel's blog,
*[How I'm able to take notes in mathematics lectures using LaTeX and Vim](https://castel.dev/post/lecture-notes-1/)*

## Vim configuration

Copy `tex.snippets` to `~/.vim/UltiSnips/` or do a partial clone.

```bash
cd ~/.vim/UltiSnips/
git clone --filter=blob:none --sparse \
  https://github.com/jfishe/latex-snippets.git tex
cd tex
git sparse-checkout set --no-cone /tex.snippets
git checkout
```

Assuming you're using
[Vim Plug](https://github.com/junegunn/vim-plug),
add the following to your `.vimrc`:

```vim
Plug 'sirver/ultisnips'
    let g:UltiSnipsExpandTrigger = '<tab>'
    let g:UltiSnipsJumpForwardTrigger = '<tab>'
    let g:UltiSnipsJumpBackwardTrigger = '<s-tab>'

Plug 'lervag/vimtex'
    let g:tex_flavor='latex'
    let g:vimtex_view_method='zathura'
    let g:vimtex_quickfix_mode=0

Plug 'KeitaNakamura/tex-conceal.vim'
    set conceallevel=1
    let g:tex_conceal='abdmg'
    hi Conceal ctermbg=none

setlocal spell
set spelllang=en_us
inoremap <C-l> <c-g>u<Esc>[s1z=`]a<c-g>u
```

Something not working as expected? Feel free to open an issue!
