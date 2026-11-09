# Repolex Knowledge Graph of rack/rack-test

RDF knowledge graph data for [rack/rack-test](https://github.com/rack/rack-test), parsed by [repolex](https://repolex.ai).

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
rlex download rack/rack-test
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── b3bfdbc79e6e69eb4e63994ec7d1e15130680054
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── b3bfdbc79e6e69eb4e63994ec7d1e15130680054
│           └── chunk-001.nq.gz
├── blob
│   ├── 197d67dbe7fea5daeb4e3b45c7e4e32c99194350.nq.gz
│   ├── 1a0c2fbd114b1fdf13edd680741b7a1241ec9df4.nq.gz
│   ├── 3c570af1f9a2a28df6dde6e46efaa7ae0cf79a3c.nq.gz
│   ├── 45429472f83745f4661697adb81635b6ca5c3659.nq.gz
│   ├── 52a7cfa77cc95d1d818cd67d22517904de737e39.nq.gz
│   ├── 5716ca5987cbf97d6bb54920bea6adde242d87e6.nq.gz
│   ├── 5bfe9a7d9b2eba955d7c531fd565b2ab04f87bd9.nq.gz
│   ├── 5da5356769ba0ba9d2b8e1edca6f2b089653fd3b.nq.gz
│   ├── 6000a593a912343340368856c48d2964a043f390.nq.gz
│   ├── 649caf31e8791eabd13f8657ea7a27282c7581ce.nq.gz
│   ├── 669a68cda22f28df9032c5b36cbed885e79f0a0e.nq.gz
│   ├── 6b68062631f4b82159f71c7767ba32c44d5cdc0a.nq.gz
│   ├── 7317af0424e6a4a884a3d5ab1122c3747c49c20a.nq.gz
│   ├── 76018072e09c5d31c8c6e3113b8aa0fe625195ca.nq.gz
│   ├── 82e3b60905c0485cbeb908407e26c05536df5058.nq.gz
│   ├── 854c5829d40ec98a56953afa012d2c2907560a16.nq.gz
│   ├── a1b4f3941feb0dc4f24f09cf84cd122bbdcfb303.nq.gz
│   ├── a30d02d4432e982115b1d2d4ebaef4c8f7afb5c6.nq.gz
│   ├── a7aa2bbd463bce1cf958d209fcbb73d9b747fe7e.nq.gz
│   ├── b39352095f0ccd0141f0b8312fb4633ecb1ebc64.nq.gz
│   ├── badbee6648413fc28841bf88671e704fd58eba99.nq.gz
│   ├── bae729158172d080f00a3ac00a08dc858d8f5ee8.nq.gz
│   ├── befb4b68ac479d2ea9b4e1ab5df280752c831678.nq.gz
│   ├── c085c607212f21b3f9376e3a81a7ea7429481cad.nq.gz
│   ├── c0c6e9b7fd6d9b602d55118cb5b36c226d65f54a.nq.gz
│   ├── c77f08a0246dfe8b1ceb7dbd01adf7d178e8dd88.nq.gz
│   ├── c86ab3cb9729476ed1ab8e3b5a609250204bae6a.nq.gz
│   ├── d8ff52b2a13b7ceb9fe0be8e7c72cb904c5cbac0.nq.gz
│   ├── dd0f6aaa2bde95283cb7bcfeb8ff6d7c76c4e987.nq.gz
│   └── eaca65faa3d421be2c913125154e170c7e482411.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── b3bfdbc79e6e69eb4e63994ec7d1e15130680054.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 38 files
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

[rack/rack-test](https://github.com/rack/rack-test)

---
*Parsed on 2026-11-09 by [repolex](https://repolex.ai)*
