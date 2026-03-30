# Superpowers 対応表

## 目的

`obra/superpowers` のワークフローをこの framework に写像し、後から参加した AI セッションでも同じ運用モデルを継承できるようにする。

## 参照元

- Repository: `https://github.com/obra/superpowers`
- Codex install guide: `https://raw.githubusercontent.com/obra/superpowers/refs/heads/main/.codex/INSTALL.md`

## 写像したワークフロー

### 1. Brainstorming -> 設計承認

- 実装前に `docs/product/`、`docs/design/`、または設計 spec ファイルで設計を定義または更新する。
- 依頼内容が曖昧なら確認質問を行う。
- 方針を決める前に選択肢とトレードオフを提示する。
- 計画に落とせるだけの明確さが得られるまでは実装しない。

推奨出力:
- `docs/design/<date>-<topic>-design.md`

対応テンプレート:
- `templates/design-spec.md`

### 2. Writing Plans -> 実装計画

- 設計承認後に、タスク単位の implementation plan を作る。
- 正確なファイルパス、明確な owner、具体的な検証手順を含める。
- できるだけ独立して完了・レビューできるタスクに分解する。

推奨出力:
- `docs/plans/<date>-<topic>-implementation.md`

対応テンプレート:
- `templates/implementation-plan.md`

### 3. Subagent-Driven Development -> 役割ベース実行

- `config/agents.yaml` の role routing を使う。
- subagent が使える環境では、各タスクに owner を 1 人だけ割り当てて委譲する。
- code quality review の前に spec compliance review を行う。

主に使う framework ファイル:
- `agents/`
- `config/agents.yaml`
- `tasks/todo.md`

### 4. Test-Driven Development -> 振る舞い変更時の既定

- 新しい振る舞い追加や bug fix では、可能な限り最初に failing test を書く。
- そのテストが想定どおり失敗することを確認する。
- その後、最小限の修正を実装する。
- focused test を再実行し、その後に広めの検証を行う。

主に使う framework ファイル:
- `tests/**`
- `tasks/todo.md`
- `templates/implementation-plan.md`

### 5. Requesting Code Review -> レビューゲート

- style だけでなく、spec と plan に照らして review する。
- 重大な問題が残っている限り完了扱いにしない。
- review findings と follow-up actions を記録する。

推奨出力:
- `docs/reviews/<date>-<topic>.md`

対応テンプレート:
- `templates/code-review.md`

### 6. Verification Before Completion -> 完了ゲート

- fresh な検証証跡なしで完了宣言しない。
- 検証には、実際に実行した command や check を含める。
- 作業終了前に `tasks/todo.md`、session report、state file を更新する。

### 7. Systematic Debugging -> 根本原因優先

- bug fix は再現、証拠収集、root cause 分析から始める。
- 推測ベースの修正をまとめて入れない。
- 原因が判明したら回帰防止のテストや検証を追加・更新する。

推奨出力:
- `docs/debug/<date>-<topic>.md`

対応テンプレート:
- `templates/debug-investigation.md`

## Superpowers から追加した framework ルール

- 明示された design / spec の文脈なしに実装しない。
- 書面化された plan なしに非自明な作業を進めない。
- 根本原因調査なしに production fix を入れない。
- fresh な検証証跡なしに完了宣言しない。
- 大きな作業は、レビュー可能な小さい単位へ分解する。
