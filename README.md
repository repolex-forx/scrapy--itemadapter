# Repolex Knowledge Graph of scrapy/itemadapter

RDF knowledge graph data for [scrapy/itemadapter](https://github.com/scrapy/itemadapter), parsed by [repolex](https://repolex.ai).

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
rlex download scrapy/itemadapter
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ef0b748c57de506a0524db06537e006a207a40b5
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ef0b748c57de506a0524db06537e006a207a40b5
│           └── chunk-001.nq.gz
├── blob
│   ├── 0451c67c40dfe50855ae8840480c11647d422a8e.nq.gz
│   ├── 0866612da722576d01a590d1bc0fe977b7c3ba61.nq.gz
│   ├── 128f64f198ef0a707dc341c0356568f7e9aff130.nq.gz
│   ├── 21b0d43d1bd3fc61c4c450029732b58f1baa9186.nq.gz
│   ├── 229667c06ad08c06a2d877c790c2dcee9e850ced.nq.gz
│   ├── 2d421349ad3382828d826de61fc9bdb9ded9e509.nq.gz
│   ├── 2df565a4c0ad329720b36bc655bed7bd058c1144.nq.gz
│   ├── 3eab9890b4f3389a5c16175c5d497856b2c9310d.nq.gz
│   ├── 4df3fa6e0566944e8a781d2a6762fc6b26ce1178.nq.gz
│   ├── 5b7ddf9c0651abdb81ecd23567bed4af4db62f00.nq.gz
│   ├── 606303c1cb2d7e1fcec907479c6ad69490d78091.nq.gz
│   ├── 60dcad6ebdbf19ac78bbeb2097cc5bc483170b93.nq.gz
│   ├── 60f3e1a185c0365c2f2924f955d1baf2fb8791ec.nq.gz
│   ├── 6223e4b760e13213d077f8920c8c6dd4fc2f0925.nq.gz
│   ├── 623d48cfa6b6f2ba551dde2435254ed5a1b63862.nq.gz
│   ├── 6906bd2c3ac839ed3911963195e25ec8df856319.nq.gz
│   ├── 734e40c059588383c76a537ce39dd419df03398c.nq.gz
│   ├── 7b228eb4992367524dc3e37e252cbf67b7941455.nq.gz
│   ├── 861e1bcb557e4971c36dc7db1864d92176e4f2b2.nq.gz
│   ├── 8ed25c73a997398f83b2b4c3639b640b28923ec0.nq.gz
│   ├── 9077106639d6ee01af74a0d04c4c6f91044f6d7b.nq.gz
│   ├── 9154cf5048f37687619cb7fd2c2198535030751c.nq.gz
│   ├── a3131347b3e75ef2a06b3f711823cf830714404d.nq.gz
│   ├── aa67d16ea6a7e95d80a5482f9c78362c3424702e.nq.gz
│   ├── ac83e7d861790f1803ca92c3378a90e85cdb5ce7.nq.gz
│   ├── b9fb51dbccf570940c9ca8d3ca9fff677347d8e4.nq.gz
│   ├── bf211e51b3a7f0e47344ac84d16823dcb40db027.nq.gz
│   ├── c04140f65de037dc9b47a2c0ae3f2d016786d97e.nq.gz
│   ├── c87fc3932863716d143f641b318721e8f7731855.nq.gz
│   ├── cf4b59a1e60c96c8f302d6a723320a9595161a31.nq.gz
│   ├── e254b0a415e16ce52471bca36dedb4584a996c0a.nq.gz
│   ├── e25ba921c56ef21b9f8925dece4b6852aeb42f3b.nq.gz
│   ├── e337fc6ce407eb9dfec30b98a7acdf6ac93ec165.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── e759659a7b373b4a73a45e1be3921323d0fcea39.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ef0b748c57de506a0524db06537e006a207a40b5.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 43 files
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

[scrapy/itemadapter](https://github.com/scrapy/itemadapter)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
