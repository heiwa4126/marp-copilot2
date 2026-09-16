# marp-copilot2

- [toku345/marp-slides: Marp を使用したスライド作成・管理プロジェクト](https://github.com/toku345/marp-slides)

が Claude Code on VSCode で動いたので
([heiwa4126/marp-claude1](https://github.com/heiwa4126/marp-claude1))、

それを clone して GitHub Copilot で動くかテスト。
そこそこ動く。

## 完成品

[slides/github-copilot-vscode.md](slides/github-copilot-vscode.md)

## 準備

クローン後

```sh
bun ci
rm -rf slides
```

GitHub Copilot に

`使える skills と subagent を列挙して`

と聞いて、 Types に

- Skills
  - creating-marp-slides - Marp スライドの作成・修正・レビュー、HTML/PDF/PPTX 出力
- Subagent
  - slide-builder - スライドビルド・PDF/HTML/PPTX 出力
  - slide-creator - 新しい Marp スライドの作成
  - slide-reviewer - スライドのレビュー・表示崩れ検出

があるのを確認。

さらに
`/creating-marp-slide`
を聞く (動作確認。たぶん自動で読む)。

## 作成

で、
`VSCode 上の GitHub Copilot について8ページのスライドを作成して`
で出来たのが
[slides/github-copilot-vscode.md](slides/github-copilot-vscode.md)

さらに

```sh
bun run build
```

で `dist/` の下に HTML と PDF ができる。

```sh
bun run build:pptx
```

で `dist/` の下に画像はりつけタイプの PowerPoint もできる(編集不可)。
