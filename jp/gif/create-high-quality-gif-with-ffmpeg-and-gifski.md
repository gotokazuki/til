# 高画質な GIF を ffmpeg と gifski で作る

今日は、`ffmpeg` と `gifski` を使って動画から **高画質なアニメーション GIF** を作る方法を学びました。  
この組み合わせは、一般的な変換ツールよりもずっときれいな画質を実現できます。

## 1. 動画をフレーム画像に分解する

```zsh
ffmpeg -i path/to/input.mov -vf fps=10 path/to/output/frame_%03d.png
```

- `-i`: 入力動画ファイル
- `-vf fps=10`: 1 秒あたり 10 フレームを抽出（必要に応じて FPS を調整）
- 出力は `frame_001.png`, `frame_002.png` のような連番ファイルになります

> [!TIP]
>
>- FPS を上げると滑らかになりますが、ファイルサイズも大きくなります
>- 一時ファイルは `frames/` のような専用フォルダに出力すると整理しやすいです

## 2. gifski で GIF に変換する

```zsh
gifski -o path/to/output/demo.gif path/to/output/frame_*.png
```

> [!NOTE]
>
> **なぜ gifski?**
>
>- 色のディザリングやグラデーションが非常に自然できれい
>- 元動画のディテールをより多く保持できる
>- `--fps` や `--quality` オプションで微調整可能
