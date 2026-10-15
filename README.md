# Repolex Knowledge Graph of click-contrib/click-spinner

RDF knowledge graph data for [click-contrib/click-spinner](https://github.com/click-contrib/click-spinner), parsed by [repolex](https://repolex.ai).

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
rlex download click-contrib/click-spinner
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 31c253177d762a3456d673f6498713d91380e5f9
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 31c253177d762a3456d673f6498713d91380e5f9
│           └── chunk-001.nq.gz
├── blob
│   ├── 10310b45f0c295210572cdf4971575a4c2c5ba95.nq.gz
│   ├── 174ff7ad800b458c3e94d0b3ea7dad741c9e0f7f.nq.gz
│   ├── 267f4000c18cff43fe693caaa1f55fb1e921219c.nq.gz
│   ├── 363eb0fd250d195e2baf9a825128d28dc566c317.nq.gz
│   ├── 52f2e99c033f0ceada85be665f9ad352b54a019a.nq.gz
│   ├── 550be80c85bc0f2b1608b2cfb6f4f0234d73fdfe.nq.gz
│   ├── 6fcbe77c9d1180e4abf9037e9d147a8b79e51606.nq.gz
│   ├── 73197ac315a39de2674206cd527f4f8a61df0082.nq.gz
│   ├── 80a8fb8f603bacf0d3313100f60d45f9dac90baf.nq.gz
│   ├── 9a5ad2e3ae820a17714d64fb8af18bd72c7919f4.nq.gz
│   ├── cc1923a40b1a5e8c7fbdb8f9f6c6bbe26c35604b.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 31c253177d762a3456d673f6498713d91380e5f9.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 20 files
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

[click-contrib/click-spinner](https://github.com/click-contrib/click-spinner)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
