# Repolex Knowledge Graph of sphinx-contrib/apidoc

RDF knowledge graph data for [sphinx-contrib/apidoc](https://github.com/sphinx-contrib/apidoc), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/apidoc
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d47f8b3120da82ed0827f5d5f68ccabba537a629
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── d47f8b3120da82ed0827f5d5f68ccabba537a629
│           └── chunk-001.nq.gz
├── blob
│   ├── 0162e94046beb77e043578daf494cc8cb6dd13c7.nq.gz
│   ├── 035ac796596a4b0c505fc0448a7b2fad429218c4.nq.gz
│   ├── 0c64bb814a218d583465a89480d48f0dccb71127.nq.gz
│   ├── 151ec1c1ea147b6feea593550d6cd957422a8959.nq.gz
│   ├── 1ae0c934e238ab7cd16ca91c54ffc93530ec7f9d.nq.gz
│   ├── 20b103112b5229d5dddf8b78ea7622fd74b560aa.nq.gz
│   ├── 376025b3e65838c0416b747eb76e71ee58fbe145.nq.gz
│   ├── 383d0b1fcc419821e43004a35179df5e101bf747.nq.gz
│   ├── 5aa85e12994d75d9a71d3d8d64921b9bda54b5c6.nq.gz
│   ├── 5d753fec4fcfbce708dd97992a994c065adbccb3.nq.gz
│   ├── 662bf8dd0cd0058e35cacefe459f9f1eea4164f2.nq.gz
│   ├── 8b4ea91dbd3668e8b76c4e9fc24393f318a132d4.nq.gz
│   ├── 8ba8eae3c81cf38c8fa4b1414fe96ec21cb9c93a.nq.gz
│   ├── 905d387a72e5bb496d98e47948c363e4fc832fe9.nq.gz
│   ├── 97cf074be9b67e09e977ab2e0dcbda9eed415159.nq.gz
│   ├── ac7d049af032e3844752d27d07bb59fa97ab4907.nq.gz
│   ├── b0203ff3cdc37ced6b7f58cf856baa92f259ca1d.nq.gz
│   ├── b5f27a5495c8508f1dd7e6aaab1b31d280a0036b.nq.gz
│   ├── b84588eab0fe7af739b733a4b71d4a3df8d1fe5d.nq.gz
│   ├── bc2e84acb11d9f7d511702f9040a67c13ac36439.nq.gz
│   ├── bc6df17a0d95ea0153cc71c79e7c3209faa3509e.nq.gz
│   ├── c33bd200b539d5aa43bfc92b0db5a8cb427470d9.nq.gz
│   ├── cb294d8ee20f9895586da930c08e63d4d7e80c56.nq.gz
│   ├── d2c7ba585785d51d20aa9f96dcab2f9031bb87d3.nq.gz
│   ├── d9f81d46d5951871f1ffb4ab79fc66c38be58bab.nq.gz
│   ├── e079f8a6038dd2dc8512967540f96ee0de172067.nq.gz
│   ├── e3cd5248260b8131b44b7628e3619b432aba327f.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e88a11c4a81e3b35eb5116829ac1ff9986f3788f.nq.gz
│   ├── e9e8ae4f3b587bf5aa88092cb214096123a2bcb4.nq.gz
│   ├── f063f5d2b957c36515287fa9994c3d499430cfb5.nq.gz
│   ├── f6ebd538bb628db5e354438bfa0e24a10e8b695b.nq.gz
│   └── fe28f4b545c2a4159f6cdb5543a6f162aa8316f8.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── d47f8b3120da82ed0827f5d5f68ccabba537a629.nq.gz
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

[sphinx-contrib/apidoc](https://github.com/sphinx-contrib/apidoc)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
