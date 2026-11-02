# Repolex Knowledge Graph of ActiveState/appdirs

RDF knowledge graph data for [ActiveState/appdirs](https://github.com/ActiveState/appdirs), parsed by [repolex](https://repolex.ai).

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
rlex download ActiveState/appdirs
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 8734277956c1df3b85385e6b308e954910533884
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 8734277956c1df3b85385e6b308e954910533884
│           └── chunk-001.nq.gz
├── blob
│   ├── 08abda83be0b6c397151096d85541c44d9b91fdb.nq.gz
│   ├── 2a9acf13daa95e85642ea255d3e3bd1ef8252804.nq.gz
│   ├── 52e59c0fca89e305093bcb10b83d0ba22eb74bee.nq.gz
│   ├── 6c3ac1b1dbb7d4d063c551440decd1178d09c012.nq.gz
│   ├── 8c89fb278cbf8774397b7a009426f784fa2ee949.nq.gz
│   ├── 9bef3459aef5eed453714a5ed140a9f84aff6533.nq.gz
│   ├── 9db7e4e23e96df44dca48c48f245d095cdaa1da8.nq.gz
│   ├── a9380b7a4534b0574b46e23bd4d364b9f879f819.nq.gz
│   ├── b78eeda4267eee2d83688f6c50f43da0acaac744.nq.gz
│   ├── e4d3ae044b44a23578e4c7e096378344ec35bc4b.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ed62d98536387fd1c7698b91ca115536b7638a15.nq.gz
│   ├── f98b053adb45f9d2dc8c602bbc3ae9bf46fb8162.nq.gz
│   └── f99fdbfdcb0ef39fcae170da02825a6c836dd01e.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 8734277956c1df3b85385e6b308e954910533884.nq.gz
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

[ActiveState/appdirs](https://github.com/ActiveState/appdirs)

---
*Parsed on 2026-11-02 by [repolex](https://repolex.ai)*
