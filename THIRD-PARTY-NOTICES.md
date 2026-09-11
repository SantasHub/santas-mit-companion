# Third-party notices and protocol references

No Albion game code, proprietary client library, packet recording or personal
data is bundled. Npcap is a separately installed system prerequisite and is not
redistributed. Its license and permission model are governed by its publisher:
https://npcap.com/#licensing

The 0.4.0 developer checkpoint embeds a public item-name/index data
reference from ao-data/ao-bin-dumps, commit
`0be6a5e74f30fc1312118be3d017f3832f027cef`, `formatted/items.txt`.
It supplies reference labels and item identities in reviewed Inventory and native
comparisons, not authoritative market values or proof of full live-version coverage.
It contains public game data, not captured personal rows or
game executable code. The reference contains 12,237 numeric indexes, item
identifiers and short English names, with no descriptions, artwork or game code.
No repository license was found at that source pin. The release records this
limited factual-reference provenance without claiming a license grant for Albion
assets or the copied compilation. No concrete conflicting rights requirement was
identified in the release review. Albion's support confirmation covers passive
listener mechanics; it does not establish a separate catalog redistribution grant.
The preserved 0.1.0 installer does not contain this new resource.
https://github.com/ao-data/ao-bin-dumps/tree/0be6a5e74f30fc1312118be3d017f3832f027cef
See `docs/DECODER-SOURCES.md` for its hash and the comparison limits.

## Offline translation review bundle

The bundle contains official PSF CPython 3.13.15 Windows x64 embeddable Python.
Its ZIP SHA-256 matches the publisher’s release page and is pinned in the lock.
The included license is retained at `translator/python/LICENSE.txt`.
https://www.python.org/downloads/release/python-31315/
Python and its packaged libraries run locally; users do not install global Python.

Locked Windows wheel contents retain their included notices under
`translator/packages/*dist-info/`. Additional upstream license texts and native
dependency notices are included in `licenses/`. CTranslate2's upstream engine
DLL is replaced by a source-built CPU-only DLL of the same version. Its Python
wrapper is unchanged. CUDA, cuDNN, Intel oneMKL and Intel OpenMP are not included.
The exact source pins, options and reviewed DLL hash are recorded in
`translator/cpu-runtime.lock.json`.

- CTranslate2 4.8.2 — MIT; OpenNMT contributors.
  https://github.com/OpenNMT/CTranslate2/tree/v4.8.2
- SentencePiece 0.2.1 — Apache2.0; Google and contributors.
  https://github.com/google/sentencepiece/tree/v0.2.1
- NumPy 2.2.6 — BSD3-Clause plus bundled dependency notices.
  https://github.com/numpy/numpy/tree/v2.2.6
- PyYAML 6.0.2 — MIT; Kirill Simonov and contributors.
  https://github.com/yaml/pyyaml/tree/6.0.2

Argos language archives are pinned in `translator/dependencies.lock.json` and
downloaded from https://data.argosopentech.com/argospm/v1/ . Wheel hashes come from
PyPI publisher metadata; model hashes were observed over HTTPS, not signed by
their publisher. Model weights/tokenizers are unmodified. Unused Stanza assets
are omitted. Each model's README is retained with its model. Spanish and Portuguese ship under
`translator/models/`; optional French, German and Russian are installed in the
user's companion language-packs folder after a verified download.
English↔Spanish uses1.0; English↔German1.3; English↔Portuguese/French/Russian1.9.

Where specified in those model READMEs, the underlying OPUS-MT model is CC-BY4.0:
Jörg Tiedemann and Santhosh Thottingal, “OPUS-MT — Building open translation
services for the World,” Proceedings of EAMT2020, Lisbon, Portugal.
The older Spanish1.0 READMEs list OpenSubtitles, ParaCrawl and UNPC/OPUS corpora
without a package license field. Argos maintainer PJ-Finlay explicitly confirmed
on August 2, 2026 that .argosmodel binaries use the project's MIT/CC0 licensing.
The MIT text is included as `licenses/LICENSE-Argos-MIT.txt`; original model
READMEs and attribution remain beside the model files.
https://github.com/argosopentech/argos-translate/issues/533#issuecomment-5160080718
https://creativecommons.org/licenses/by/4.0/
https://opus.nlpl.eu/

The worker uses public CTranslate2/SentencePiece APIs and references Argos
tokenization behavior; it does not bundle the full Argos/Stanza application.
https://github.com/argosopentech/argos-translate

## Native translation and runtime dependencies

CTranslate2's pinned CPU build includes oneDNN 3.1.1, cpu_features, spdlog/fmt,
BS thread pool, mathfun routines, nlohmann/json 3.11.2 (Niels Lohmann, MIT)
and half_float 2.2.0 (Christian Rau, MIT).
Their license and applicable bundled-program notices are in `licenses/`, along
with SentencePiece's absl, darts_clone, esaxx and protobuf-lite notices.
Exact publisher source URLs and file hashes are recorded in
`licenses/PROVENANCE.json`. These are third-party components, not Santa's MIT work.

Microsoft .NET, ASP.NET Core and Windows Desktop 10.0.12 license/third-party
notices are included separately. Vendor inclusion does not imply endorsement.

The sparse protocol-18 reader and bounded message stream use published wire
facts, with reference to LuluStudioX/AlbionPacketExplorer at commit
`faab74d7c70b0de78210be2f17e70573551405c6` (MIT, Copyright 2026 LuluStudioX).
Full notice: `LICENSE-AlbionPacketExplorer.txt`.
https://github.com/LuluStudioX/AlbionPacketExplorer/tree/faab74d7c70b0de78210be2f17e70573551405c6/libs/PhotonWire
Schema references, pins and evidence limits are recorded in the source document
`docs/DECODER-SOURCES.md`. No noncommercial application implementation is bundled.

- .NET / WPF / ASP.NET Core: Microsoft and contributors, MIT license and applicable
  third-party notices shipped with the self-contained .NET runtime.
  https://github.com/dotnet/runtime/blob/main/LICENSE.TXT
  https://github.com/dotnet/wpf/blob/main/LICENSE.TXT
  https://github.com/dotnet/aspnetcore/blob/main/LICENSE.txt
- SharpPcap 6.3.1: Tamir Gal, Chris Morgan, Ayoub Kaanich, Noah Potash, Phillip
  Lemon, Evan Plaice; MIT license. Full notice: `LICENSE-SharpPcap.txt`.
  Unmodified transitive PacketDotNet 1.4.8 is Mozilla Public License 2.0;
  full license: `LICENSE-PacketDotNet.txt`. Source corresponding to the
  redistributed assembly is available at https://github.com/dotpcap/packetnet/tree/v1.4.8.
  No PacketDotNet source files are modified by this application.
  https://github.com/dotpcap/sharppcap/tree/v6.3.1/LICENSES
  https://github.com/dotpcap/packetnet
- NSIS 3.12 installer runtime: zlib/libpng license; installer compiler includes
  separately licensed components. https://nsis.sourceforge.io/License

- py3langid 0.3.0: BSD-3-Clause license. Used offline for incoming chat language
  detection. The pinned wheel and embedded model are included in the installer;
  no runtime download is required. See `LANGUAGE-DETECTOR.json` and
  `licenses/LICENSE-py3langid.txt`.

The narrow Photon envelope inspector was implemented with reference to the public
Albion Data Project's `client/photon/parser.go` framing documentation and parser
tests. It does not copy the general-purpose deserializer or support encrypted
traffic. Source: https://github.com/ao-data/albiondata-client
That project's parser cites JPCodeCraft/AlbionDataAvalonia as an earlier framing
reference. The upstream code is MIT licensed; its notice follows for attribution:

MIT License

Copyright (c) 2017 The Albion Data Project

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
