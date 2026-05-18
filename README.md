# ai-models

Public hosting for large on-device model files used by [SenseForge](https://github.com/rcmendes/senseforge).

Files are published as [GitHub Releases](https://github.com/rcmendes/ai-models/releases) (not committed to git). The app downloads from:

`https://github.com/rcmendes/ai-models/releases/download/language-models-v1/<asset>`

## Assets (language-models-v1)

| Asset | Tier |
|-------|------|
| `android-low-qwen2.5-0.5b-q8.task` | Android low |
| `android-mid-phi4-mini-q8.task.part00/01` | Android mid |
| `android-high-gemma4-e2b-web.task.part00/01` | Android high |
| `ios-low-qwen2.5-0.5b-4bit.zip` | iOS low |
| `ios-mid-qwen3-4b-4bit.zip` | iOS mid |
| `ios-high-gemma4-e2b-coreml.zip.part00/01` | iOS high (Gemma 4 E2B CoreML) |

## Maintainer

Re-publish from the SenseForge repo (builds from Hugging Face, uploads here):

```bash
cd /path/to/senseforge
./tool/publish_language_model_mirrors.sh --upload
```

Or copy an existing private release:

```bash
gh release download language-models-v1 --repo rcmendes/senseforge -D /tmp/lm-assets
gh release create language-models-v1 --repo rcmendes/ai-models \
  --title "On-device language models v1" \
  /tmp/lm-assets/*
```
