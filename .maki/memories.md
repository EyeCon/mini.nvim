# Memories

## Project state
- Fork of echasnovski/mini.nvim; `main@upstream` = upstream (echasnovski), local `main` carries fork commits (Jujutsu support for mini.statusline: feat `qlvksuqq`, docs `qknuyrpp`; CI cleanup `yupzwkpo`).
- Jujutsu statusline feature: `MiniStatusline.section_jujutsu()` + `H.update_jujutsu_change_id()` shells out to `jj log` on BufReadPost/BufWritePost/FileReadPost/DirChanged. Must run `jj` in the buffer file's dir (fixed `nmlolosu`), not `vim.fn.getcwd()` — mismatched cwd silently hides the change ID. `H` in mini modules is file-local: test via public API (`section_jujutsu`), not `st.H`.
- Help content for the feature now lives in the Lua docstrings; `kvntxqlq` synced + regenerated `doc/mini-statusline.txt` (section order follows source: jujutsu before git).

## Conventions (upstream mini.nvim)
- Doc comments: inline code/plugins in backticks (`` `lewis6991/gitsigns.nvim` ``), help refs as `|'statusline'|`, `|mini.git|`. Lua string literals use single quotes.
- `doc/*.txt` is generated from Lua comments via mini.doc: `nvim --headless --noplugin -u ./scripts/minimal_init.lua -c "lua require('mini.doc').generate()"`. Generator output has no trailing newline; hand-edits to `.txt` are lost on regen — always put doc content in Lua comments first. `scripts/lintdoc.lua` validates docs.

## Gotchas
- `qlvksuqq` accidentally rewrote pre-existing doc-comment quotes (backticks -> single quotes, dropped `|tag|` refs, mangled plugin name). Restored in `qtlqtsvq`; unrelated refactor churn (nvim-0.10 compat shims, `-- stylua: ignore start/end` at statusline.lua:594) still present in the feat commit.
