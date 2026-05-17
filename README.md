# ai-models

Public hosting for large on-device model files used by [SenseForge](https://github.com/rcmendes/senseforge).

Files are published as [GitHub Releases](https://github.com/rcmendes/ai-models/releases) (not committed to git). The app downloads from:

`https://github.com/rcmendes/ai-models/releases/download/language-models-v1/<asset>`

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
