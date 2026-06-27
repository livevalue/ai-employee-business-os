# Workflow Design

## Workflow Name

例: 問い合わせ対応から回答下書きまでのAI補助フロー

## Goal

この業務フローで実現したい成果を記入します。

## Trigger

- いつ始まるか:
- 誰が始めるか:
- どのツールから始まるか:

## Steps

| Step | Actor | Action | Output | Review |
|---|---|---|---|---|
| 1 | Human | 問い合わせを確認する | 原文 |  |
| 2 | AI | 要点を整理する | 要約 | Human |
| 3 | AI | 回答案を下書きする | Draft | Human |
| 4 | Human | 内容を確認する | Final response | Owner |
| 5 | Human/AI | 記録と改善点を残す | Log | Owner |

## Quality Checks

- 顧客課題に答えているか
- 不足情報を確認できているか
- 表現が不安をあおっていないか
- 人間の最終確認が入っているか
- 次回改善に使えるログが残るか

## Improvement Log

| Date | Issue | Change | Result |
|---|---|---|---|
|  |  |  |  |

