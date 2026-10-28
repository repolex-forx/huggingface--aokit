# Repolex Knowledge Graph of huggingface/aokit

RDF knowledge graph data for [huggingface/aokit](https://github.com/huggingface/aokit), parsed by [repolex](https://repolex.ai).

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
rlex download huggingface/aokit
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 66b74bef60dbcbb20e441e0793ef6444bc20402f
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 66b74bef60dbcbb20e441e0793ef6444bc20402f
│           └── chunk-001.nq.gz
├── blob
│   ├── 05f05ca4e89d60ce71c610c50d906fc690804306.nq.gz
│   ├── 08a3eaf6cf46ffc06574c626a4fb3a504c66cfed.nq.gz
│   ├── 12f0f5f7be8aa5863aa2080de0791601fe8cf138.nq.gz
│   ├── 15f7bdd7916ac5fca2274ad5d1239bafe0f0f5a2.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 315bf888697af9c585f52a8e11073c9810eb76a3.nq.gz
│   ├── 330265c5eb860f77009d63799014735ef7e10458.nq.gz
│   ├── 33c114655b26f5f23a74874590e4953c86583df2.nq.gz
│   ├── 3f3474255791986caaaf53861b212e42f639de82.nq.gz
│   ├── 4181ad462a2d39b3401b4564f3cc938e60e83fa4.nq.gz
│   ├── 4915b6b5067cccee6a63ea2cc73ffcf142cfa1f7.nq.gz
│   ├── 5d847eb5a91b135b9307abbf89ce5e355cb4f608.nq.gz
│   ├── 6606c6325c1422e0430f1dc19eedab05c3287e7c.nq.gz
│   ├── 7c794f90b7906f7823326e0bf218f6e585c2af2c.nq.gz
│   ├── 82bf0e22551773eb4af81c8e6a12a00cd8dd9585.nq.gz
│   ├── 8a03263a1e618c7d3fb4b10948db467375bccf3b.nq.gz
│   ├── 901075dca64cd54a7ac4911fb4926cda31edc65e.nq.gz
│   ├── bddac976f33f340a379ecbaf6938ab0dea576749.nq.gz
│   ├── cf5794cc7e0856bea870265d4e2ed8fdf6f73c91.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── eecb78e0cc25ed40f1a6547b613585e2eac12885.nq.gz
│   ├── f1ee630c7be579ded489000f848c3b417683afb6.nq.gz
│   └── ff22940438b43093e7ae4daf5f7fc2c5f0ef27d1.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 66b74bef60dbcbb20e441e0793ef6444bc20402f.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 31 files
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

[huggingface/aokit](https://github.com/huggingface/aokit)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
