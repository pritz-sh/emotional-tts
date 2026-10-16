## Notebooks

| Notebook | What it does |
|---|---|
| `notebooks/styletts2_lite_emo.ipynb` | Two-stage TTS training (Stage 1: LJSpeech, Stage 2: ESD fine-tune with LJSpeech replay) and emotion-conditioned synthesis |
| `notebooks/text_emotion_classifier_comparison.ipynb` | Trains and benchmarks three text emotion classifiers, then exports `clf_last.pt` for the TTS notebook |

## Quick start

Both notebooks are designed for Google Colab with a GPU runtime.

1. Open a notebook in Colab (or locally with Jupyter).
2. Run the first cell to install dependencies (`espeak-ng` is needed for phonemization in the TTS notebook).
3. For the TTS notebook, set `STAGE = 1` and then `STAGE = 2`. Stage 2 downloads ESD from Kaggle, so you'll need a `kaggle.json` token.
4. Run the classifier notebook, then copy the exported `clf_last.pt` into the TTS checkpoint folder.

## Datasets

- [LJSpeech](https://keithito.com/LJ-Speech-Dataset/): neutral single-speaker speech
- [ESD](https://hltsingapore.github.io/ESD/): emotional speech, English speakers 0011-0020
- [RAVDESS](https://zenodo.org/records/1188976): optional extra emotions (calm, fearful, disgust)
- [GoEmotions](https://huggingface.co/datasets/google-research-datasets/go_emotions): text emotion labels

## Notes

- Model checkpoints and cached features are not included. They're saved to Google Drive during training.
- Dependencies are listed in `requirements.txt`.

## License

MIT. See `LICENSE`. Datasets keep their own licenses.
