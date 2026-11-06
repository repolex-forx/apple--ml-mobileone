# Repolex Knowledge Graph of apple/ml-mobileone

RDF knowledge graph data for [apple/ml-mobileone](https://github.com/apple/ml-mobileone), parsed by [repolex](https://repolex.ai).

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
rlex download apple/ml-mobileone
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 3cebdf04a1524c447ab5e44a5235524f8da46f8d
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 3cebdf04a1524c447ab5e44a5235524f8da46f8d
│           └── chunk-001.nq.gz
├── blob
│   ├── 00ff27cab5c1a051c3f9db2e5df3970f497c277c.nq.gz
│   ├── 0df6744a7311b05df1b5e521e4d361149e61e571.nq.gz
│   ├── 1193eb851d9c699d89258db4be84a8e323ed6896.nq.gz
│   ├── 18d981003d68d0546c4804ac2ff47dd97c6e7921.nq.gz
│   ├── 1a8846430afa1148f27e70b43ea628128b740fb2.nq.gz
│   ├── 22aeedc113eab2a9f4b7bc2435bb8806c93b9eb2.nq.gz
│   ├── 24c645701af4ede169ec2c9df5d0016521694c44.nq.gz
│   ├── 368d96c25b69f2569ecb4abbb300f47c433c2367.nq.gz
│   ├── 3cbf3d2814ea50eeee7b71d0dee351501b8abd17.nq.gz
│   ├── 47185390aa67aa3b464c3ba9f625140a8d086e87.nq.gz
│   ├── 4d9ca101a8516d0d4390c67d2fbae9ace870c38e.nq.gz
│   ├── 511bf68534b7ef735a964845dd627bcd274cdcdf.nq.gz
│   ├── 5a7971f7676fd9e9407136d653826f462f8ef99a.nq.gz
│   ├── 705f9385bd60496a12a56017049ac5f6ebb24998.nq.gz
│   ├── 7385faa280d6338173e530b225598f7f224d15d0.nq.gz
│   ├── 7e4647018c844306c046db59bded10c8729ee3df.nq.gz
│   ├── 865e9329f3767a7c1dd66294b8025bf81dee7d2c.nq.gz
│   ├── 8a0497978067a3574983bcb9319e7ba4612049b0.nq.gz
│   ├── 8e4b2fdccf87002c184c4d76331fba30c5a3da88.nq.gz
│   ├── 919434a6254f0e9651f402737811be6634a03e9c.nq.gz
│   ├── 947d724cd42fe39b8b26bff31e84631ccd232565.nq.gz
│   ├── a1084fea4bb9a1dd4f391db9655cc737a8a7dfd7.nq.gz
│   ├── a81634e87424cbce194f380526d20742a14df122.nq.gz
│   ├── a9b949cabff7a7d11623d60c644780c16a8913c2.nq.gz
│   ├── b6949054241af508ed37428053dc533c909af042.nq.gz
│   ├── bcc68e57182968203401148777d86f01ff2b413e.nq.gz
│   ├── c5093dcfde540aca821e5d9dc4610f5ff02ef702.nq.gz
│   ├── c97533b8da88521d6c2161d7fd7afacb260cf8c2.nq.gz
│   ├── d5479fde00837df73f9b4d2d3bce8a1a19836f99.nq.gz
│   ├── dce26f1359d9746fbc4b0469d5376d8c9b9e9e97.nq.gz
│   ├── dd3c9afdae35805086796848ae7dfa52ec858a07.nq.gz
│   ├── dfe24a79bb6d734d34f950746ea959077e94cb44.nq.gz
│   ├── e35b22ae5b5dedc40c80f96e4eac15480e96db4c.nq.gz
│   ├── f0a77fed6d4c732a6ebf6a0f73146e2e9f8337a7.nq.gz
│   └── ff96316648fa9c4b865bbac49452ed6e55a67cc0.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 3cebdf04a1524c447ab5e44a5235524f8da46f8d.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 41 files
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

[apple/ml-mobileone](https://github.com/apple/ml-mobileone)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
