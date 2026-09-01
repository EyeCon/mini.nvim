# Memories

## Project state
- Fork of echasnovski/mini.nvim; `main@upstream` = upstream (echasnovski), local `main` carries fork commits (Jujutsu support for mini.statusline: feat `qlvksuqq`, docs `qknuyrpp`; CI cleanup `yupzwkpo`).
- Jujutsu statusline feature: `MiniStatusline.section_jujutsu()` + `H.update_jujutsu_change_id()` shells out to `jj log` on BufReadPost/BufWritePost/FileReadPost/DirChanged.

## Conventions (upstream mini.nvim)
- Doc comments: inline code/plugins in backticks (`` `lewis6991/gitsigns.nvim` ``), help refs as `|'statusline'|`, `|mini.git|`. Lua string literals use single quotes.
- `doc/*.txt` is generated from Lua comments via mini.doc (`scripts/`); keep both in sync or regenerate.

## Gotchas
- `qlvksuqq` accidentally rewrote pre-existing doc-comment quotes (backticks -> single quotes, dropped `|tag|` refs, mangled plugin name). Restored in `qtlqtsvq`; unrelated refactor churn (nvim-0.10 compat shims, `-- stylua: ignore start/end` at statusline.lua:594) still present in the feat commit.
