# Repolex Knowledge Graph of webpy/webpy-examples

RDF knowledge graph data for [webpy/webpy-examples](https://github.com/webpy/webpy-examples), parsed by [repolex](https://repolex.ai).

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
rlex download webpy/webpy-examples
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 196ec74f121f1ed90e0e63794f268f123adeb106
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 196ec74f121f1ed90e0e63794f268f123adeb106
│           └── chunk-001.nq.gz
├── blob
│   ├── 1331da6d20dc347d8fed1f367be6acd9eff19cc7.nq.gz
│   ├── 1c188a10390091f811dab715dcfb945f3af8e8b8.nq.gz
│   ├── 1c1a7f7b1f73faac2adc2c306a0ac9df3739bf23.nq.gz
│   ├── 1ff82c349d63adcf7801c870403082dd216b9a5d.nq.gz
│   ├── 2c46080f6219a467e831425d8003da6555538f56.nq.gz
│   ├── 371c948bbe5c1e16614b834cc77cc5d696dd6fec.nq.gz
│   ├── 4c75dd727c909c1e3518057c458be65ffed67d3a.nq.gz
│   ├── 4c77d0f65bf084b6db5f1bf2ba4869d0c10de9e8.nq.gz
│   ├── 4cfe27738c60a025ca38ac96c5df6c0615932360.nq.gz
│   ├── 52593149b78b4e49fdfa04cfd5563be84339479a.nq.gz
│   ├── 6f91d63853ad52bb46d58fcdb302b6bfeb5a1433.nq.gz
│   ├── 80d62aa162ca05bb4662e6666b3303d682ad7240.nq.gz
│   ├── 894a44cc066a027465cd26d634948d56d13af9af.nq.gz
│   ├── 8d96a034bd3a3a48e677bf39e7598b2648eb6810.nq.gz
│   ├── 919e9ac93b1cff8c6b4907388596ca41b5d91481.nq.gz
│   ├── cb584ab139324fbfcd499758a8c30c7765d46199.nq.gz
│   ├── d5442d6347c6322ec63a3055de7c88be15600d8b.nq.gz
│   ├── d7e3469d974dc59aaf76a1ade7766c1448655702.nq.gz
│   ├── ddd49dfd098c68364296d0f133c4dc2db73e66a4.nq.gz
│   ├── de5c0bceced670599c8988d71ffc28e7b64ecec9.nq.gz
│   ├── e1efabd499e037f3f544ddb8fd7a86704738e139.nq.gz
│   └── e2405e6673ad6590428154f182920ffab07c692f.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 196ec74f121f1ed90e0e63794f268f123adeb106.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 30 files
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

[webpy/webpy-examples](https://github.com/webpy/webpy-examples)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
