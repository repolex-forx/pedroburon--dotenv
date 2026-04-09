# Repolex Knowledge Graph of pedroburon/dotenv

RDF knowledge graph data for [pedroburon/dotenv](https://github.com/pedroburon/dotenv), parsed by [repolex](https://repolex.ai).

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
lexq download pedroburon/dotenv
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 0768eb37483922117d17fd5e5641f3fc9052f757
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 0768eb37483922117d17fd5e5641f3fc9052f757.nq.gz
│   └── repolex
│       └── 0768eb37483922117d17fd5e5641f3fc9052f757
│           └── chunk-001.nq.gz
├── blob
│   ├── 0ff045128b5590d3bbf91e42b84fc85d87461a52.nq.gz
│   ├── 11920bd618d31c1bc3e53b3ded7786dc289db79b.nq.gz
│   ├── 14b560c6f34f8a8616a10589f853385d3f946e4c.nq.gz
│   ├── 3412c932814605d011bbaaf7912311ede4fd8184.nq.gz
│   ├── 5e16252936686aaaca4aa1d704dff7d34775a35b.nq.gz
│   ├── 65dd2c6a75545aac8fce76471d6890563c3e2375.nq.gz
│   ├── 727c46c9c87187293f0e79bd3f3e2b9971268249.nq.gz
│   ├── 9b83e5e1d8af2dd218256c6a8623b4b1de5de1bc.nq.gz
│   ├── 9df810bdb656b356b6ba79c68750505ce89b6f3d.nq.gz
│   ├── a3d5f79834f82c669b37de900cdc3f11c576afd2.nq.gz
│   ├── ca0dcb3a29df85dbc45ed72b2302067d6395258a.nq.gz
│   └── db089e313f3b11686530f43aedb304997de0f994.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 0768eb37483922117d17fd5e5641f3fc9052f757.nq.gz
├── filetree
│   └── 0768eb37483922117d17fd5e5641f3fc9052f757.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 22 files
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

[pedroburon/dotenv](https://github.com/pedroburon/dotenv)

---
*Parsed on 2026-04-09 by [repolex](https://repolex.ai)*
