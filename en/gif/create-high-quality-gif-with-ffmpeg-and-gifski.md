# Create a High-Quality GIF with ffmpeg and gifski

Today I learned how to make a **high-quality animated GIF** from a video using `ffmpeg` and `gifski`.  
This combination gives much better visual quality than most built-in converters.

## 1. Extract frames from the video

```zsh
ffmpeg -i path/to/input.mov -vf fps=10 path/to/output/frame_%03d.png
```

- `-i`: input video file
- `-vf fps=10`: extract 10 frames per second (adjust the FPS as needed)
- The output will be a sequence like `frame_001.png`, `frame_002.png`, etc.

> [!TIP]
>
>- Higher FPS = smoother animation, but larger file size
>- It’s best to output frames into a separate folder like frames/ to keep things tidy

## 2. Convert frames into a GIF with gifski

```zsh
gifski -o path/to/output/demo.gif path/to/output/frame_*.png
```

> [!NOTE]
>
> Why gifski?
>
>- Produces much better color dithering and gradients
>- Maintains more detail from the original video
>- Supports options like --fps and --quality for fine tuning
