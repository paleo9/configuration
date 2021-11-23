# creating nvim/init.lua

Seems like a good opportunity to convert to lua for the init file.

## Blogs

  * getting started using lua in neovim: https://github.com/nanotee/nvim-lua-guide
  * from init.vim to init.lua: https://teukka.tech/luanvim.html
  * https://icyphox.sh/blog/nvim-lua/
  * https://vonheikemen.github.io/devlog/tools/configuring-neovim-using-lua/


## Example lua dotfiles to pillage
  
  * codesmell's dot files: github.com/whatsthatsmell/dots

## YT videos

  * codesmell's lua key mapping: https://www.youtube.com/watch?v=IMXhsdBjveU

## Distraction-free coding

  * lua plugin replacement for goyo: github.com/folke/zen-mode.nvim

## Vim help on lua

  * vim.api.xxx

## Setting options in nvim.lua with examples

Use :help api

``` Lua
-- nvim_buf_set_option({buffer}, {name}, {value}) // buffer is the id of the buffer to affect, current buffer is 0
vim.api.nvim_buf_set_option(0, "tabstop", 2)

-- nvim_win_set_option({window}, {name}, {value}) // window is the id of the window to affect, current window is 0
vim.api.nvim_win_set_option(0, "number", true)

-- use jj for <esc> in insert mode
vim.api.nvim_set_keymap("i", "jj", "<esc>", {noremap = false, silent = true})
```
