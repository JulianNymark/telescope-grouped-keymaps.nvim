# usage

:warning: this plugin isn't ready yet, it seems I don't understand how lazy works yet :flushed:
Therefore the lazy install snippet below isn't fully working.
I don't think I need to specify dependencies here, but it seems to not wait for
these dependencies to actually "finish" loading before it runs, so to truly get to
run this you can manually run the setup() after neovim has launched...(this is shown below)

```lua
{
	"JulianNymark/telescope_grouped_keymaps.nvim",
	dependencies = {
		"nvim-telescope/telescope.nvim",
		"folke/which-key.nvim",
	},
	opts = {},
	config = function()
		local module = require("telescope_grouped_keymaps")
		module.setup({})

		vim.keymap.set("n", "<leader>sK", function()
			module.picker_grouped_keymaps({})
		end, { desc = "list grouped keymaps" })

		print("loaded telescope_grouped_keymaps")
	end,
},

```

:warning: running this works, the above doesn't yet :cry:

```
:lua require("telescope_grouped_keymaps").setup({})
```
