# Repolex Knowledge Graph of mne-tools/mne-tools

RDF knowledge graph data for [mne-tools/mne-tools](https://github.com/mne-tools/mne-tools), parsed by [repolex](https://repolex.ai).

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
rlex download mne-tools/mne-tools
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── de3c5489a62412b9456d5a139dd9cf4e67b6a426
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── de3c5489a62412b9456d5a139dd9cf4e67b6a426
│           └── chunk-001.nq.gz
├── blob
│   ├── 02c548063e8509fc58180a8c318f30a5ed843bee.nq.gz
│   ├── 104c102e40168b049debba65dc7a50d550c23078.nq.gz
│   ├── 10a28542000230312e510db478c2e5d64e2b2efc.nq.gz
│   ├── 168a1116be4d5b265a1749ec0524786bdb6670c0.nq.gz
│   ├── 18351b685a0dbda4eedbd7d69a88165e036173bf.nq.gz
│   ├── 23b123d2981d14e43b30a8db4727bbfb570e91a6.nq.gz
│   ├── 29bcd93664ed41528d97fe161715e9ecebd72ede.nq.gz
│   ├── 2ffe52f3cc8c49ce55976712ee4135b37a48c076.nq.gz
│   ├── 3086a28647ce1989fdfe2bb45f28bd71cb0b0912.nq.gz
│   ├── 33940d40d1c8cc99b01e0ce6fdf9050d03c4bc07.nq.gz
│   ├── 36a62ca598f6b7a796b4a95f36ccbf526e5fa588.nq.gz
│   ├── 37b3d36657e8b530d801a92e7a4254a23d70d65c.nq.gz
│   ├── 3b4cafc4f568e1880a6e7c43a268685aa019630c.nq.gz
│   ├── 43a8d34b7745c59fbe03c35bc514aa91491b193d.nq.gz
│   ├── 4946340095a99ead306974754a821a0b28247957.nq.gz
│   ├── 57a0f90db6c75dc98bbda1f7e9e4eb295cc90e6b.nq.gz
│   ├── 6038f42ca00db8caf385ee699221414625c740d2.nq.gz
│   ├── 6330d849f69d3e06d159a1e9b65b97d8b9b9a953.nq.gz
│   ├── 7704fd476961baf2f35f2265535db8d50e2e5859.nq.gz
│   ├── 785af871c570350cfbd43f50c697d8218e21eb93.nq.gz
│   ├── 79281623ab914b1669106d989f684b3b65e1dd40.nq.gz
│   ├── 7ab9824fc099cc28c8bca44341b5eac46aaecffd.nq.gz
│   ├── 7e50937b771e3de3b49c1f73048932c036ffdc60.nq.gz
│   ├── 7f9f95b04e16d65db5b01ecd104dcbd7c95ca61a.nq.gz
│   ├── 833448a2b19c581e40943847bfbaa00e99a8b3e1.nq.gz
│   ├── 8fed1f2550949ff2d7fa5d869116ef1f91267739.nq.gz
│   ├── 94ecb273cd1c6da9b3a421d77f8430377ac1dedb.nq.gz
│   ├── b2149072d89b7d75db3f8f22e157f32f4b93ae48.nq.gz
│   ├── bf169c8aa1e09121fd0e9e5d1d2384d951175a91.nq.gz
│   ├── c787b1285333221450004ff55853321196ca6e14.nq.gz
│   ├── dd799fcb447e3227ed1bec070caba0c8a39dc5ab.nq.gz
│   ├── e196ae044bf3a239b485caeaad2eade1500b3724.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e893c869ea732952ad5e8b0d8e49e2a1bc581aa8.nq.gz
│   ├── ec5ed282ecf26d860bb392be9c7bcc6da22671c2.nq.gz
│   ├── ec915bea461be3808290af19f83778f99d722f56.nq.gz
│   ├── f30b1a5e349e2ea3bbfff4ecc3d506965f6e189f.nq.gz
│   └── fa128e7f2674c8c0fd3aa96d0877ffd6ca54a11a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── de3c5489a62412b9456d5a139dd9cf4e67b6a426.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 46 files
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

[mne-tools/mne-tools](https://github.com/mne-tools/mne-tools)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
