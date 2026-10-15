# Repolex Knowledge Graph of Textualize/toolong

RDF knowledge graph data for [Textualize/toolong](https://github.com/Textualize/toolong), parsed by [repolex](https://repolex.ai).

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
rlex download Textualize/toolong
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 5aa22ee878026f46d4d265905c4e1df4d37842ae
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 5aa22ee878026f46d4d265905c4e1df4d37842ae
│           └── chunk-001.nq.gz
├── blob
│   ├── 0154e0d9e14350e99b85d2c7445c48c3f56ffc25.nq.gz
│   ├── 068959d80666da4e297034f3f44d2734ec613b27.nq.gz
│   ├── 1eb2fae57f36cb9144dff727491436916dbf08c1.nq.gz
│   ├── 21893630c7df23ef1bde0cbadd67bfab478abbff.nq.gz
│   ├── 2fb8773dea1a54c279f9c0ff58ed4f727a8f570f.nq.gz
│   ├── 300e20a7d1a67c9fc0f54cee99ba6d6e84f6d936.nq.gz
│   ├── 4ecb47c6e9eba6e4619bd7c2f63cc41b5eb53b60.nq.gz
│   ├── 50ff30a01b91d64f0303cebf75686f0ae3e8b9d2.nq.gz
│   ├── 59361d2311576ad500b6749c153c0cefc2f02477.nq.gz
│   ├── 5a195f3313e030e46daacab225718ca5c669cef7.nq.gz
│   ├── 680a14274352ce82add35c18309712849b291d0e.nq.gz
│   ├── 68bc17f9ff2104a9d7b6777058bb4c343ca72609.nq.gz
│   ├── 7354ddc2d1ced002b818da4106c3cd17d1181ffb.nq.gz
│   ├── 885ec5f355d052ab5f70062b3dcfcdcc1454d85f.nq.gz
│   ├── 9221e29bcbe4c5b1a1fe97189478cba8555fe6b2.nq.gz
│   ├── af20c66cc0fe538780eada1d1a3dc259b07be0bc.nq.gz
│   ├── bd35e89970e8df463706ca3faf4c33e67dd0a2a8.nq.gz
│   ├── c14c33efcd4c4fb6414449fb5a6f43ffa2ebfe53.nq.gz
│   ├── c1faff1474507f3fccc2816e722341010500c0e6.nq.gz
│   ├── cc2c4cd45715a80e59d585a7b9602e4f37069a1c.nq.gz
│   ├── d2a1dba39d887760b01042b912f545ab3b3beed5.nq.gz
│   ├── e08cd118c0e044e2c1600c347049bbb6dc1da336.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── e8ec30276989d39d35b75abf4dbf3a2cac4c94ca.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 5aa22ee878026f46d4d265905c4e1df4d37842ae.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 32 files
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

[Textualize/toolong](https://github.com/Textualize/toolong)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
