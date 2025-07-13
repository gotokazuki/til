# 大規模な図を描く

PlantUML は画像の幅と高さを最大4096ピクセルに制限しています。
大規模な図を描きたい場合は、環境変数 `PLANTUML_LIMIT_SIZE` を使って制限を引き上げることができます。
設定方法は以下の通りです。

```zsh
# .zshrc に追記
export PLANTUML_LIMIT_SIZE=8192
```

VSCode の PlantUML 拡張機能を使っている場合は、設定ファイルに以下のように記述することも可能です。

```json
{
  "plantuml.commandArgs": [
    "-DPLANTUML_LIMIT_SIZE=8192"
  ]
}
```

> [!Note]
> 20,000 x 10,000 ピクセルを超えるような非常に大きな図の場合、メモリ不足の問題が発生することがあります。
> その際は、PlantUML 実行時に Java VM のメモリ割り当てを -Xmx オプション（例：-Xmx1024m）で増やすことを検討してください。
