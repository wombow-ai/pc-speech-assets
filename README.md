# pc-speech-assets

Byte-exact copies of the two files that the voice feature of Wombow for Windows downloads:

- the **sherpa-onnx v1.13.8** speech recognition runtime for Windows x64, and
- NVIDIA's **Parakeet TDT 0.6B v2** English speech recognition model, as converted to ONNX and quantized to int8 by the sherpa-onnx project.

They are the assets of release [set-1](https://github.com/wombow-ai/pc-speech-assets/releases/tag/set-1). This is not an official release of the sherpa-onnx project or of NVIDIA; for anything other than these exact files, use the upstream projects linked below.

## What this is for

Wombow for Windows downloads these two files once, when a player turns on voice. Its primary source is Wombow's mirror at `https://cdn.wombow.com/pc-speech/`. This release is the fallback source, for the versions of the app that list it, used when the mirror cannot be reached.

## Why it exists

The app pins each file by its size and SHA-256, and refuses a file that does not match them, wherever it came from.

The sherpa-onnx project publishes its models on a rolling release, `asr-models`, where a model that is exported again is uploaded under the same name and replaces the earlier file. That happened to the Parakeet package on 2026-11-07 at 05:47 UTC: the file at that address is now a new export with different bytes (482,440,461 bytes, SHA-256 `6fc4426b54aa549a0019b8a75b8dea59164e71790a37ac56a045ad57f915f714`), which an app pinned to the earlier file cannot accept.

The files here are byte for byte the ones the app pins. This repository has immutable releases turned on: once set-1 is published, its assets cannot be modified or deleted and its tag cannot be moved, so these bytes will not change.

## Files

| File | Bytes | SHA-256 |
|---|---:|---|
| `sherpa-onnx-v1.13.8-win-x64-shared-MT-Release-no-tts.tar.bz2` | 23,271,851 | `4b0a94f7b5c606b1b64a19a831c2127559e4b3d34e195465ebc7be73d9ed4783` |
| `sherpa-onnx-nemo-parakeet-tdt-0.6b-v2-int8.tar.bz2` | 482,468,385 | `157c157bc51155e03e37d2466522a3a737dd9c72bb25f36eb18912964161e1ad` |

Download:

- https://github.com/wombow-ai/pc-speech-assets/releases/download/set-1/sherpa-onnx-v1.13.8-win-x64-shared-MT-Release-no-tts.tar.bz2
- https://github.com/wombow-ai/pc-speech-assets/releases/download/set-1/sherpa-onnx-nemo-parakeet-tdt-0.6b-v2-int8.tar.bz2

To check them, run one of these in the folder you downloaded them to, with [SHA256SUMS](SHA256SUMS) beside them: `sha256sum -c SHA256SUMS` (Linux), `shasum -a 256 -c SHA256SUMS` (macOS), or `Get-FileHash -Algorithm SHA256 <file>` (Windows PowerShell).

### Where they come from

**Runtime.** `sherpa-onnx-v1.13.8-win-x64-shared-MT-Release-no-tts.tar.bz2` is the file of that name in the sherpa-onnx release v1.13.8, https://github.com/k2-fsa/sherpa-onnx/releases/tag/v1.13.8. The file there is unchanged: GitHub's SHA-256 digest of it is the one above.

**Model.** `sherpa-onnx-nemo-parakeet-tdt-0.6b-v2-int8.tar.bz2` is the file of that name as the sherpa-onnx release asr-models, https://github.com/k2-fsa/sherpa-onnx/releases/tag/asr-models, published it until it was replaced on 2026-11-07 (see above). The five files inside it are the same, byte for byte, as the files of those names in the Hugging Face repository csukuangfj/sherpa-onnx-nemo-parakeet-tdt-0.6b-v2-int8 at commit 1ab9323565ddb038682214b292f588070a538ce2: https://huggingface.co/csukuangfj/sherpa-onnx-nemo-parakeet-tdt-0.6b-v2-int8/tree/1ab9323565ddb038682214b292f588070a538ce2. The original model is NVIDIA's: https://huggingface.co/nvidia/parakeet-tdt-0.6b-v2.

## Licenses and attribution

This repository only redistributes; the files are provided as-is under their own licenses. No file has been modified: each archive is the upstream file, byte for byte, including any license or notice files inside it.

- **sherpa-onnx**, https://github.com/k2-fsa/sherpa-onnx, by the k2-fsa project. Copyright (c) 2023 Xiaomi Corporation (sherpa-onnx/c-api/c-api.h), and the sherpa-onnx authors. Licensed under the Apache License, Version 2.0: [licenses/sherpa-onnx-LICENSE.txt](licenses/sherpa-onnx-LICENSE.txt), sherpa-onnx's own LICENSE file at tag v1.13.8.
- **ONNX Runtime** (`onnxruntime.dll`, inside the runtime archive), https://github.com/microsoft/onnxruntime. Copyright (c) Microsoft Corporation. MIT License: [licenses/onnxruntime-LICENSE.txt](licenses/onnxruntime-LICENSE.txt).
- **Parakeet TDT 0.6B v2** (parakeet-tdt-0.6b-v2), by NVIDIA, https://huggingface.co/nvidia/parakeet-tdt-0.6b-v2. Licensed under the Creative Commons Attribution 4.0 International license (CC BY 4.0), https://creativecommons.org/licenses/by/4.0/legalcode.en. Changes: the sherpa-onnx project converted NVIDIA's model to ONNX and quantized it to int8; this repository redistributes that package without further change. The model is provided by NVIDIA "as is", with no warranties of any kind, as section 5 of the license sets out.

What each license asks of a redistributor, and how this repository meets it: [LICENSE-NOTICES.md](LICENSE-NOTICES.md).
