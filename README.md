# Repolex Knowledge Graph of dask/dask-glm

RDF knowledge graph data for [dask/dask-glm](https://github.com/dask/dask-glm), parsed by [repolex](https://repolex.ai).

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
rlex download dask/dask-glm
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 8dee45ab865d2df8dd004693f38e2491c1eb88e1
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 8dee45ab865d2df8dd004693f38e2491c1eb88e1
│           └── chunk-001.nq.gz
├── blob
│   ├── 06df5331b452dae0c4eea1f2622f2c5099a62455.nq.gz
│   ├── 08c3949833ff6b0440ee18662e2ed7c131617c09.nq.gz
│   ├── 26a421c92de5e5dbb35b88fc9f2e0f0ef4c6e557.nq.gz
│   ├── 2d93cd1a57f958d8e638b823cb7169ee3bdd8921.nq.gz
│   ├── 3470b086ade97ee55f8005b82ea6ceb14d02aaa2.nq.gz
│   ├── 4d903340541bb56b5a578144d33b5bb0e2934722.nq.gz
│   ├── 4f836548081d917541cc8fc77b70b08813a18f32.nq.gz
│   ├── 5064c036ac83e0e19aa24443932048b3c54072fa.nq.gz
│   ├── 50cf76cb85a36fd03b984319c4907a66eafbf864.nq.gz
│   ├── 53749abb45ee85353a632567c529b632701ea686.nq.gz
│   ├── 5867e8a7b7550f6bfe1901d7669a689e1958ac89.nq.gz
│   ├── 58f24298fad37bd50a828f41828e7bf5df3cd8e8.nq.gz
│   ├── 59ffc43c2a1e8cb834a03c1a41fd74ef6379a3f0.nq.gz
│   ├── 5d0fa2ddcfa713603fedf34a07ac7f1632df4909.nq.gz
│   ├── 5d4c011a5595d1f0f1b0abc5c3e2a4ad8a89656f.nq.gz
│   ├── 783cb7269e76b421fccdf1e5e5bb573814175d0f.nq.gz
│   ├── 7f39fd799c9f50d6ede310849bf4686f2e7893fb.nq.gz
│   ├── 833c4b29bcb4ce25895cad38884877b56cbffb35.nq.gz
│   ├── 912f0b6314cca0625e20ed96faddbd4ead8aa784.nq.gz
│   ├── 940f7371ce5f9a44e289ed5a62822fcdf4292362.nq.gz
│   ├── 9e13c8f520a9aec55a477522f7ee37f0f5aba716.nq.gz
│   ├── a7634d5be612a65fb413f0865ac74915fb5dc7b8.nq.gz
│   ├── ab4175a59fe6a4d47de60f899e7442bb1fde9585.nq.gz
│   ├── b104a4d9a57d00b1855b5bb0abc19d734519901e.nq.gz
│   ├── bd9b3faf3bc2bd67c7a03210280b40747cfec764.nq.gz
│   ├── beddb8d73157fe301d3b8ac6191a3a3004c4cab8.nq.gz
│   ├── c6699457312d283244011fbefd67dcac67b0bdef.nq.gz
│   ├── cbd82a5888d64ad2eb75db7270b678312aca1f69.nq.gz
│   ├── cd17b6c0786b96cd8842cd4f1cfb16077cff315f.nq.gz
│   ├── ce213adad63c2e35033e44247b82a0e9c800f2e4.nq.gz
│   ├── d592621db8a827134578061c6f4db882ae2b64ee.nq.gz
│   ├── d6c6523ac0da2ec867d0609c322ea4fb96fbd473.nq.gz
│   ├── d701e83a5a96a9e892084d4509ba1e3a8d078bd2.nq.gz
│   ├── da491545558a849541b194ef41ee67698c06a11f.nq.gz
│   ├── e73686e378cb9f6c2b318ea748a0279714b13fec.nq.gz
│   ├── e98875c859b6b2d7c0f6714aa1064d229ac9d666.nq.gz
│   ├── ebd0fae7307c330f3eafa26bd8c66f6b8365c2b3.nq.gz
│   ├── fd736652dfac0c61eb7be3354fd6d46241065dc7.nq.gz
│   └── fdc7265c8873c0e8dddff9943c003e5066c479e7.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 8dee45ab865d2df8dd004693f38e2491c1eb88e1.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 47 files
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

[dask/dask-glm](https://github.com/dask/dask-glm)

---
*Parsed on 2026-10-17 by [repolex](https://repolex.ai)*
