# Repolex Knowledge Graph of klen/muffin-sentry

RDF knowledge graph data for [klen/muffin-sentry](https://github.com/klen/muffin-sentry), parsed by [repolex](https://repolex.ai).

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
rlex download klen/muffin-sentry
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── bc97360dfa4339e4b9af4bf769e6c84117e1bdda
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── bc97360dfa4339e4b9af4bf769e6c84117e1bdda
│           └── chunk-001.nq.gz
├── blob
│   ├── 043b0da50f2577ae8f65f0b65f433256bb291d41.nq.gz
│   ├── 0a6ee958310ca78a98bf4803c291d5898c7fd5b4.nq.gz
│   ├── 23c5c150f58bdd129447223d88288e859f8cccb1.nq.gz
│   ├── 4311acbfaaf94c2c6467b33f82d14b172dd717ab.nq.gz
│   ├── 4a060cc8ce501e4a5b9157c2f5ed52285582dd60.nq.gz
│   ├── 4d66be51d8b54dee04e75db0d223b733499fcc32.nq.gz
│   ├── 4d858ab27801eb8296409750464ec7ac8b585553.nq.gz
│   ├── 5f1d5686f3dc12105665875988bbe0b90d32c2bc.nq.gz
│   ├── 666ce2a519fd8f0c3599a11f968422b82612ca92.nq.gz
│   ├── 6cdd0ab2024bb33b2510e0a384c83d454521cd5b.nq.gz
│   ├── 78df056a6afd6b2f7c5a8695635380a19f30acd9.nq.gz
│   ├── 7a3f07ab83552f47a8705fa5d22729a324a2f71a.nq.gz
│   ├── 849dcfe5f163d043aa40a7b04eec69532db4c050.nq.gz
│   ├── 96958749c8e91cc9cf41eaea30732e151d25673d.nq.gz
│   ├── b1ec394bd935fd3d8cac8e97d2eab7a0c26337d7.nq.gz
│   ├── b67845bc2c6cd2427fb72d00d412e8cd9037989f.nq.gz
│   ├── c6fa885ca67b7c37071f978525de766ae0af3377.nq.gz
│   ├── c9db9563b5d0a187416a8ab6562a070f4aafae3d.nq.gz
│   ├── ce48f87110f5a00c4f3320f9ed0c8e630cb23daf.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e728d03676c20ba87a39556e60b642f5df17ebde.nq.gz
│   └── f8535500ce94832e3e988db81666c5c6b1580589.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── bc97360dfa4339e4b9af4bf769e6c84117e1bdda.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 29 files
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

[klen/muffin-sentry](https://github.com/klen/muffin-sentry)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
