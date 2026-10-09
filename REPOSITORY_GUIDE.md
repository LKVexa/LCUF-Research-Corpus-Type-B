<!-- SPDX-License-Identifier: GPL-3.0-only -->
# LCUF Research Corpus — Type B Repository Guide

Copyright (C) 2026 RUSSELL PHILIP SMITHSON

This repository publishes **Type B: LCUF Research Corpus 0.2.0**. Its complete corpus is provided as [`LCUF_RESEARCH_CORPUS_B.zip`](LCUF_RESEARCH_CORPUS_B.zip). This is a byte-exact copy of the original Type B distribution archive, with **762 files** under its internal `LCUF_RESEARCH_CORPUS_0.2.0/` directory. The archive preserves the entire Type A baseline under `LCUF_RESEARCH_CORPUS_0.2.0/baseline/0.1.0/`.

The repository also includes all **12 publication documentation files**, including the root [README](README.md), [full description](FULL_DESCRIPTION.md), [LICENSE](LICENSE), [NOTICE](NOTICE), [COPYRIGHT](COPYRIGHT), [licensing scope](LICENSING.md), metadata, integrity manifest, standalone license and documentation-validation records. These publication files are exact copies of the prepared documentation package. This guide and [ARCHIVE_INTEGRITY.json](ARCHIVE_INTEGRITY.json) are additional repository support files.

The shared README describes both Type A and Type B and their archive distribution. The commands below apply specifically to this Type B repository.

## Obtain and extract Type B

Clone or download this repository, then open PowerShell in its root directory. Use a clean destination where `LCUF_RESEARCH_CORPUS_0.2.0/` does not already exist. Extract the included archive:

```powershell
Expand-Archive -LiteralPath './LCUF_RESEARCH_CORPUS_B.zip' -DestinationPath '.'
Set-Location './LCUF_RESEARCH_CORPUS_0.2.0'
python -B tools/verify_release.py --deep
```

The integrity receipt records the archive's current filename, SHA-256 digest, exact byte length, CRC test and file count. Older sealed package receipts inside or beside the original distribution may refer to its earlier versioned filename. `ARCHIVE_INTEGRITY.json` is a separate distribution receipt; it does not rewrite those original receipts or authenticate an author.

For a PowerShell archive-hash comparison from the repository root:

```powershell
Get-FileHash -LiteralPath './LCUF_RESEARCH_CORPUS_B.zip' -Algorithm SHA256
```

Compare the result with `archive.sha256` in `ARCHIVE_INTEGRITY.json`. The versioned release manifest provides the individual-file integrity records after extraction.

## Run the Type B host extension

From inside the extracted `LCUF_RESEARCH_CORPUS_0.2.0/` directory:

```text
python -B extensions/lcuf_x.py check examples/accept_residue_add.lcufx
python -B extensions/lcuf_x.py run examples/accept_residue_add.lcufx
python -B extensions/lcuf_x.py run examples/accept_coset_prefix.lcufx
python -B extensions/lcuf_x.py run examples/accept_hrr_noninverse.lcufx
python -B extensions/lcuf_x.py run examples/accept_remote_wire.lcufx
```

Type B applies twenty research articles through five design volumes, an article application matrix, typed profiles and a bounded host reference. Its `LCUF-X/0.2` language supports 21 closed operations, including finite residue arithmetic, real-valued coset fields, HRR, periodic diffusion, decoded raster indexing and scaled-sign compression state. It preserves the JA mathematical foundation and separately identifies new engineering contracts.

The extension publishes 352 conformance records, 208 numerical comparisons and 60 new tests. Host programs execute in one process. The remote-wire example models an authorized transfer; it does not contact a network. Native boot images, authenticated federation, a complete distributed optimizer and physical implementations remain architecture contracts with explicit acceptance requirements.

Read `README.md`, `REPRODUCIBILITY.md`, `design/ARTICLE_APPLICATION_MATRIX.md` and `validation/VALIDATION_SUMMARY.json` inside the extracted version folder for detailed design, dependencies, commands and evidence. The recorded environment is CPython 3.12.14 on Windows AMD64. Core host execution uses the standard library; schema replay uses `jsonschema`, and optional numerical comparisons require NumPy 2.3.5. The offline dependency tree includes a native component for CPython 3.12 Windows AMD64; other platforms need compatible pinned dependencies. Regeneration can rewrite evidence, so preserve an untouched extraction for comparison.

## Copyright and license scope

Copyright (C) 2026 RUSSELL PHILIP SMITHSON.

The original publication documents identified in [COPYRIGHT](COPYRIGHT) use **GNU GPL version 3 only (`GPL-3.0-only`)**. This repository guide and its original archive-integrity metadata are also licensed under GPL-3.0-only. You may redistribute and modify these covered works under version 3 of the GNU General Public License as published by the Free Software Foundation. They are supplied without warranty, including implied warranties of merchantability or fitness for a particular purpose. The complete terms are in [LICENSE](LICENSE).

The corpus archive retains its existing file-level terms. Supplied articles, figures, upstream snapshots, frozen references and bundled dependencies retain their respective copyright and license notices. The publication GPL grant does not relicense every corpus file. Preserve the original notices and provenance. The Free Software Foundation copyright in the complete GNU license text remains intact.
