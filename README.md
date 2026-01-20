# cmp-luasnip-choice

[luasnip](https://github.com/L3MON4D3/LuaSnip) choice node completion source for [blink-cmp](https://github.com/saghen/blink.cmp)



## Installation

```lua
require("lazy").setup({
	{
		"becknik/blink-cmp-luasnip-choice",
		dependencies = {
			{ "Saghen/blink.cmp" },
		},
		opts = {
			-- Optional config can go here
		}
	},
})
```

## Usage

```lua
require 'blink.cmp' .setup {
	-- …
	sources = {
		providers = {
			choice = {
				name = 'LuaSnip Choice Nodes',
				module = 'blink-cmp-luasnip-choice'
				opts = {},
			},
		}
	},
	-- …
	default = {
		'choice',
		'lsp',
		-- …
	}
}

```

## Further Recommendations

To quick toggling on smaller nodes, I'd recommend setting:

```lua
vim.keymap.set({"i", "s"}, "<C-n>", function()
	if ls.choice_active() then
		ls.change_choice(1)
	end
end, { silent = true, desc = "LuaSnip Next Choice" })

vim.keymap.set({"i", "s"}, "<C-p>", function()
	if ls.choice_active() then
		ls.change_choice(-1)
	end
end, { silent = true, desc = "LuaSnip Prev Choice" })
```
