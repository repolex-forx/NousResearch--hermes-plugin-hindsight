# Repolex Knowledge Graph of NousResearch/hermes-plugin-hindsight

RDF knowledge graph data for [NousResearch/hermes-plugin-hindsight](https://github.com/NousResearch/hermes-plugin-hindsight), parsed by [repolex](https://repolex.ai).

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
rlex download NousResearch/hermes-plugin-hindsight
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 7385025e90e98b0a4f8042f40ec956b71cb18287
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 7385025e90e98b0a4f8042f40ec956b71cb18287.nq.gz
│   └── repolex
│       └── 7385025e90e98b0a4f8042f40ec956b71cb18287
│           └── chunk-001.nq.gz
├── blob
│   ├── 00f2d38d8063d0c6b219c0081e51888063b0c55e.nq.gz
│   ├── 27bf2de2e9bb02762e8498d424474c79c193edf0.nq.gz
│   ├── 302801f075928e8499ddf5a3c5351b8a4728b719.nq.gz
│   ├── 4a2f1dbf2422b3a50187d5f10011bf64f7abbb46.nq.gz
│   ├── 6655b2a5d39fccd919a153b5aabfef9ba427a281.nq.gz
│   ├── 75410e73319c72cd3e991a501c5455eb78f38375.nq.gz
│   ├── 9dfa763af7f494cfe9171c9d64fadbba0525ae29.nq.gz
│   ├── bf71258714b7d0020167d4dffa4b51399f1b721f.nq.gz
│   ├── c4d17a6a6f29aa97174dfb671b91d68107bf1c17.nq.gz
│   ├── d29826c3f55573e483f2f64c2a18dbc21cd26b1d.nq.gz
│   ├── da7d337bfea13476e91e29892f78869885ea55d4.nq.gz
│   └── e6fdbac351533f217325ffc9c09e8144c0a963d0.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 7385025e90e98b0a4f8042f40ec956b71cb18287.nq.gz
├── filetree
│   └── 7385025e90e98b0a4f8042f40ec956b71cb18287.nq.gz
├── issue
│   └── issue.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 21 files
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

[NousResearch/hermes-plugin-hindsight](https://github.com/NousResearch/hermes-plugin-hindsight)

---
*Parsed on 2026-09-30 by [repolex](https://repolex.ai)*
