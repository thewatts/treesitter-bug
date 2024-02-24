## Treesitter Bug?

It looks like, if `highlight = { enable = true }` is set, that `gf` breaks.

### To reproduce:

1. Startup NVIM, using the provided bare-bones `init.lua`.

( Note: It *only* has lazy-vim, vim-rails, and nvim-treesitter )

2. cd into the included rails application, and open `app/views/posts/_post.html.erb`
3. Move your cursor to be over the word "another_partial"
4. In normal mode, hit `gf`

#### Expected:

The file, `app/views/posts/_another_partial.html.erb` will be opened.

#### Actual:

You get the error: `E345: Cannot find file "another_parial" in path`

---

If you change the config in `init.lua` to set `highlight` to `enable = false` - it works as expected.
