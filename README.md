# Neural Sound Synthesis · Part 10 — Language-Model Music Generation

The tenth part of the [Neural Sound Synthesis](https://github.com/BrendanJamesLynskey/Neural_Sound_Synthesis) series. Once a neural codec turns audio into discrete tokens, a transformer can model sound exactly like text — next-token prediction, cross-entropy, temperature sampling, classifier-free guidance. This part traces that idea through AudioLM's semantic/acoustic hierarchy, MusicLM's text conditioning, MusicGen's codebook-interleaving trick, and the Jukebox and VALL-E extremes.

### [Launch App](https://brendanjameslynskey.github.io/Neural_Sound_Synthesis_10_LM_Music_Generation/)

Part of the [DSP & Music](https://github.com/BrendanJamesLynskey/DSP_and_Music) collection.

---

## What's inside

| Section | Content |
|---------|---------|
| **Audio as a Language** | The paradigm: codec tokens → transformer, the autoregressive factorisation, cross-entropy training, the two-stage tax |
| **Sampling** | Temperature, top-k / top-p, classifier-free guidance — with a **live autoregressive melody generator** you play |
| **AudioLM** | Semantic (w2v-BERT) + acoustic (SoundStream RVQ) hierarchy, coarse-to-fine — with an **interactive token-stack explorer** |
| **MusicLM** | Text-to-music via MuLan text–audio embeddings, the conditioning cascade, MusicCaps |
| **MusicGen** | A single transformer over EnCodec's parallel codebooks — with a **flatten/parallel/delay interleaving stepper** |
| **Jukebox & VALL-E** | The raw-audio ancestor with lyrics, and the zero-shot voice-cloning speech cousin |
| **Timeline** | 2020 (Jukebox) → 2023 (MusicGen), cross-linked to Parts 9 and 11 |

## Live demos (all synthesised in-browser, no audio files)

1. **Transformer-over-tokens melody generator** — a real autoregressive next-token sampler over a musical token vocabulary (scale pitches + rest + sustain). Learns a bigram transition table from built-in seed melodies and samples a new tune token-by-token with a temperature slider (greedy → creative → random). Shows the token stream and a piano-roll, and plays the result.
2. **Semantic + acoustic hierarchy explorer** — AudioLM's two-stage stack: coarse semantic tokens generated first, then acoustic RVQ levels coarse-to-fine. Hover any cell to see what that level carries; animate the generation order.
3. **Codebook interleaving patterns** — MusicGen's flatten vs parallel vs delay schedules for K parallel RVQ codebook streams under one transformer. Step through decoding time and watch which codebook tokens are predicted when, and how the total step count changes.

## Technology

Single-file HTML/CSS/JS · Web Audio API · HTML5 Canvas · KaTeX · Palatino + Lucida Console · No external dependencies · No build step
