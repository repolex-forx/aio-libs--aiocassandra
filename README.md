# Repolex Knowledge Graph of aio-libs/aiocassandra

RDF knowledge graph data for [aio-libs/aiocassandra](https://github.com/aio-libs/aiocassandra), parsed by [repolex](https://repolex.ai).

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
rlex download aio-libs/aiocassandra
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 023dd429e1780251c585d698e1dbcfb4ec15c377
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 023dd429e1780251c585d698e1dbcfb4ec15c377
│           └── chunk-001.nq.gz
├── blob
│   ├── 1156e4a3f7b2e6ceff326927fab1a5a947e56513.nq.gz
│   ├── 28840c2e4450b0b314ac692018b69f2001e7385c.nq.gz
│   ├── 4a731e1fc5a113e696d669add896982480130c36.nq.gz
│   ├── 50a35601971ed7010d3c790fe8ab50d27f51c3dd.nq.gz
│   ├── 5c1e6e37704944c273504fa2b8ace88623de138d.nq.gz
│   ├── 6ea20650afd318e6f414b05025314b348b228afc.nq.gz
│   ├── 83ed093489ffa6993e3367dbf50076ae16ef3cf2.nq.gz
│   ├── 8feef6e01be208e975ee52c59367b8f65cecce75.nq.gz
│   ├── a860a098893a751c3fe924c601e6c3ae18a240e3.nq.gz
│   ├── b7775cca5a1ca55ccb9fefb8989b63bd148ba3ac.nq.gz
│   ├── bf53af9596fadfd9c49bb79376eb24213851f465.nq.gz
│   ├── de2bf33ff6335cd711ae1e5b990c105508c67667.nq.gz
│   ├── df6b1a750fa6f599b00045d694edb8a1d93bd101.nq.gz
│   ├── e24206f7951ce600070c653a55f024bdf4d78a08.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── ef8ff8756b24b900a3dfaa6ebf2bd4bb9e1a966f.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 023dd429e1780251c585d698e1dbcfb4ec15c377.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 24 files
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

[aio-libs/aiocassandra](https://github.com/aio-libs/aiocassandra)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
