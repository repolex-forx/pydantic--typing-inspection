# Repolex Knowledge Graph of pydantic/typing-inspection

RDF knowledge graph data for [pydantic/typing-inspection](https://github.com/pydantic/typing-inspection), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download pydantic/typing-inspection
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 8db011350942f33ac4b5d7db60d4d9ea83ab480f
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 8db011350942f33ac4b5d7db60d4d9ea83ab480f.nq.gz
│   └── repolex
│       └── 8db011350942f33ac4b5d7db60d4d9ea83ab480f
│           └── chunk-001.nq.gz
├── blob
│   ├── 0a197900e25d259ab4af2e31e78501787d7a6daa.nq.gz
│   ├── 0ac82642764385ea3f11da13ebedc6811b87d995.nq.gz
│   ├── 264c88eed7d4ac9d44ad12c9ebcd5045ac896aa8.nq.gz
│   ├── 2d7a5346d39b916772dfb8386e535f71c10a7cd8.nq.gz
│   ├── 2e75782b89c6c1c7900f3625933247e92a728495.nq.gz
│   ├── 405f2fc146a459b1d1bf7f9ea5d1049086cc6559.nq.gz
│   ├── 5071598005a21063ff3b2a2a1dedced885267de6.nq.gz
│   ├── 55d7071e8e79f1b236b0800eb95804ca2b2fac15.nq.gz
│   ├── 6d9dd09f3752e8fb347fe1e107160b942f977ac8.nq.gz
│   ├── 7a538c6df8891c05b229eaf029d6137969479c67.nq.gz
│   ├── 7d6287fa8a2b7a80b98346d1cb46a9f72a2cd38b.nq.gz
│   ├── 869dc6ce80b2f84427c92b0ae2b0304fea14b1c3.nq.gz
│   ├── 95ad356f1a776d303f3dd45e7cd6facaf812af41.nq.gz
│   ├── 96366638f10739ec6baac3a3377fa4b289cf6d2f.nq.gz
│   ├── 9cda3eaa371814c9740cb9c764b1b6d043fb6922.nq.gz
│   ├── b2355ef1e38de91b3a5317bbc213d0baf69d1ec2.nq.gz
│   ├── c6a1cd16ae5f8123f919d4fe062fa6acd82f3c16.nq.gz
│   ├── c7ee4acec462f3fd91b8b0baf598f92ccacf580d.nq.gz
│   ├── caeb2f71973c883afa9fcb90cef93ffef4bcfcf2.nq.gz
│   ├── cf15d676dbc58b3866aef31f9d2be723c5974d9d.nq.gz
│   ├── d6c083e5456c8ad5da7559a3c0a901e0812a5014.nq.gz
│   ├── d7127586af34ff232d2938e337731b9b100b0dbf.nq.gz
│   ├── dc44ba98cd8ccdba374982819083d89bbf808c2e.nq.gz
│   ├── e36c3386b6578a5a62e230e03de8ebabbeb7a7cc.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e825ad51621c5e34d370ba64f13f6854d89456a6.nq.gz
│   └── f954bc309139d0be2a3562fd9c76882a0239fc5f.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 8db011350942f33ac4b5d7db60d4d9ea83ab480f.nq.gz
├── filetree
│   └── 8db011350942f33ac4b5d7db60d4d9ea83ab480f.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 37 files
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

## Source repository

[pydantic/typing-inspection](https://github.com/pydantic/typing-inspection)

---
*Parsed on 2026-09-16 by [repolex](https://repolex.ai)*
