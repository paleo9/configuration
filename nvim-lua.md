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

## Install Packer package manager

see  https://github.com/wbthomason/packer.nvim

1.  Install the code into your .local directory. The nvim/ subdirectories will be created automatically.

```
  git clone --depth 1 https://github.com/wbthomason/packer.nvim\
 ~/.local/share/nvim/site/pack/packer/start/packer.nvim
```

1. Create ~/.config/nvim/lua/plugins.lua

```
  return require('packer').startup(function()
    use 'wbthomason/packer.nvim'
  end)
```

1. Inside nvim, run the packer update or install script

```
  :PackerInstall
    or
  :PackerUpdate
```

## Install Language Server Protocol (LSP) Plugin

1. Install the nvim-lspconfig plugin.
1. Install a language server
1. Add lua require('lspconfig').xx.setup{...} to your init.vim where "xx" is the name of the relevant config.
1. Restart nvim.
1. Run PackerUpdate or PackerInstall
1. Check that an LSP client has attached to the current buffer.
1. Create a project, this project must contain a file matching the root directory trigger.

## Install the nvim-lspconfig plugin (using packer)

``` lua
  -- config/nvim/lua/plugins.lua:
  use 'neovim/nvim-lspconfig'
```

## Install a language server (pyright)

``` 
  npm install -g pyright
```

## add require statement to nvim.init

```
  require('lspconfig').pyright.setup{}
```

## restart nvim and update Packer

In nvim: 

:PackerUpdate


### Create a python file, add errors and try it out

``` python
  print hello
  print "hello"
  print("hello")

