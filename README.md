# Repolex Knowledge Graph of encode/requests-async

RDF knowledge graph data for [encode/requests-async](https://github.com/encode/requests-async), parsed by [repolex](https://repolex.ai).

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
rlex download encode/requests-async
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 1de1b948a09b1e164b62c3617b6702d266fc94b2
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 1de1b948a09b1e164b62c3617b6702d266fc94b2
│           └── chunk-001.nq.gz
├── blob
│   ├── 0087e106dc840903008de32da2b77da18a473c5c.nq.gz
│   ├── 046f8ed7cd85fed396e8e256c64c578a4d8931f4.nq.gz
│   ├── 07098666f40e3f931faea6209c5ed320c16dbb59.nq.gz
│   ├── 1972c8eeb6ac5aea6e947d008ec8939d332544d4.nq.gz
│   ├── 2c6fb51c9de33e7d063d2499f93ddbedbb931954.nq.gz
│   ├── 2e2045634b138bea5e8c1abeda3cc3ff7e404d0e.nq.gz
│   ├── 394ccbe41a3e324cad0c4aaa12a770d0427a651e.nq.gz
│   ├── 3e082779d7ce8b50eec573ed48e85ae35c37e910.nq.gz
│   ├── 48b4f51fdcad816ac7381c57899b8ccd1f828f2e.nq.gz
│   ├── 5554990983b5a6dc7b3467411654aa91a074b6d4.nq.gz
│   ├── 7071898450d34ec08ffc8d6dd6a69298e7f8a488.nq.gz
│   ├── 938e2d157f6859521b0b0d97f64612cfd51d0d9e.nq.gz
│   ├── 93c83dec5e12629606577baaa10197aa7c3646c8.nq.gz
│   ├── 94cc0b225083ed85e701ea6a77ac1d5bd56ae0dd.nq.gz
│   ├── 99f3b89ee3de4488ac6cdc02fe1a380c9ce4292c.nq.gz
│   ├── a043a2a5659f6b7dd5790c18d917303c4e8feb67.nq.gz
│   ├── a1720c832f3233e9aa5d68ebedeee3ae5258ae58.nq.gz
│   ├── a35ea9a76fa3bf55c9d24c3c65452ab2bfeac10d.nq.gz
│   ├── a56dea65639a3304c9ff96a543429fa458f4ffd2.nq.gz
│   ├── bcbee22481ff2df845cd8837d1b7a34fac31c20a.nq.gz
│   ├── cf54d9899f1f3b4d1a59274aa89bbc1c2a2fc1ca.nq.gz
│   ├── d42904fb867092875ec6f7bc05f818fe78f85766.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e8ef29ae12360b3925107c317977f197b77cc8bb.nq.gz
│   ├── ed7c425e5489faf006a2d24d46702af8cf3976d9.nq.gz
│   ├── ede5dbb41ec0547a5f6a28a10b1c59b1e3eacfc3.nq.gz
│   ├── eff072eedbb381b1b559fa6560182425b108b151.nq.gz
│   └── f6898f58bc5af8c009ce19235f5fceea233c1687.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 1de1b948a09b1e164b62c3617b6702d266fc94b2.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 36 files
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

[encode/requests-async](https://github.com/encode/requests-async)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
