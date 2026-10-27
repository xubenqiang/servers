---
"@modelcontextprotocol/server-filesystem": patch
---

`search_files` now reads `excludePatterns` the same way `directory_tree` does: a bare name such as `"node_modules"` also excludes an entry with that name at any depth and the whole subtree below it, instead of only matching it at the searched root. Previously `excludePatterns: ["node_modules"]` pruned a top-level `node_modules` but still descended into `packages/a/node_modules` and returned its files.
