
Choose the right LLM model.

## Model info

### parameter_size: 1.7B

Parameters = the "knobs" the model learned during training. More knobs = more knowledge/capability, but also more RAM and slower.

| Size | RAM Needed (rough) | Vibe |
| ------- | ------------------ | ---------------------------------------------------------- |
| 1B–3B | 1–3 GB | Tiny, fast, dumb-ish. Fine for autocomplete, simple tasks. |
| 7B–8B | 5–8 GB | The "sweet spot" for laptops. |
| 13B–30B | 10–25 GB | Smarter, needs a good GPU or lots of RAM. |
| 70B+ | 40+ GB | Serious hardware territory. |
| 400B+ | Data center | GPT-4 / Claude class. |

So 1.7B = small and fast, runs on pretty much anything, but won’t be winning any IQ contests.

### quantization_level: Q8_0

This is a compression trick. Originally each parameter is a 32-bit or 16-bit float (fancy decimal number). Quantization rounds them to smaller integers to save space.

Think JPEG for model weights — lose a little quality, save a lot of size.

Common levels (smaller number = more compressed = worse quality but faster/smaller):

| Quant | Bits/weight | Quality | File size (for 1.7B) |
| ------ | ----------- | ----------------------- | -------------------- |
| F16 | 16 | Original-ish | ~3.4 GB |
| Q8_0 | 8 | Nearly identical to F16 | ~1.8 GB |
| Q6_K | ~6 | Very good | ~1.4 GB |
| Q5_K_M | ~5 | Good | ~1.2 GB |
| Q4_K_M | ~4 | Decent, most popular | ~1.0 GB |
| Q2_K | ~2 | Noticeably dumber | ~0.7 GB |

Q8_0 is basically "lossless-ish" — about half the size of the original with almost no quality drop. Good default for small models where you’ve got the RAM to spare.

---

## Voice

or an old CPU, the levers that actually reduce the heaviness are model-side, and they're cheaper to try than any code change:  

1. Quantized Kokoro — you're on Kokoro-82M-v1.0-ONNX-fp16; speaches also serves the int8-quantized ONNX variant, which is markedly faster on old CPUs for a small quality cost. That's just a TTS_MODEL env change and a model download — no code at all.

2. A lighter engine entirely — piper-class models are far lighter than Kokoro if speaches' catalogue reaches them, at a real quality cost.

3. Making sure speaches gets all its cores (its ONNX runtime thread settings), since laptops often end up throttled.

My recommendation: try the int8 model first and see if the pain disappears/