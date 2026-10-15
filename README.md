# Repolex Knowledge Graph of astropy/astropy-iers-data

RDF knowledge graph data for [astropy/astropy-iers-data](https://github.com/astropy/astropy-iers-data), parsed by [repolex](https://repolex.ai).

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
rlex download astropy/astropy-iers-data
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 46fb023b0648a5e97a8f95ab1eeb15f40f6bdd2b
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 46fb023b0648a5e97a8f95ab1eeb15f40f6bdd2b
│           └── chunk-001.nq.gz
├── blob
│   ├── 02ce78e072367ec5f038c71829ff0662fd94b4bc.nq.gz
│   ├── 0bd9a031c71ca82d634fea0e9d59b01678582c1d.nq.gz
│   ├── 192b213ff456b3e370a71d358eddb4216d0f0a09.nq.gz
│   ├── 28c903f07a82579330ea8e1a282dd91059e33e1f.nq.gz
│   ├── 382f6e7693a2a0f3d078984f7e227a8757462a84.nq.gz
│   ├── 4acaf5e625abd16c47884aa9b9fa0cca441ba752.nq.gz
│   ├── 551c6f5f1b0a07cef6f6df10453bbaca442371d9.nq.gz
│   ├── 572a6b4b6d24f18d9e0e407cc48c355c8aff7f61.nq.gz
│   ├── 624546e5656d00a2669cf4ceaf5818cc171d926f.nq.gz
│   ├── 650379c4e9d522ed9cf89c700260be6bf141e5f0.nq.gz
│   ├── 6e9d6b99a94229abbee0dd0c9670f07bffdd9757.nq.gz
│   ├── 73506af86f932ff48f37cda7c0352b4cf5a09829.nq.gz
│   ├── 769c4a68ff949550e05c6ffbfc9a72dd91b4208d.nq.gz
│   ├── bad7a41d3bd1b1281f01e13b4a412d6e7ec51483.nq.gz
│   ├── bfec37840d0adb88fb59d9f3607ae46478292bd3.nq.gz
│   ├── c6f9e17995296d9b2c7804b3b71bbe4a36375149.nq.gz
│   └── e4b26ddbed225b997a1eb19c679d53d13197e97e.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 46fb023b0648a5e97a8f95ab1eeb15f40f6bdd2b.nq.gz
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

[astropy/astropy-iers-data](https://github.com/astropy/astropy-iers-data)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
