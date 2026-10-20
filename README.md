# Repolex Knowledge Graph of simonw/datasette-leaflet

RDF knowledge graph data for [simonw/datasette-leaflet](https://github.com/simonw/datasette-leaflet), parsed by [repolex](https://repolex.ai).

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
rlex download simonw/datasette-leaflet
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 339d9931326cf0dce22f6a950fd202fb1c4f04db
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 339d9931326cf0dce22f6a950fd202fb1c4f04db
│           └── chunk-001.nq.gz
├── blob
│   ├── 02cc307d3e066407aa1f20b7ead3c7fcc0d9da83.nq.gz
│   ├── 1a72e5784b2b456eac5d7670738db80697af3377.nq.gz
│   ├── 200c333dca9652ac4cba004d609e5af4eee168c1.nq.gz
│   ├── 32d406437894c820975e4285066af5033a8e3aa9.nq.gz
│   ├── 378f5254814182c18e50d4a93b8b039a58a8aa58.nq.gz
│   ├── 39aa46ecf5a3d97e64fe16ba4b28fcfdcc51c4d8.nq.gz
│   ├── 4be5490d444eecc74fe8ce300e42dbfb9403f6bb.nq.gz
│   ├── 4f020068383c6e672f97afe855f9a35b8b92efe2.nq.gz
│   ├── 88f9e501888c9c6cb29ad340d9a888627dd1b6d8.nq.gz
│   ├── 8a71f6ae27d31172a0d45567a64a53404e088d9a.nq.gz
│   ├── 950edf24677ded147df13b26f91baa2b0fa70513.nq.gz
│   ├── 9ade8dc49bc5ff4d2c8772f00d8d7933b520f710.nq.gz
│   ├── 9fd2979532a19a15b824ce763c76e04a8dafadfb.nq.gz
│   ├── b69a6cc7b4e1474d1c9f968d9239e636982fbf8f.nq.gz
│   ├── bbbd5ff05167fbb3d02c365e505f17d0305724b5.nq.gz
│   ├── ed7f5081cae3165027607100faff29178c243c30.nq.gz
│   └── ee372058cacafb78d4c16acecfa9158925b8b1ac.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 339d9931326cf0dce22f6a950fd202fb1c4f04db.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 25 files
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

[simonw/datasette-leaflet](https://github.com/simonw/datasette-leaflet)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
