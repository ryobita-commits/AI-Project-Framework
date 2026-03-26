# AI Project Development Framework

AI を使ったプロジェクト推進を、役割分担、正本管理、改善ループ込みで回すための汎用フレームワークです。

## 目的

各 AI が記憶ではなくリポジトリ上のファイルから共通認識を再構築し、同じ前提で企画、設計、実装、テスト、レビュー、改善を進められる状態を作ります。

## 正本の優先順位

情報が衝突した場合は、以下の順に優先します。

1. `PROJECT.md`
2. `CURRENT_STATE.md`
3. `plans/change-requests/` 配下の承認済み変更
4. `docs/decisions/` 配下の意思決定記録
5. `agents/` 配下の role contract
6. `specs/features/` 配下の作業単位仕様
7. `worklog/` 配下の作業記録

詳細は `governance/source-of-truth.md` を参照します。

## 主なファイル

- `PROJECT.md`: 何を作るか、何を作らないか
- `CURRENT_STATE.md`: 現在の進捗、優先事項、ブロッカー
- `STATUS.md`: 人が素早く見るための要約ステータス
- `FRAMEWORK_STATUS.md`: フレームワーク自体の整備状況
- `WORKFLOW.md`: 企画、実行、改善、承認の運用ルール
- `config/agents.yaml`: 役割ごとのモデル、権限、read/write 範囲
- `config/authority.yaml`: PM AI が自律承認できる範囲
- `config/workflows.yaml`: 課題検知から修正完了までの流れ
- `agents/AGENTS_INDEX.md`: 役割一覧
- `bootstrap/project-type-router.md`: 最初の project type 判定
- `bootstrap/questions/`: project type ごとの初期質問
- `bootstrap/output-templates/`: project type ごとの最初の live ファイル構成
- `templates/`: 会議メモ、改善提案、テスト計画書などのテンプレート
- `samples/`: `_sample` として使う具体例

## 作業開始時の参照順

各 AI は、作業前に原則として以下の順で参照します。

1. `README.md`
2. `PROJECT.md`
3. `CURRENT_STATE.md`
4. `STATUS.md`
5. `WORKFLOW.md`
6. `governance/source-of-truth.md`
7. `config/agents.yaml`
8. `config/authority.yaml`
9. `config/workflows.yaml`
10. `agents/AGENTS_INDEX.md`
11. `agents/shared/conventions.md`
12. `agents/shared/definition-of-done.md`
13. 自分の role contract

## PM 会議モード

企画や重要判断の場では、以下の構成で会議できます。

- `pm_moderator`: 司会、論点整理、結論記録
- `pm_critic`: 批判的視点、リスク発見
- `pm_advocate`: 推進視点、前向きな打ち手整理
- `pm_analyst`: 根拠整理、比較、統合判断
- human: 人間の意図、制約、最終判断

常時複数 AI で回す必要はありません。重要判断時だけ使う運用でも成立します。

## bootstrap の使い方

この framework は、少なくとも以下の project type に対応します。

- `game`
- `web_app`
- `mobile_app`
- `test_plan`
- `planning_workshop`
- `sales_plan`
- `general_project`

開始手順は以下です。

1. `bootstrap/project-type-router.md` で project type を判定する
2. 対応する `bootstrap/questions/` の質問に答える
3. 回答を `bootstrap/initial-answers.md` にまとめる
4. `bootstrap/session-bootstrap_template.md` に沿って canonical file を作る
5. 必要なら `samples/` の `_sample` ファイルを見本として使う

## test_plan 向け追加物

テスト計画書作成案件向けに、以下を正式追加しています。

- `bootstrap/questions/test_plan.md`
- `bootstrap/output-templates/test_plan.md`
- `templates/test-plan-outline.md`
- `templates/test-plan-document.md`
- `templates/system-test-spec.md`
- `samples/test-plan-document_sample.md`
- `samples/test-plan-outline_sample.md`

## 公開前確認

GitHub に公開する前に、以下を確認してください。

1. `FRAMEWORK_STATUS.md`
2. `REPOSITORY_SETUP.md`
3. `LICENSE`
