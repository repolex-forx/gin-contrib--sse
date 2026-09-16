# Repolex Knowledge Graph of gin-contrib/sse

RDF knowledge graph data for [gin-contrib/sse](https://github.com/gin-contrib/sse), parsed by [repolex](https://repolex.ai).

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
lexq download gin-contrib/sse
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 41aa9c0d6d639b46ce650e49009820fd864f9df5
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 41aa9c0d6d639b46ce650e49009820fd864f9df5.nq.gz
│   └── repolex
│       └── 41aa9c0d6d639b46ce650e49009820fd864f9df5
│           └── chunk-001.nq.gz
├── blob
│   ├── 068107b64c30b936253d935e9830ccff46f7ba8f.nq.gz
│   ├── 1a82f3f561873da3e5158ba107b86195dbef4ba8.nq.gz
│   ├── 1f44caf582e0c744b9c19653822ea279028ba91e.nq.gz
│   ├── 1ff7f370605592e4c09bd16f6775c075631bd9e6.nq.gz
│   ├── 47094ac61f1d9bb7ec2549c29b916015ae7f2c4b.nq.gz
│   ├── 4c910add43b906a9ed15bc34e19f62cf73ce2f67.nq.gz
│   ├── 503d775a8e3c26a94a9a4b6a57f85e9537b8bbd1.nq.gz
│   ├── 632e8eb25cb1d8b150df7205f82cc6c8df23982d.nq.gz
│   ├── 6df102df03e794e3dd7a04848517debf522d1692.nq.gz
│   ├── 724d9d07dd9f9d44f768f3d99cd098985a5ae0db.nq.gz
│   ├── 9ebb49f41808abbcc01535a1916d066fd0bb1eee.nq.gz
│   ├── a63ac203746929cac829a8f9492efad78973a7bf.nq.gz
│   ├── baf143b8b4cf6e76f4d44310d0b76f94d172beb1.nq.gz
│   ├── c4c1710c475c1aaf6b41e75cf7003b167ddb3739.nq.gz
│   ├── d34f5d807461d99e55629d011868fa878e78d9f1.nq.gz
│   ├── d5be52395ced960e1e6c0524a311fef5a7fd85b0.nq.gz
│   └── da2c2d4b642edad250dcd4d9516aee56d4b8c004.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 41aa9c0d6d639b46ce650e49009820fd864f9df5.nq.gz
├── filetree
│   └── 41aa9c0d6d639b46ce650e49009820fd864f9df5.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 26 files
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

[gin-contrib/sse](https://github.com/gin-contrib/sse)

---
*Parsed on 2026-09-16 by [repolex](https://repolex.ai)*
