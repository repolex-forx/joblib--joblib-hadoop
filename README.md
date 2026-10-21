# Repolex Knowledge Graph of joblib/joblib-hadoop

RDF knowledge graph data for [joblib/joblib-hadoop](https://github.com/joblib/joblib-hadoop), parsed by [repolex](https://repolex.ai).

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
rlex download joblib/joblib-hadoop
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 5ab445b66f3fe95eb023417f4951253a65898bb0
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 5ab445b66f3fe95eb023417f4951253a65898bb0
│           └── chunk-001.nq.gz
├── blob
│   ├── 060c1a4d17fab2c0420ec6d777dfa67f7b2ba4f8.nq.gz
│   ├── 15e1a48220339620af13c5fe23097c25048b83b2.nq.gz
│   ├── 166f0167baee6cf48abc8aa212b6f6d00ef4abbc.nq.gz
│   ├── 2175e0936e3e675ff17be55b3d86ebaa95a64c99.nq.gz
│   ├── 244a1452643f77f18e62903db5b77b61632f6644.nq.gz
│   ├── 266f47de214ff84cc503b24bc0e460b0c1b03d25.nq.gz
│   ├── 286e0e0d81f9a7058f47df37cd86be8f8f68e0e1.nq.gz
│   ├── 2bdd33676e7f0ad98d3146b5169096393a98a773.nq.gz
│   ├── 335c7f4e23d782208563834ff4af0fd5f79eea51.nq.gz
│   ├── 576483053a149a8e53f5dd717c1697fd637d4cbc.nq.gz
│   ├── 5b012b5f1732fd1cbf66c1bd67bc7a5778c3a6a5.nq.gz
│   ├── 60becd85b40eac09fbaaedd9f9d80f85ac9c8122.nq.gz
│   ├── 6a7fb010efc7465944c0483ee56156e5d0d047ec.nq.gz
│   ├── 72daa994b7f31c4a50165bfd1ea0d35e7350313d.nq.gz
│   ├── 73ea5852ce681b2d3eb2f30c58672d0fdba01c7f.nq.gz
│   ├── 7e40264da5f4e22d5adab608698a7797574ff740.nq.gz
│   ├── 924597caa12e760793e298201674a3371c7088ce.nq.gz
│   ├── 95b6d06780005a2bc951e3a8978ac281a23f3cf2.nq.gz
│   ├── 9a86f4301d68eb4a58d7707dcb09901fe663546b.nq.gz
│   ├── 9d2ccc9d1d66c708a7b5bd922f7994d5f8a5c7ac.nq.gz
│   ├── a54c4e5cc7437395cb6f1f99591a56a24d7c2933.nq.gz
│   ├── b2aba225976d610a49289c5c6134c01082759587.nq.gz
│   ├── b43ba74f6c96e07cf259cdee3421f60eff2c9747.nq.gz
│   ├── be0604b8d3fcc0934abadf548ed85c07a1fc6f12.nq.gz
│   ├── cbf66b434e9aa57cb108659e2e502b5e3cc75a83.nq.gz
│   ├── d1041a8142df8199194ec70e8e630956171a8ba6.nq.gz
│   ├── d5d88cb46fd2b19f4922be46d2ff8d8b6591b44e.nq.gz
│   ├── dba12aff149e09a6964d4f6d1af56b9511b7df90.nq.gz
│   ├── e6583f4c3f9c39eb0c0b709e83c31b3026eddea2.nq.gz
│   ├── e78978a9da57a82378880e7864b3b5a556b318c6.nq.gz
│   ├── f8cb646f6c877145bbdd56864a664a01c977471f.nq.gz
│   ├── fd360592d83ac7a189df0a52d186c90bdb0269ca.nq.gz
│   └── fe7dc12020ef396361344c754189fda6f4bb99d8.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 5ab445b66f3fe95eb023417f4951253a65898bb0.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 41 files
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

[joblib/joblib-hadoop](https://github.com/joblib/joblib-hadoop)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
