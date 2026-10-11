# Repolex Knowledge Graph of samuelcolvin/buildpg

RDF knowledge graph data for [samuelcolvin/buildpg](https://github.com/samuelcolvin/buildpg), parsed by [repolex](https://repolex.ai).

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
rlex download samuelcolvin/buildpg
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── e2a16abea5c7607b53c501dbae74a5765ba66e15
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── e2a16abea5c7607b53c501dbae74a5765ba66e15
│           └── chunk-001.nq.gz
├── blob
│   ├── 01aae69a824ae3b8e631b7cc928c08f464540eb2.nq.gz
│   ├── 0456082bfdd4506619665ca88b0a72c729f0697f.nq.gz
│   ├── 09553a8c9a42a3760d6dcfb6d5a42e0f7d7eafb3.nq.gz
│   ├── 0c71cd70bbe38f1dc109d5269a384fbfcde3c652.nq.gz
│   ├── 0ded0420be269417ec2bf0b5b839c4caab361c4e.nq.gz
│   ├── 155836bfa7280f7e8ce386d449a0cf43433e4504.nq.gz
│   ├── 2ac794d5b2ff814b5e417d62652a9397f2ebf793.nq.gz
│   ├── 3ade0b8d2a298c963e71a679e359ef5fc52049fc.nq.gz
│   ├── 4854c09c0a17f1bc39ffbbb98cf0174415d34597.nq.gz
│   ├── 4eea85780da1cf7be75d5cbd4cba5322f4ee6a62.nq.gz
│   ├── 51319988dd9f83da89e15d3d9b19c1573673bf89.nq.gz
│   ├── 592e67dd097da9be85049d5eb3a03947d4cd4f30.nq.gz
│   ├── 645a2e1d1cdf07dfe3280541ef029a75ce71711b.nq.gz
│   ├── 6891cf8734e0a915ecc0fcfbc393d0fd1e470902.nq.gz
│   ├── 6bf130f0c91398ab024a5130ac602bb4ccd9cb0e.nq.gz
│   ├── 6f79c63d718f4929ccb30e569d4981acbdfd541f.nq.gz
│   ├── 7629d64646c3b0d460a135fe40b2c63731e3fbd1.nq.gz
│   ├── 7bd95ecedb8af925bdcdbb2eca0dbb76f9eaee8a.nq.gz
│   ├── 88d25c8aebf0a5a0c76bc1b0673db9868eb769a7.nq.gz
│   ├── 944a8c7a94baafe7f90ce4275ab7ebf03ffd9efe.nq.gz
│   ├── c49dd5fefd6f5a43d57fb050bf9f16e7db43589e.nq.gz
│   ├── dc9680b875bf33eb2f59d944e4d6c97252bd1dd9.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── f5020f0476f9efc057158894988aedaee1a6f7f6.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── e2a16abea5c7607b53c501dbae74a5765ba66e15.nq.gz
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

[samuelcolvin/buildpg](https://github.com/samuelcolvin/buildpg)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
