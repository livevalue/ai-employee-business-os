# AI Employee Business OS

中小企業や1人事業者が、人手不足・属人化・対応遅れに対して、AIを単発利用で終わらせず、業務を分解し、人とAIの役割を決め、継続運用できる形に落とし込むためのオープンソース業務OSです。

This repository provides practical Markdown templates and operating structures for designing human-in-the-loop AI employee workflows for small businesses, solo professionals, and local service providers.

## Who This Is For

このOSSは、AIに詳しい人だけのためのものではありません。むしろ、現場の業務を抱えながら「どこからAIを使えばよいかわからない」人のために作ります。

| User | Situation | First outcome |
|---|---|---|
| 中小企業の経営者 | 採用できず、既存メンバーに業務が集中している | AIに任せられる作業と、人が見るべき判断を分ける |
| 1人社労士 | 問い合わせ、文書作成、顧問先対応が重い | 問い合わせ整理AI、FAQ下書きAI、面談メモAIを設計する |
| Web / AI支援者 | 顧客にAI導入を提案したいが、業務設計が曖昧 | ヒアリングから運用フローまでをテンプレート化する |
| 小規模チーム | 業務が人の頭の中にあり、引き継げない | 業務をMarkdownで可視化し、改善できる状態にする |

## Why This Exists

中小企業の人手不足は、単に「人が足りない」だけではありません。多くの場合、次の問題が重なっています。

- 業務が分解されていない
- 判断基準が人の経験に閉じている
- FAQ、手順、顧客対応履歴が散らばっている
- AIを試しても、業務フローに組み込めていない
- 人が確認すべきところまでAIに任せようとして不安になる
- Web、LINE、WordPress、メール、社内業務がつながっていない

このプロジェクトは、AI導入を目的にしません。

目的は、限られた人が本来の判断、提案、関係構築に集中できるように、AIが担える処理・作業・下書き・確認補助を業務フローに組み込むことです。

## Market-In Logic

技術からではなく、現場の困りごとから逆算します。

| Market pain | Root cause | Required design | Repository component |
|---|---|---|---|
| 人手が足りない | 作業が担当者に集中している | 業務を作業単位に分解する | `templates/task-decomposition.md` |
| AIを使いこなせない | 何を任せるかが曖昧 | AI社員の役割を定義する | `templates/ai-employee-role-card.md` |
| AI利用が不安 | 責任境界が曖昧 | 人間レビューの基準を決める | `templates/human-ai-boundary.md` |
| 業務改善が続かない | 運用ログがない | 改善前提のフローにする | `templates/workflow-design.md` |
| ヒアリングが浅い | 現場情報が不足している | 入力情報を標準化する | `templates/business-hearing-sheet.md` |
| 属人化している | 知識が文書化されていない | Markdownで共有可能にする | `docs/architecture/` |

## Core Concept

AI社員とは、人間の代わりに責任を負う存在ではありません。

このOSSでは、AI社員を次のように定義します。

> 業務の中にある整理、分類、要約、下書き、確認補助、一次対応、記録、改善案生成を担い、人間の判断と価値提供を支える業務ロール。

### AIが担うこと

- 情報整理
- 問い合わせ分類
- 要約
- 文書の下書き
- FAQ案の作成
- 不足情報の洗い出し
- チェックリスト作成
- 改善案の生成

### 人が担うこと

- 最終判断
- 例外対応
- 顧客との信頼形成
- 法的、倫理的、契約的な責任
- 金額、条件、方針の決定
- 顧客に送る最終文面の承認

## Quick Start: 30分で1業務をAI社員化する

最初から全社DXを目指さず、1つの小さな業務を対象にします。おすすめは、問い合わせ対応、面談メモ整理、FAQ下書き、Webページ改善案の作成です。

### Step 1: 業務を1つ選ぶ

次の条件に当てはまる業務を選びます。

- 毎週または毎日発生する
- 文章処理が多い
- 判断基準を説明できる
- 過去の資料、FAQ、履歴がある
- 最終確認を人間ができる

例:

- 顧問先からの問い合わせを整理する
- Webフォームから来た相談内容を分類する
- 面談メモから次回対応を洗い出す
- よくある質問からFAQ案を作る

### Step 2: 現状をヒアリングする

`templates/business-hearing-sheet.md` を使い、次を埋めます。

- 誰が担当しているか
- どのくらい時間がかかっているか
- どこでミスや抜け漏れが起きるか
- どの情報を見て判断しているか
- AIに下書きしてほしいものは何か
- 人間が必ず確認するべきところはどこか

ここで大事なのは、AIにいきなり答えを出させることではありません。AIに渡す前に、現場の文脈を取り出すことです。

### Step 3: 業務を作業単位に分解する

`templates/task-decomposition.md` を使い、業務を次の単位に分けます。

| Work type | Example | AI fit |
|---|---|---|
| 情報収集 | 問い合わせ本文、過去FAQ、顧客情報を集める | High |
| 分類 | 内容を「手続き」「相談」「見積」「クレーム」に分ける | High |
| 要約 | 問い合わせの要点を3行にまとめる | High |
| 下書き | 回答案、確認事項、次アクションを作る | High |
| チェック | 不足情報、リスク、確認点を洗い出す | Medium |
| 判断 | 回答方針、契約条件、法的判断を決める | Human |

AI化する対象は、職種ではなく作業です。ここを分けると、AI導入が一気に現実的になります。

### Step 4: 人とAIの責任境界を決める

`templates/human-ai-boundary.md` を使い、次を明確にします。

- AIが作ってよいもの
- AIが判断してはいけないもの
- 人間レビューが必須のもの
- 顧客に送る前の確認項目
- 個人情報や機密情報の扱い

基本ルール:

- AIは下書きまで
- 顧客送信前に人間が確認する
- 法的、契約的、金額的な判断は人間が行う
- 例外対応や感情対応は人間が責任を持つ

### Step 5: AI社員ロールカードを作る

`templates/ai-employee-role-card.md` を使い、AI社員を曖昧な便利ツールではなく、1つの業務ロールとして定義します。

例:

```md
Role Name: 問い合わせ一次整理AI社員

Purpose:
顧問先や見込み客からの問い合わせを分類、要約し、回答下書きと確認事項を作る。

Inputs:
- 問い合わせ本文
- サービス説明
- FAQ
- 過去の回答例
- 顧客メモ

AI Tasks:
- 問い合わせ分類
- 要点整理
- 不足情報の洗い出し
- 回答案の下書き
- 人間レビュー用チェックリスト作成

Human Tasks:
- 最終回答
- 法的判断
- 契約条件の判断
- 顧客感情への配慮
```

### Step 6: ワークフローに落とす

`templates/workflow-design.md` を使い、実際の運用手順にします。

| Step | Actor | Action | Output | Review |
|---|---|---|---|---|
| 1 | Human | 問い合わせを受け取る | 原文 |  |
| 2 | AI | 要点、分類、不足情報を整理 | Summary | Human |
| 3 | AI | 回答案を下書き | Draft | Human |
| 4 | Human | 内容、責任境界、表現を確認 | Final response | Owner |
| 5 | Human / AI | 改善ログを残す | Improvement log | Owner |

### Step 7: 改善ログを残す

AI社員は一度作って終わりではありません。

次のログを残すことで、業務OSとして育ちます。

- どの出力が役に立ったか
- どこに誤りや不足があったか
- 追加すべきFAQは何か
- 人間レビューで毎回直している表現は何か
- 次回からAIに渡すべき文脈は何か

## Harness Engineering

このリポジトリでは、ハーネスエンジニアリングを次のように扱います。

> AIに良い出力をさせるために、文脈、役割、入力、手順、禁止事項、レビュー基準、改善ログを外部構造として設計すること。

単発プロンプトではなく、次の3層でAIを支えます。

### 1. Context Pack

AIが業務を理解するための文脈です。

- 対象業務
- 顧客像
- 現在の困りごと
- 使用ツール
- 既存資料
- 判断基準
- 避けたい表現
- 守るべき方針

主に使うファイル:

- `templates/business-hearing-sheet.md`
- `docs/principles/market-in-principles.md`

### 2. Task Harness

AIに実行させる作業の枠組みです。

- AIの役割
- 入力情報
- 出力形式
- 作業手順
- 人間に確認してほしい点
- AIが判断してはいけない領域

主に使うファイル:

- `templates/task-decomposition.md`
- `templates/ai-employee-role-card.md`
- `templates/workflow-design.md`

### 3. Review Gate

AI出力を業務で使う前の確認基準です。

- 事実確認
- 責任境界
- 個人情報
- 法的、契約的、金額的判断
- 顧客に送る表現
- 次回改善ログ

主に使うファイル:

- `templates/human-ai-boundary.md`
- `templates/workflow-design.md`

## Copy-and-Paste Prompt

最初の1業務を設計するときは、次のプロンプトを使えます。

```text
あなたは中小企業向けの業務設計アシスタントです。
目的は、AI導入そのものではなく、人手不足・属人化・対応遅れを減らすために、AIが担える処理・作業・下書き・確認補助を業務フローに組み込むことです。

以下の情報をもとに、1つの業務をAI社員化する設計をしてください。

守る方針:
- 不安をあおらない
- AIに最終責任を負わせない
- 人とAIの責任境界を明確にする
- 抽象論で終わらせず、実務手順に落とす
- まず小さな1業務から始める

入力情報:
1. 対象業務:
2. 現在の担当者:
3. 発生頻度:
4. 現在かかっている時間:
5. よく起きるミス、抜け漏れ、遅れ:
6. 参照できる資料、FAQ、履歴:
7. AIに任せたい作業:
8. 人間が必ず判断すること:

出力してください:
- 業務の作業分解
- AIに任せる作業
- 人間が担う判断
- AI社員ロールカード
- 実際のワークフロー
- 顧客に出す前のレビュー項目
- 初回導入時の注意点
- 改善ログに残すべき項目
```

## Example: 1人社労士の問い合わせ対応

### Before

- 問い合わせ内容を読むだけで時間がかかる
- 手続き相談、顧問相談、見積相談が混ざる
- 回答前に確認すべき情報が毎回抜ける
- FAQ化できる内容が蓄積されない
- 顧客対応が属人化する

### AI Employee Design

| Item | Design |
|---|---|
| Role | 問い合わせ一次整理AI社員 |
| AI tasks | 分類、要約、不足情報の洗い出し、回答下書き |
| Human tasks | 最終回答、法的判断、顧問先事情の反映 |
| Inputs | 問い合わせ本文、FAQ、サービス説明、過去回答 |
| Outputs | 要約、分類、確認事項、回答ドラフト、改善ログ |
| Review gate | 事実、法的判断、個人情報、顧客感情、送信可否 |

### After

- 問い合わせの要点がすぐ見える
- 回答前に確認すべきことが明確になる
- FAQ化すべき内容が残る
- 人間は判断と関係構築に集中できる
- 次回以降のAI出力が改善される

## Directory Structure

```text
ai-employee-business-os/
├── README.md
├── LICENSE
├── CONTRIBUTING.md
├── AGENTS.md
├── docs/
│   ├── application/
│   │   └── codex-for-oss-form-answers.md
│   ├── architecture/
│   │   └── directory-structure.md
│   └── principles/
│       └── market-in-principles.md
├── templates/
│   ├── ai-employee-role-card.md
│   ├── business-hearing-sheet.md
│   ├── human-ai-boundary.md
│   ├── task-decomposition.md
│   └── workflow-design.md
└── examples/
    └── solo-sharoushi/
        └── README.md
```

## How To Use With Codex Or Claude Code

このリポジトリは、AIエージェントに丸投げするためではなく、AIエージェントに安定した文脈を渡すためのものです。

おすすめの使い方:

1. `AGENTS.md` で共通方針を読ませる
2. `business-hearing-sheet.md` に現場情報を入れる
3. `task-decomposition.md` でAI化候補を分ける
4. `human-ai-boundary.md` でレビュー基準を決める
5. `ai-employee-role-card.md` でAI社員の役割を固定する
6. `workflow-design.md` で運用手順にする
7. 出力を人間が確認し、改善ログを残す

AIに依頼するときは、「全部読んで考えて」ではなく、対象業務に必要なファイルだけを渡します。これにより、文脈が散らからず、出力の再現性が上がります。

## What This Repository Provides

- 業務を作業単位に分解するテンプレート
- AI社員の役割を定義するロールカード
- 人とAIの責任境界を明確にするチェックリスト
- 中小企業向けのヒアリングシート
- AI導入前の業務整理フレーム
- Claude Code / Codex で扱いやすいMarkdown中心の構成
- 社労士、Web支援者、AI活用支援者が応用できる実務例

## What This Is Not

- AIに法的判断や最終責任を任せるためのツールではありません
- 不安をあおってAI導入を売るための営業資料ではありません
- 大企業向けの重いDXフレームワークではありません
- プロンプトを並べただけのテンプレート集ではありません
- 人を減らすためだけの自動化マニュアルではありません

## Roadmap

- 業種別ユースケースの追加
- 1人社労士向けの実例拡充
- 問い合わせ対応、FAQ作成、面談メモ整理のサンプル追加
- MarkdownからHTML、提案書、チェックリストへ変換するサンプル
- セキュリティ、個人情報、レビュー手順のチェックリスト追加
- Codex / Claude Code 向けの運用ルール整備

## License

This project is licensed under the MIT License.
