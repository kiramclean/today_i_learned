+++
title = "How to set up Vim to work with Markdown"
date = 2017-07-28
tags = ["vim", "markdown"]
categories = ["programming", "tools"]
+++

## The Problem

Editing markdown in vim as-is can be.. not so great. The lines go forever and
there's no syntax highlighting.

## The Solution

If you're writing a ton of stuff in markdown just because markdown is great,
you might want to use a different program or editor that's made for editing
markdown.  If you're just running into a markdown file once in a while in the
course of development, though, you can add these lines to your `.vimrc` to make
working with markdown in vim a little more enjoyable.

```vim
" Recognize .md files as markdown
autocmd BufNewFile,BufReadPost *.md set filetype=markdown

" Wrap text for mardown by default at 80 chars and don't break words apart
autocmd FileType markdown setlocal wrap linebreak textwidth=80

" Highlight code blocks in markdown
let g:markdown_fenced_languages = ['elixir', 'html', 'javascript', 'ruby']

```

It's all pretty self-explanatory. Tweet at me if you have questions! This is
enough to make editing markdown in vim at least good enough that you don't feel
like you have to open a separate editor just to edit some markdown once in a
while.

### Bonus Tip

If you already have a buffer open when you load some new settings, instead of
reopening it after you reload your new config, you can select the lines you want
to re-format and then hit `gq` to make them follow your new style rules.

🙂

