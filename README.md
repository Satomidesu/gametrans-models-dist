# gametrans-models-dist

The files that the **gametrans** desktop app downloads. On first launch: screen text recognition,
and one English → X translation model chosen by the user (26 target languages). Users who turn on the optional **high-quality mode**
(Japanese, Chinese, Korean) also download a local AI translation model and the program that runs it (`llm-*.zip`).
The app goes online only for these downloads; the AI also runs only on the user's PC.

gametrans が落とすファイルの置き場です。初回起動で、文字認識の土台と、使う人が選んだ訳し先 1 つぶんの翻訳モデルだけを落とします。
高品質モード（日本語・中国語・韓国語）を入にした人だけが、AI の翻訳モデルとそれを動かす部品（`llm-*.zip`）も落とします。
アプリが通信するのはこの取得のときだけです。AI も PC の中だけで動きます。

- The files are the **release assets of tag `v1`** (one zip per bundle). The app pins every file by SHA-256; do not replace assets under the same tag.
- These are model files and, for the optional high-quality mode, the unmodified third-party llama.cpp runtime; no gametrans code is included. The gametrans application itself is a separate program under its own license and is not in this repository.
- No warranty. See each license text for the disclaimer.

## Licenses — several licenses in one repository

Every translation model in the table below (the `mt-*.zip` bundles) is a **modified work**; the optional high-quality mode model
further down is distributed unmodified. For each `mt-*.zip` model, gametrans made the same changes
(this is the notice of changes required by Apache-2.0 Section 4(b) and by CC BY / CC BY-SA Section 3(a)(1)(B)):

> Exported from the original weights to ONNX with Hugging Face Optimum (`encoder_model.onnx`, `decoder_model_merged.onnx`),
> quantized to int8 with ONNX Runtime dynamic quantization (including the `If` subgraphs), and stored the weights
> shared by the encoder and decoder once in `weights.bin` (duplicate tensors removed). For the HPLT v2.0 models
> (Korean, Turkish, Ukrainian, Thai, Vietnamese, Norwegian), the original Marian checkpoint was first rearranged into the
> Hugging Face transformers format; the HPLT v1.0 Arabic model was exported from the Hugging Face-format weights published
> in its repository. `source.spm` / `target.spm` are byte-identical to the original SentencePiece files (for HPLT models,
> copies of the original `model.en-xx.spm`); `vocab.json` and the `*config.json` files were re-written by the export tools.

No DRM or technical restriction is applied. You may copy and redistribute each model under its own license.

| Bundle (zip) | Target | Original model | Authors | License |
|---|---|---|---|---|
| `mt-fugumt-en-ja.zip` | Japanese | https://huggingface.co/staka/fugumt-en-ja | **Satoshi Takahashi** | **CC BY-SA 4.0** (`LICENSES/cc-by-sa-4.0.txt`). This modified version is distributed under the same license. |
| `mt-opus-en-ru.zip` | Russian | https://huggingface.co/Helsinki-NLP/opus-mt-en-ru | **Helsinki-NLP** (Language Technology Research Group, University of Helsinki; Jörg Tiedemann et al.) | Apache License 2.0 (`LICENSES/Apache-2.0.txt`) |
| `mt-opus-en-zh.zip` | Chinese (Simplified / Traditional) | https://huggingface.co/Helsinki-NLP/opus-mt-en-zh | **Helsinki-NLP** (Language Technology Research Group, University of Helsinki; Jörg Tiedemann et al.) | Apache License 2.0 (`LICENSES/Apache-2.0.txt`) |
| `mt-hplt-en-ko.zip` | Korean | https://huggingface.co/HPLT/translate-en-ko-v2.0-hplt_opus | the **HPLT project** (High Performance Language Technologies) | CC BY 4.0 (`LICENSES/cc-by-4.0.txt`) |
| `mt-opus-mt-en-de.zip` | German | https://huggingface.co/Helsinki-NLP/opus-mt-en-de | **Helsinki-NLP** (Language Technology Research Group, University of Helsinki; Jörg Tiedemann et al.) | CC BY 4.0 (`LICENSES/cc-by-4.0.txt`) |
| `mt-opus-mt-en-es.zip` | Spanish | https://huggingface.co/Helsinki-NLP/opus-mt-en-es | **Helsinki-NLP** (Language Technology Research Group, University of Helsinki; Jörg Tiedemann et al.) | Apache License 2.0 (`LICENSES/Apache-2.0.txt`) |
| `mt-opus-mt-en-ROMANCE-pt_BR.zip` | Portuguese (Brazil) | https://huggingface.co/Helsinki-NLP/opus-mt-en-ROMANCE | **Helsinki-NLP** (Language Technology Research Group, University of Helsinki; Jörg Tiedemann et al.) | Apache License 2.0 (`LICENSES/Apache-2.0.txt`) |
| `mt-opus-mt-en-fr.zip` | French | https://huggingface.co/Helsinki-NLP/opus-mt-en-fr | **Helsinki-NLP** (Language Technology Research Group, University of Helsinki; Jörg Tiedemann et al.) | Apache License 2.0 (`LICENSES/Apache-2.0.txt`) |
| `mt-opus-mt-en-zlw-pol.zip` | Polish | https://huggingface.co/Helsinki-NLP/opus-mt-en-zlw | **Helsinki-NLP** (Language Technology Research Group, University of Helsinki; Jörg Tiedemann et al.) | Apache License 2.0 (`LICENSES/Apache-2.0.txt`) |
| `mt-hplt-en-tr.zip` | Turkish | https://huggingface.co/HPLT/translate-en-tr-v2.0-hplt_opus | the **HPLT project** (High Performance Language Technologies) | CC BY 4.0 (`LICENSES/cc-by-4.0.txt`) |
| `mt-opus-mt-en-it.zip` | Italian | https://huggingface.co/Helsinki-NLP/opus-mt-en-it | **Helsinki-NLP** (Language Technology Research Group, University of Helsinki; Jörg Tiedemann et al.) | Apache License 2.0 (`LICENSES/Apache-2.0.txt`) |
| `mt-hplt-en-uk.zip` | Ukrainian | https://huggingface.co/HPLT/translate-en-uk-v2.0-hplt_opus | the **HPLT project** (High Performance Language Technologies) | CC BY 4.0 (`LICENSES/cc-by-4.0.txt`) |
| `mt-opus-mt-en-cs.zip` | Czech | https://huggingface.co/Helsinki-NLP/opus-mt-en-cs | **Helsinki-NLP** (Language Technology Research Group, University of Helsinki; Jörg Tiedemann et al.) | Apache License 2.0 (`LICENSES/Apache-2.0.txt`) |
| `mt-hplt-en-th.zip` | Thai | https://huggingface.co/HPLT/translate-en-th-v2.0-hplt | the **HPLT project** (High Performance Language Technologies) | CC BY 4.0 (`LICENSES/cc-by-4.0.txt`) |
| `mt-hplt-en-vi.zip` | Vietnamese | https://huggingface.co/HPLT/translate-en-vi-v2.0-hplt_opus | the **HPLT project** (High Performance Language Technologies) | CC BY 4.0 (`LICENSES/cc-by-4.0.txt`) |
| `mt-opus-mt-en-id.zip` | Indonesian | https://huggingface.co/Helsinki-NLP/opus-mt-en-id | **Helsinki-NLP** (Language Technology Research Group, University of Helsinki; Jörg Tiedemann et al.) | Apache License 2.0 (`LICENSES/Apache-2.0.txt`) |
| `mt-opus-mt-en-hu.zip` | Hungarian | https://huggingface.co/Helsinki-NLP/opus-mt-en-hu | **Helsinki-NLP** (Language Technology Research Group, University of Helsinki; Jörg Tiedemann et al.) | Apache License 2.0 (`LICENSES/Apache-2.0.txt`) |
| `mt-opus-mt-en-nl.zip` | Dutch | https://huggingface.co/Helsinki-NLP/opus-mt-en-nl | **Helsinki-NLP** (Language Technology Research Group, University of Helsinki; Jörg Tiedemann et al.) | Apache License 2.0 (`LICENSES/Apache-2.0.txt`) |
| `mt-opus-mt-en-sv.zip` | Swedish | https://huggingface.co/Helsinki-NLP/opus-mt-en-sv | **Helsinki-NLP** (Language Technology Research Group, University of Helsinki; Jörg Tiedemann et al.) | Apache License 2.0 (`LICENSES/Apache-2.0.txt`) |
| `mt-opus-mt-en-ro.zip` | Romanian | https://huggingface.co/Helsinki-NLP/opus-mt-en-ro | **Helsinki-NLP** (Language Technology Research Group, University of Helsinki; Jörg Tiedemann et al.) | Apache License 2.0 (`LICENSES/Apache-2.0.txt`) |
| `mt-opus-mt-en-el.zip` | Greek | https://huggingface.co/Helsinki-NLP/opus-mt-en-el | **Helsinki-NLP** (Language Technology Research Group, University of Helsinki; Jörg Tiedemann et al.) | Apache License 2.0 (`LICENSES/Apache-2.0.txt`) |
| `mt-opus-mt-en-bg.zip` | Bulgarian | https://huggingface.co/Helsinki-NLP/opus-mt-en-bg | **Helsinki-NLP** (Language Technology Research Group, University of Helsinki; Jörg Tiedemann et al.) | Apache License 2.0 (`LICENSES/Apache-2.0.txt`) |
| `mt-opus-mt-en-da.zip` | Danish | https://huggingface.co/Helsinki-NLP/opus-mt-en-da | **Helsinki-NLP** (Language Technology Research Group, University of Helsinki; Jörg Tiedemann et al.) | Apache License 2.0 (`LICENSES/Apache-2.0.txt`) |
| `mt-opus-mt-en-fi.zip` | Finnish | https://huggingface.co/Helsinki-NLP/opus-mt-en-fi | **Helsinki-NLP** (Language Technology Research Group, University of Helsinki; Jörg Tiedemann et al.) | Apache License 2.0 (`LICENSES/Apache-2.0.txt`) |
| `mt-hplt-en-nb.zip` | Norwegian (Bokmål) | https://huggingface.co/HPLT/translate-en-nb-v2.0-hplt | the **HPLT project** (High Performance Language Technologies) | CC BY 4.0 (`LICENSES/cc-by-4.0.txt`) |
| `mt-hplt-v1-en-ar.zip` | Arabic | https://huggingface.co/HPLT/translate-en-ar-v1.0-hplt_opus | the **HPLT project** (High Performance Language Technologies) | CC BY 4.0 (`LICENSES/cc-by-4.0.txt`) |

The English → Russian and English → Chinese bundles additionally had their separately stored output projection (`lm_head`)
replaced with a `Transpose` of the identical quantized token embedding; on a 442-sentence test set the output token sequences are identical before and after.

### Text recognition (`ocr-base.zip`) — Apache License 2.0, unmodified

PP-OCRv5 text detection / recognition models by PaddlePaddle / PaddleOCR (Baidu), ONNX versions by RapidAI / RapidOCR
(https://github.com/RapidAI/RapidOCR). Distributed unmodified under the Apache License 2.0 (`LICENSES/Apache-2.0.txt`):
`ocr/ch_PP-OCRv5_det_mobile.onnx` and `ocr/ch_PP-OCRv5_rec_mobile.onnx` are the files listed in RapidOCR v3.9.2
(`python/rapidocr/default_models.yaml`, from https://www.modelscope.cn/models/RapidAI/RapidOCR) and have the same SHA-256 as listed there.

### High-quality mode (optional) — `llm-hy-mt2-1.8b-q4km.zip`, `llm-runtime-b11624-r2.zip`

Downloaded only by users who turn on the high-quality mode (Japanese, Chinese, Korean). The model runs on the user's PC
as a separate process; nothing is sent over the network.

**`llm-hy-mt2-1.8b-q4km.zip` — Apache License 2.0, unmodified.** `llm/Hy-MT2-1.8B-Q4_K_M.gguf` is the file of the same name
from https://huggingface.co/tencent/Hy-MT2-1.8B-GGUF (revision `a0c709d9`) by **Tencent**, with the same size and SHA-256 as published there.
`llm/Hy-MT2-LICENSE.txt` is that repository's `LICENSE.txt` (Apache License 2.0, Copyright (C) 2026 Tencent), byte-identical. The repository has no NOTICE file.

**`llm-runtime-b11624-r2.zip` — MIT, with the bundled components below.** The files needed to run `llama-server`, taken from the official
llama.cpp release b11624 (https://github.com/ggml-org/llama.cpp/releases/tag/b11624, `llama-b11624-bin-win-vulkan-x64.zip`) by **the ggml authors**.
Changes: `llama-server.exe` is renamed to `gametrans-llm.exe`, `ggml-vulkan.dll` is moved to `vk/`, and `LICENSE-LLVM-OpenMP` is renamed to
`LICENSE-LLVM-OpenMP.txt`; all 24 files taken from the release are byte-identical to it, and files the app does not use are left out.
Six license texts were added: `LICENSE-llama.cpp.txt`, `LICENSE-cpp-httplib.txt`, `LICENSE-nlohmann-json.txt` and `LICENSE-BoringSSL.txt`,
and two notice files that gametrans assembled from the upstream license texts (`LICENSE-llama.cpp-third-party.txt`, `LICENSE-llama.cpp-webui.txt`),
because the official release ships only the LLVM OpenMP text.
The Microsoft Visual C++ runtime files are **not** in this zip; when Windows has no copies or only older ones, the gametrans app copies its own
installed copies into the folder.
The license texts are in the zip under `llm/runtime/` (copies are also in this repository under `LICENSES/llama.cpp-b11624/`):

| Component | License | File in the zip |
|---|---|---|
| llama.cpp / ggml (the ggml authors) | MIT | `LICENSE-llama.cpp.txt` |
| cpp-httplib (yhirose), built into llama-server | MIT | `LICENSE-cpp-httplib.txt` |
| nlohmann/json (Niels Lohmann), built into llama-server | MIT | `LICENSE-nlohmann-json.txt` |
| BoringSSL 0.20260929.0, built into `llama-server-impl.dll` and `llama-common.dll` | Apache License 2.0 | `LICENSE-BoringSSL.txt` |
| LLVM OpenMP (`libomp.dll`, as shipped in the llama.cpp release zip) | Apache License 2.0 WITH LLVM-exception | `LICENSE-LLVM-OpenMP.txt` |
| Other third-party code compiled into the DLLs: llamafile tinyBLAS (Mozilla), YaRN, FP16 (Maratyszcza), the UTF-8 decoder (Hoehrmann) and Grisu2 (Loitsch) inside nlohmann/json, ggllm.cpp, Pillow resampling, Unicode data tables, Vulkan-Headers (Khronos), rotate-bits, the C++ port of Hugging Face's Jinja engine, a Microsoft Learn code sample, plus precautionary entries | MIT, MIT-CMU, Unicode-3.0, Apache-2.0 OR MIT and others | `LICENSE-llama.cpp-third-party.txt` |
| The llama.cpp web UI compiled into `llama-server-impl.dll` (gametrans starts the server with `--no-webui`, so it is never shown): 388 entries: 365 npm packages, code embedded in them or copied into the UI source, and the KaTeX fonts | MIT, ISC, BSD, Apache-2.0, OFL-1.1 and others | `LICENSE-llama.cpp-webui.txt` |

`mtmd.dll` also contains miniaudio and stb_image, and `mtmd.dll` and `llama-common.dll` contain subprocess.h; they are used under their
public-domain option (Unlicense), so no notice is required (listed in Part C of `LICENSE-llama.cpp-third-party.txt`).

## Files and SHA-256

| File | For | Bytes | SHA-256 |
|---|---|---:|---|
| `ocr-base.zip` | text recognition (every language) | 21,451,180 | `522dec56b3d25f2566f401d0419d87859ce1e1197ca8bde8f91442053a95d444` |
| `mt-fugumt-en-ja.zip` | 日本語 | 81,089,012 | `00f1c2f24f5cdc8adfcca963d3b939dae6b2300e4e913b09e78400d149cb35a6` |
| `mt-opus-en-ru.zip` | Русский | 82,762,481 | `af1125ce7a629717453a5d0d3c976c30b975e7047a04ba0bd3a05568e92e246d` |
| `mt-opus-en-zh.zip` | 简体中文 / 繁體中文 | 82,796,222 | `9c3a6623e101652adf9d60c93f3817277d53c430515312d0ef0599bf46389ffd` |
| `mt-hplt-en-ko.zip` | 한국어 | 116,212,547 | `e7420261a870c64ff0b0b8fada2b7650bdfbfc05a002471ebb35df36f6da406a` |
| `mt-opus-mt-en-de.zip` | Deutsch | 108,511,121 | `fa60f1e9407138812f94d15cac4277122f716b556683da810db0b2b1a25ebb3a` |
| `mt-opus-mt-en-es.zip` | Español | 116,000,343 | `04c68e0b2bc5f3ed1dce35e3de1f31ef1a8d3f7637708affe409ee58da3026b3` |
| `mt-opus-mt-en-ROMANCE-pt_BR.zip` | Português (Brasil) | 115,818,733 | `48037bf4001c61bae85e94470c25adef9da4268e3307dba878f448be921f1247` |
| `mt-opus-mt-en-fr.zip` | Français | 110,051,992 | `fa63128ca4a7ae068ec95be70bb0c3e6a75f22065cea225c5685630d9ccb8702` |
| `mt-opus-mt-en-zlw-pol.zip` | Polski | 108,598,609 | `752b4afa033eeff15b54e0c47c811472e3ebc6f42a7bcd16c17054d537a5ffb3` |
| `mt-hplt-en-tr.zip` | Türkçe | 116,170,753 | `d4aaa05afc240d3f0902f6750152756cea37af5bcfbe22329eb8dd1a2657d99e` |
| `mt-opus-mt-en-it.zip` | Italiano | 132,222,708 | `09e39df2421c57f226f9e98e88cc932a51bbb82d5df88e4458b8ef04c6e3808b` |
| `mt-hplt-en-uk.zip` | Українська | 117,726,871 | `54af92994e9a1d64a05e275533a363c9ce980b6c63efa49d3321e6529fc46fca` |
| `mt-opus-mt-en-cs.zip` | Čeština | 113,430,332 | `97e21bcceac398d605ea4a8ae8a65ed1bcf4f0fbfaaf773802e0a8a46cb1bc20` |
| `mt-hplt-en-th.zip` | ไทย | 118,451,334 | `5fa053126acebedf5efc0e88dc0b344050a101420fd5e1d3c6bd3d23ea945cb1` |
| `mt-hplt-en-vi.zip` | Tiếng Việt | 115,799,641 | `6e4eeade3d61bb6bf35f5e94e732b95d797da0b55d14f82d28fe4e479cc547f5` |
| `mt-opus-mt-en-id.zip` | Bahasa Indonesia | 105,123,812 | `2d68c2a50adc8ee1bc430b8d027c6167decb2200c400a89d340589110ab71aa7` |
| `mt-opus-mt-en-hu.zip` | Magyar | 113,438,497 | `303478f92ca732f8cac7fe1f7efbde9d837d1ac192c51564066dae1d66e3531e` |
| `mt-opus-mt-en-nl.zip` | Nederlands | 118,132,611 | `16179567d32a20fbba78c70fe682e3200772beb2337b3a59f41d849600ba4860` |
| `mt-opus-mt-en-sv.zip` | Svenska | 106,856,480 | `0f41c60b0ede137d79edd01a5188c71d061bafc844c8a1d14eeb32026bc27289` |
| `mt-opus-mt-en-ro.zip` | Română | 110,156,844 | `d4e263da54e2db2e99ccb81e8831825db0cdf051ad0ca49efd25772ac6957546` |
| `mt-opus-mt-en-el.zip` | Ελληνικά | 116,871,020 | `01ff9e7e48810a74f08e5d4b195219e324a3da06815a4f7ce9910d4d483c0d59` |
| `mt-opus-mt-en-bg.zip` | Български | 113,508,535 | `f185a40a6774028a15cca57739c6b9c05f0a039fd8d5f886556b082d51e73370` |
| `mt-opus-mt-en-da.zip` | Dansk | 109,518,820 | `a57261a210933ca3db2c31e7af809f21570941e010997428e7f776b4e28adaa9` |
| `mt-opus-mt-en-fi.zip` | Suomi | 116,020,299 | `d7ded6206f6e8fa010e52a8d1fe2e0eb424febd9661d231045daa26bc6548001` |
| `mt-hplt-en-nb.zip` | Norsk bokmål | 115,996,337 | `2eade47235efc8e449cdb200cbd959d2760157bfe4627504044d234190dbe903` |
| `mt-hplt-v1-en-ar.zip` | العربية | 117,041,361 | `757c012ee9510266a02ebc6f672a11a4ec5317bd614112b70936499463e30708` |
| `llm-hy-mt2-1.8b-q4km.zip` | high-quality mode: AI model (optional) | 1,133,092,359 | `5eddc2d3fb8fe62ea6d54b601aed95e0d39a2b3b61cdf6082ca094d45c5623d0` |
| `llm-runtime-b11624-r2.zip` | high-quality mode: runtime (optional) | 86,667,784 | `64e00f2788190f110f8e59254ff9386116dfbeb19c7dbeeeedb4d628e4105105` |

29 files, 4,119,518,638 bytes in total. Each zip is uncompressed (stored) with fixed timestamps, so its size and bytes are
determined by the files inside; the app checks the zip size before reading it and the SHA-256 of every file after extracting it.

Download URL: `https://github.com/Satomidesu/gametrans-models-dist/releases/download/v1/<File>`
