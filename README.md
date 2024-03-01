## Requirements

```
python > 3.9
py -3.10 -m venv ./env 
```
## Installation

Download
ffmpeg-6.1.1-full_build.7z (解壓縮至 C:\Program Files 並加入環境變數中)
- 檢查是否安裝成功：`ffmpeg -version`

- https://www.gyan.dev/ffmpeg/builds/ffmpeg-release-github

安裝OpenAI-whisper
```
pip install -U openai-whisper
```
## Available models and languages

There are five model sizes, four with English-only versions, offering speed and accuracy tradeoffs. Below are the names of the available models and their approximate memory requirements and inference speed relative to the large model; actual speed may vary depending on many factors including the available hardware.

|  Size  | Parameters | English-only model | Multilingual model | Required VRAM | Relative speed |
|:------:|:----------:|:------------------:|:------------------:|:-------------:|:--------------:|
|  tiny  |    39 M    |     `tiny.en`      |       `tiny`       |     ~1 GB     |      ~32x      |
|  base  |    74 M    |     `base.en`      |       `base`       |     ~1 GB     |      ~16x      |
| small  |   244 M    |     `small.en`     |      `small`       |     ~2 GB     |      ~6x       |
| medium |   769 M    |    `medium.en`     |      `medium`      |     ~5 GB     |      ~2x       |
| large  |   1550 M   |        N/A         |      `large`       |    ~10 GB     |       1x       |


## Command-line usage
The following command will transcribe speech in audio files
```
whisper audio.flac or .mp3 or .wav --language zh --model large --device cpu
```

OUTPUT DIR 輸出資料夾設定
``` 
--output_dir OUTPUT_DIR, -o OUTPUT_DIR
```

OUTPUT FORMAT 輸出檔案格式設定
```
--output_format {txt,vtt,srt,tsv,json,all}, -f {txt,vtt,srt,tsv,json,all}
```
language 輸出中文問題
```
--initial_prompt "此為繁體中文的句子"  # traditional
--initial_prompt "此为简体中文的句子"  # simplified
```

