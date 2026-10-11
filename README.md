# Repolex Knowledge Graph of tiangolo/docker-with-compose

RDF knowledge graph data for [tiangolo/docker-with-compose](https://github.com/tiangolo/docker-with-compose), parsed by [repolex](https://repolex.ai).

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
rlex download tiangolo/docker-with-compose
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── f15906670bc3b50446201b3391218a830156269e
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── f15906670bc3b50446201b3391218a830156269e
│           └── chunk-001.nq.gz
├── blob
│   ├── 06d073f8e1a794a0af242f1070a1317a5b6cac13.nq.gz
│   ├── 0ffc101a3f23548392499fe5104f3f8cf4d4e91b.nq.gz
│   ├── 2f47937b279e14417ae3bf4d776e3e7fb63c8c0c.nq.gz
│   ├── 361d57758fce853f678b6b83d2df929123241df6.nq.gz
│   ├── 3e43ed669735049bcdb4628877880c46f4122112.nq.gz
│   ├── 5b3973300bbd906da44fc0ef689fdbce75585d56.nq.gz
│   ├── 62a78532ea09646e07b14b71f26125c9b9667922.nq.gz
│   ├── 69fce64d4a909fb00a5bf4dc6c9162f5291bdb27.nq.gz
│   ├── 722d5e71d93ca0aa0db6fd22452e46be5604a84d.nq.gz
│   ├── 9963173e52eabf0a6bbd9b434ffdd53355912a06.nq.gz
│   ├── b82b279ddc57fbf6f2f5b5e8abc0d48851a80549.nq.gz
│   ├── c002dbfab3c7b19e9808d41ce800d26723d4b455.nq.gz
│   ├── d76f475d88678b0116b09609e4083ea8c3778f5b.nq.gz
│   └── d872c8932f4902843bfc775a2dca7617fc12d086.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── f15906670bc3b50446201b3391218a830156269e.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 22 files
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

[tiangolo/docker-with-compose](https://github.com/tiangolo/docker-with-compose)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
