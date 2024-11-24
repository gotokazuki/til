# Draw A Large Scale Diagram

PlantUML restricts image width and height to 4096 pixels. If you want to draw a large scale diagram, you can use the environment variable `PLANTUML_LIMIT_SIZE` to increase the limit.
Here's how you can set it:

```zsh
# add in .zshrc
export PLANTUML_LIMIT_SIZE=8192
```

If you use vscode-plantuml extension, you can also set it in the settings.

```json
{
  "plantuml.commandArgs": [
    "-DPLANTUML_LIMIT_SIZE=8192"
  ]
}
```

> [!Note]
> For exceptionally large diagrams (e.g., over 20,000 x 10,000 pixels), you may encounter memory issues.
> In such cases, consider increasing the Java VM’s memory allocation by using the -Xmx option (e.g., -Xmx1024m) when running PlantUML.
