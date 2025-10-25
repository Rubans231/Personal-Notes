
2025-10-25 19:28

Status:

Tags: [[linux]]




# jupyter_notebooks in nvim using molten and imagemagick

- THIS WAS A FUCKING PAIN IN THE ASS, but i learned alot(For example, i learned how to not kms even if i'm stressed over hours tryna make a single thing work). Great experience. 10/10 on forced existential crisis
- Tbh, i was only stuck because of an obvious ignorance. I hadn't downloaded "jupyter" package to run jupyter notebooks because nobody in the world wants to mention as a prerequisite since it is so obvious

## Here's how it works

- For convinience it is first good to just have a venv wrapper. venv wrapper makes it easy to create venvs. Here's the one i used which i copy pasted into my ~/.zshrc file
	- [venv wrapper](https://gist.github.com/benlubas/5b5e38ae27d9bb8b5c756d8371e238e6)
- then activate a venv and run pip install pip install pynvim jupyter jupyter_client ipykernel cairosvg pnglatex plotly kaleido pyperclip
- Then install image.nvim with `sudo pacman -S imagemagick` and then paste this into .config/nvim/lua/plugins 
	- `return {`
    `{`
        `"benlubas/molten-nvim",`
        `version = "^1.0.0", -- use version <2.0.0 to avoid breaking changes`
        `dependencies = { "3rd/image.nvim" },`
        `build = ":UpdateRemotePlugins",`
        `init = function()`
            `-- these are examples, not defaults. Please see the readme`
            `vim.g.molten_image_provider = "image.nvim"`
            `vim.g.molten_output_win_max_height = 20`
        `end,`
    `},`
    `{`
        `-- see the image.nvim readme for more information about configuring this plugin`
        `"3rd/image.nvim",`
        `opts = {`
            `backend = "kitty", -- whatever backend you would like to use`
            `max_width = 100,`
            `max_height = 12,`
            `max_height_window_percentage = math.huge,`
            `max_width_window_percentage = math.huge,`
            `window_overlap_clear_enabled = true, -- toggles images when windows are overlapped`
            `window_overlap_clear_ft_ignore = { "cmp_menu", "cmp_docs", "" },`
        `},`
    `}`
`},`

- add this to end of neovim options.lua

```lua
vim.g.python3_host_prog=vim.fn.expand("~/.virtualenvs/neovim/bin/python3")
```
	
	
	Paste this into the nvim/config/options
	-` max_width = 100, -- tweak to preference
	  `max_height = 12, -- ^`
	 ` max_height_window_percentage = math.huge, -- this is necessary for a good experience`
	  `max_width_window_percentage = math.huge,`
	  `window_overlap_clear_enabled = true,`
	 ` window_overlap_clear_ft_ignore = { "cmp_menu", "cmp_docs", "" }
	- optionally set this into tmux config (- `set -gq allow-passthrough on`  `set -g visual-activity off`)


- Then add these to keymaps
- ```lua
  vim.keymap.set("n", "<localleader>e", ":MoltenEvaluateOperator<CR>", { desc = "evaluate operator", silent = true })
vim.keymap.set("n", "<localleader>os", ":noautocmd MoltenEnterOutput<CR>", { desc = "open output window", silent = true })
vim.keymap.set("n", "<localleader>rr", ":MoltenReevaluateCell<CR>", { desc = "re-eval cell", silent = true })
vim.keymap.set("v", "<localleader>r", ":<C-u>MoltenEvaluateVisual<CR>gv", { desc = "execute visual selection", silent = true })
vim.keymap.set("n", "<localleader>oh", ":MoltenHideOutput<CR>", { desc = "close output window", silent = true })
vim.keymap.set("n", "<localleader>md", ":MoltenDelete<CR>", { desc = "delete Molten cell", silent = true })

-- if you work with html outputs:
vim.keymap.set("n", "<localleader>mx", ":MoltenOpenInBrowser<CR>", { desc = "open output in browser", silent = true })
  ```
	

- dont know what these do but it works without this and it's supposed to go into options.lua
- ```lua
  -- I find auto open annoying, keep in mind setting this option will require setting
-- a keybind for `:noautocmd MoltenEnterOutput` to open the output again
vim.g.molten_auto_open_output = false

-- this guide will be using image.nvim
-- Don't forget to setup and install the plugin if you want to view image outputs
vim.g.molten_image_provider = "image.nvim"

-- optional, I like wrapping. works for virt text and the output window
vim.g.molten_wrap_output = true

-- Output as virtual text. Allows outputs to always be shown, works with images, but can
-- be buggy with longer images
vim.g.molten_virt_text_output = true

-- this will make it so the output shows up below the \`\`\` cell delimiter
vim.g.molten_virt_lines_off_by_1 = true
  ```









# References
https://github.com/benlubas/molten-nvim/blob/main/docs/Notebook-Setup.md
