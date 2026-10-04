# MealWise models

Public model downloads for MealWise. Model weights are distributed as GitHub
Release assets; they are not stored in Git.

## Food extractor v1

This model extracts food names, quantities, and units from a meal description.
It is a MealWise LoRA fine-tune of
[Qwen2.5-0.5B-Instruct](https://huggingface.co/Qwen/Qwen2.5-0.5B-Instruct),
fused from the selected step-1000 adapter and converted to Q4_K_M GGUF with
llama.cpp b10516. Nutrition values are resolved separately by the app.

- File: `mealwise-qwen2.5-0.5b-instruct-q4_k_m.gguf`
- Size: 397,807,456 bytes (about 379 MiB)
- SHA-256: `4cff339c4ed40d6e00742c46c34939d08b62f845c70faf4c4ed1e512b34b27e9`
- [Download model](https://github.com/AniketIndulkar/mealwise-models/releases/download/food-extractor-v1/mealwise-qwen2.5-0.5b-instruct-q4_k_m.gguf)
- [Release and attribution files](https://github.com/AniketIndulkar/mealwise-models/releases/tag/food-extractor-v1)

## App configuration

Set the MealWise repository Actions variable `MEALWISE_MODEL_URL` to:

```text
https://github.com/AniketIndulkar/mealwise-models/releases/download/food-extractor-v1/mealwise-qwen2.5-0.5b-instruct-q4_k_m.gguf
```

For local Flutter builds, pass
`--dart-define=MEALWISE_MODEL_URL=<the URL above>`.
The app validates the exact file size and SHA-256 before installation.

Use the versioned URL above rather than a mutable latest-release URL. A future
model version requires a new release and matching app checksum configuration.

## Verification

Download the model and `SHA256SUMS` from the release, then run:

```bash
shasum -a 256 -c SHA256SUMS
```

Food extraction can be incorrect. MealWise keeps extracted meals available for
user review; this model is not a source of nutrition measurements.

## License and attribution

The Qwen base model is copyright 2024 Alibaba Cloud and licensed under
Apache-2.0. MealWise's model modifications (LoRA fine-tuning, fusion, and GGUF
quantization) are distributed under Apache-2.0 as well.
See [LICENSE](LICENSE) and [NOTICE](NOTICE).
The repository contains model distribution metadata and release assets.
