# telescope_grouped_keymaps

The missing newbie plugin "bridge"?

[Which-key](https://github.com/folke/which-key.nvim) lets you group keybinds.

[Telescope.builtin.keymaps](https://github.com/nvim-telescope/telescope.nvim/blob/b4da76be54691e854d3e0e02c36b0245f945c2c7/lua/telescope/builtin/init.lua#L386) is great for searching up keybinds.

But `Telescope.builtin.keybinds` doesn't know about your groupings via `Which-key`!

This plugin tries to bridge that gap with a custom telescope picker (copied & modified from the original keymaps picker). Now you can get the "full description" of your groups description + keys description.

![screenshot](./README/screenshot.png)

## Getting started

### Installation

Using [Lazy.nvim](https://github.com/folke/lazy.nvim)

```lua
{
	"JulianNymark/telescope_grouped_keymaps.nvim",
	dependencies = {
		"nvim-telescope/telescope.nvim",
		"folke/which-key.nvim",
	},
	opts = {},
	config = function(_, opts)
		local module = require("telescope_grouped_keymaps")
		module.setup({})

		vim.keymap.set("n", "<leader>sK", function()
			module.picker_grouped_keymaps({})
		end, { desc = "list grouped keymaps" })
	end,
},
```
