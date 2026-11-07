# Repolex Knowledge Graph of sphinx-contrib/py_directive

RDF knowledge graph data for [sphinx-contrib/py_directive](https://github.com/sphinx-contrib/py_directive), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download sphinx-contrib/py_directive
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 14b44920c0fdffd2ec5284ba3690c787c2968f84
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 14b44920c0fdffd2ec5284ba3690c787c2968f84
│           └── chunk-001.nq.gz
├── blob
│   ├── 0a746f9fd1dbb1f44dc66d014ead02043108ec2b.nq.gz
│   ├── 0d4bb6e4bf8c65d247320bb0d3994ebb7c698c49.nq.gz
│   ├── 2d74c58f248790e34e482eb07e20ec6c753c9d2d.nq.gz
│   ├── 43d1972bbbbb754eb4f211b3b329ae204c8e3dc0.nq.gz
│   ├── 45dd5f5b51e10661a6b6699e050c4ab23d721804.nq.gz
│   ├── 6c6a13959777fe6425b2c51996c4970140d21e44.nq.gz
│   ├── 6fa3d7b1a7c3390469529d23cf0a5769b718215e.nq.gz
│   ├── 8e7e2bc0d26ebc39199523caf9850ff62f3d650a.nq.gz
│   ├── ab39fe969fd459a472936ada4e2d892deb31682e.nq.gz
│   └── b5a7dc29ef0f7f3593b1c61cfc5dfe8a17d3918c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 14b44920c0fdffd2ec5284ba3690c787c2968f84.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 16 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[sphinx-contrib/py_directive](https://github.com/sphinx-contrib/py_directive)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
