# Session Bootstrap Template

このファイルは、初期質問の回答を最初の live project package に変換するためのルールです。

## 入力

- `bootstrap/project-type-router.md`
- 対応する `bootstrap/questions/` の質問ファイル
- 対応する `bootstrap/output-templates/` の出力テンプレート
- `bootstrap/initial-answers.md`
- `PROJECT_sample.md`
- `samples/` 配下の `_sample` ファイル

## 出力

- `PROJECT.md`
- `CURRENT_STATE.md`
- `STATUS.md`
- `docs/design/<date>-<topic>-design.md`
- `docs/plans/<date>-<topic>-implementation.md`
- `tasks/todo.md`
- `tasks/lessons.md`
- `plans/meeting-notes/<date>-kickoff.md`
- `issues/backlog.md`
- `specs/features/` 配下の最初の spec、または同等の作業単位定義

## 変換ルール

- `_sample` ファイルは見本であり、正本にしてはいけない
- 汎用文よりも、案件固有で短い表現を優先する
- 未解決事項は `PROJECT.md` の `Open Questions` に残す
- `game` 以外では用語をその領域に合わせて読み替える
- `test_plan` の場合は、テスト対象、読者、品質判断材料、工程範囲を最優先で抜き出す
- active role set は `config/agents.yaml#project_type_profiles` から選ぶ

## 必須で抜き出す項目

- project type
- タイトル
- 一言説明
- 主目的
- 主成果物
- 最初のマイルストーン
- 主要リスク
- 主な未決定事項
- 最初に使う role
- 最初の design spec
- 最初の task plan

## kickoff meeting に最低限含めるもの

- 判断したい問い
- 共通目標
- 検討した選択肢
- advisor の主張
- human input
- 決定
- 次アクション
