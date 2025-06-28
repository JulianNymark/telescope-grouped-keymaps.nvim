# usage

## Lazy

```lua
{
	"JulianNymark/telescope_grouped_keymaps.nvim",
	dependencies = {
		"nvim-telescope/telescope.nvim",
		"folke/which-key.nvim",
	},
  event = "VeryLazy",
	opts = {},
	config = function()
		local module = require("telescope_grouped_keymaps")
		module.setup()

		vim.keymap.set("n", "<leader>sK", function()
			module.picker_grouped_keymaps({})
		end, { desc = "list grouped keymaps" })

		print("loaded telescope_grouped_keymaps")
	end,
},

```
