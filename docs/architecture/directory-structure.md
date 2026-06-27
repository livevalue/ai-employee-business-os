# Directory Structure

この構成は、申請のための見せ方ではなく、実務で継続開発するための設計です。

## Design Logic

中小企業のAI活用で必要なのは、単発のプロンプトではなく、次の構成要素です。

| Layer | Purpose | Directory |
|---|---|---|
| Context | 課題、対象者、思想をそろえる | `docs/principles/` |
| Templates | 実務で使う型を提供する | `templates/` |
| Examples | 業種別に応用例を示す | `examples/` |
| Application | OSS支援や外部説明に使う | `docs/application/` |
| Agent Rules | CodexやClaude Codeの出力を安定させる | `AGENTS.md` |

## Why Markdown

Markdownは、AIエージェント、人間の共同編集、GitHubでのレビュー、ドキュメント生成に向いています。

- 差分が読みやすい
- GitHub上でそのまま読める
- Claude Code / Codex が扱いやすい
- HTML、PDF、提案書へ変換しやすい
- 非エンジニアにも編集しやすい

