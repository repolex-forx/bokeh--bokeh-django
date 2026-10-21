# Repolex Knowledge Graph of bokeh/bokeh-django

RDF knowledge graph data for [bokeh/bokeh-django](https://github.com/bokeh/bokeh-django), parsed by [repolex](https://repolex.ai).

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
rlex download bokeh/bokeh-django
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ce5cfca5a32b494a962d6bd0285ef751da5034fb
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ce5cfca5a32b494a962d6bd0285ef751da5034fb
│           └── chunk-001.nq.gz
├── blob
│   ├── 0575a580faaa0523a0aa4b16e98425a128849fc0.nq.gz
│   ├── 1d1affdea8c151f93ec7bab0c69d5475838ad8f8.nq.gz
│   ├── 20b66e882c1168f551e0cefefcebd43b79bf7ed8.nq.gz
│   ├── 3eae80e489cfda92173305e9da8979b0b7122140.nq.gz
│   ├── 766ef3d2b268627f2aee61baeb52729a4911eeca.nq.gz
│   ├── 7f6492fdc2690f28664587a2adf19401bf059026.nq.gz
│   ├── 8818be6db92acfd7e06ea9341c05b2f89d6f52cf.nq.gz
│   ├── 8fa7eb66e427d9779ef9f7cd32f231ac2816715b.nq.gz
│   ├── 9160afdfa3b8d0a4baaf8dec8d406297b08304f1.nq.gz
│   ├── a08f947ab32ba9145a3cef653d77fbe5dc014c4a.nq.gz
│   ├── ab160c31e4d3aa14f616e611b03a19719075d656.nq.gz
│   ├── abf247cf2182da80110e4138d68e8774e2384734.nq.gz
│   ├── adf385dbd60d98d66e6281cc8c0fc19f3c3122d8.nq.gz
│   ├── ae46b5315c99ced06d3028f29be599818b6ca2c8.nq.gz
│   ├── b6e47617de110dea7ca47e087ff1347cc2646eda.nq.gz
│   ├── c41c1b870169015c44650f231869dd62a324db27.nq.gz
│   ├── d35ba52048cdff1cc7a41996632192ea32603051.nq.gz
│   ├── e2b7ef427c001b7cd40eff8b4580406ce7e78d12.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e946bbf73ca7db98a79d7797486a1c7add425f7b.nq.gz
│   └── fab0e1c228f943a802ddd1adfaab6c3919f96e1c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ce5cfca5a32b494a962d6bd0285ef751da5034fb.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 29 files
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

[bokeh/bokeh-django](https://github.com/bokeh/bokeh-django)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
