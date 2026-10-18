# Repolex Knowledge Graph of kennethreitz/envoy

RDF knowledge graph data for [kennethreitz/envoy](https://github.com/kennethreitz/envoy), parsed by [repolex](https://repolex.ai).

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
rlex download kennethreitz/envoy
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ab463a14da47bd8334cdf5e64f6b9dd2ba9dd28a
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ab463a14da47bd8334cdf5e64f6b9dd2ba9dd28a
│           └── chunk-001.nq.gz
├── blob
│   ├── 0d20b6487c61e7d1bde93acf4a14b7a89083a16d.nq.gz
│   ├── 18e148de86c99e0ead13d144fb9c60bd15fd5b5e.nq.gz
│   ├── 520107e228f32b5555e88328df04141d6054e9fd.nq.gz
│   ├── 52203914924110f2a11737f05841e9cfe3045e4d.nq.gz
│   ├── 5a81f2547a25696730ddc94ad0a302c7934a705b.nq.gz
│   ├── 5df74074c95635b77a94dc5666e804c5dd515c9e.nq.gz
│   ├── 5e4090017a9bec5de60a745d17007a9e95f31a43.nq.gz
│   ├── a8753d19a4a185b52e4e3ed106f7495f2e5a4ea3.nq.gz
│   ├── a9b4c2b93c3f2e7f4cd0741d97b1e4ca8febe784.nq.gz
│   ├── c5c3007558040cb8a8fbafb80baa73e96813fe79.nq.gz
│   ├── ca4c937412d08b61b74d2315315ee6ce474d6587.nq.gz
│   └── e1be9d9c22e09fc729b3c370f584970e2af2e42d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ab463a14da47bd8334cdf5e64f6b9dd2ba9dd28a.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 20 files
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

[kennethreitz/envoy](https://github.com/kennethreitz/envoy)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
