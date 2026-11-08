# License notices

This repository holds no code or data of its own: its release v1 redistributes two upstream archives, unchanged. Below is what each license asks of someone who redistributes these files, and how this repository does it.

This repository only redistributes; the files are provided as-is under their own licenses.

## sherpa-onnx runtime: Apache License 2.0

`sherpa-onnx-v1.13.8-win-x64-shared-MT-Release-no-tts.tar.bz2` is a binary release of sherpa-onnx, https://github.com/k2-fsa/sherpa-onnx (Copyright (c) 2023 Xiaomi Corporation (sherpa-onnx/c-api/c-api.h), and the sherpa-onnx authors), licensed under the Apache License, Version 2.0. It is redistributed as published at https://github.com/k2-fsa/sherpa-onnx/releases/tag/v1.13.8.

Section 4 of the license, point by point:

- **4(a), a copy of the license goes with the work:** [licenses/sherpa-onnx-LICENSE.txt](licenses/sherpa-onnx-LICENSE.txt) is sherpa-onnx's own LICENSE file, as of tag v1.13.8.
- **4(b), modified files say so:** no file has been modified; the archive is the upstream file, byte for byte.
- **4(c), the work's own notices are kept:** all of them, since nothing inside the archive has been changed.
- **4(d), NOTICE:** the sherpa-onnx repository has no NOTICE file at its root (checked at tag v1.13.8), so there are no NOTICE attributions to pass on; any notice files inside the archive are passed on unchanged.

### ONNX Runtime: MIT License

The runtime archive includes `onnxruntime.dll` from ONNX Runtime, https://github.com/microsoft/onnxruntime (Copyright (c) Microsoft Corporation), under the MIT License. The license asks that its copyright notice and permission notice go with all copies; they are in [licenses/onnxruntime-LICENSE.txt](licenses/onnxruntime-LICENSE.txt).

## Parakeet TDT 0.6B v2 model: CC BY 4.0

`sherpa-onnx-nemo-parakeet-tdt-0.6b-v2-int8.tar.bz2` is NVIDIA's Parakeet TDT 0.6B v2 English speech recognition model, as converted to ONNX and quantized to int8 by the sherpa-onnx project, under the Creative Commons Attribution 4.0 International Public License (CC BY 4.0). Section 3(a) of that license asks a redistributor to keep the following with the material:

- **Creator:** NVIDIA. Model: Parakeet TDT 0.6B v2 (parakeet-tdt-0.6b-v2).
- **The material:** https://huggingface.co/nvidia/parakeet-tdt-0.6b-v2
- **License:** CC BY 4.0, https://creativecommons.org/licenses/by/4.0/legalcode.en. As the model card says: "GOVERNING TERMS: Use of this model is governed by the CC-BY-4.0 license."
- **Disclaimer:** the model is provided by NVIDIA "as is", with no warranties of any kind, as section 5 of the license sets out.
- **Changes:** the sherpa-onnx project (k2-fsa) converted NVIDIA's model to ONNX and quantized it to int8, and published the package at https://github.com/k2-fsa/sherpa-onnx/releases/tag/asr-models; its five files are also at https://huggingface.co/csukuangfj/sherpa-onnx-nemo-parakeet-tdt-0.6b-v2-int8/tree/1ab9323565ddb038682214b292f588070a538ce2. This repository makes no further change.
