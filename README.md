# AI Project Development Framework

AI を使ったプロジェクト推進を、役割分担、正本管理、改善ループ込みで回すための汎用フレームワークです。

## この framework でできること

- AI が記憶に頼らず、repo 上の正本から共通認識を再構築できる
- 役割ごとに read/write 範囲、モデル、権限を分けて分業できる
- 課題や改善点を `記録 -> 判定 -> 実行 -> 検証 -> 履歴化` の流れで管理できる
- project type ごとの初期質問から、最初の canonical file を作れる
- PM 会議を `moderator / critic / advocate / analyst / human` で運用できる

## 対応している project type

- `game`
- `web_app`
- `mobile_app`
- `test_plan`
- `planning_workshop`
- `sales_plan`
- `general_project`

## 最短の始め方

1. [bootstrap/project-type-router.md](bootstrap/project-type-router.md) で project type を決める
2. [bootstrap/questions/](bootstrap/questions/) の対応ファイルに沿って初期質問へ答える
3. 回答を [bootstrap/initial-answers.md](bootstrap/initial-answers.md) に記録する
4. [bootstrap/session-bootstrap_template.md](bootstrap/session-bootstrap_template.md) に沿って最初の live ファイルを作る
5. 必要なら [samples/](samples/) の `_sample` を見本として使う

## 初回にまず見るファイル

- [README.md](README.md)
- [PROJECT.md](PROJECT.md)
- [CURRENT_STATE.md](CURRENT_STATE.md)
- [STATUS.md](STATUS.md)
- [WORKFLOW.md](WORKFLOW.md)
- [agents/AGENTS_INDEX.md](agents/AGENTS_INDEX.md)
- [config/agents.yaml](config/agents.yaml)
- [config/authority.yaml](config/authority.yaml)
- [config/workflows.yaml](config/workflows.yaml)

## test_plan 向けの追加物

テスト計画書や試験方針資料を作る案件向けに、以下を正式追加しています。

- [bootstrap/questions/test_plan.md](bootstrap/questions/test_plan.md)
- [bootstrap/output-templates/test_plan.md](bootstrap/output-templates/test_plan.md)
- [templates/test-plan-outline.md](templates/test-plan-outline.md)
- [templates/test-plan-document.md](templates/test-plan-document.md)
- [templates/system-test-spec.md](templates/system-test-spec.md)
- [samples/test-plan-document_sample.md](samples/test-plan-document_sample.md)
- [samples/test-plan-outline_sample.md](samples/test-plan-outline_sample.md)

## リポジトリの考え方

この framework は、AI が「前の会話」ではなく「現在の repo 状態」を見て判断する前提で設計しています。

### 正本の優先順位

情報が衝突した場合は、以下の順に優先します。

1. `PROJECT.md`
2. `CURRENT_STATE.md`
3. `plans/change-requests/` 配下の承認済み変更
4. `docs/decisions/` 配下の意思決定記録
5. `agents/` 配下の role contract
6. `specs/features/` 配下の作業単位仕様
7. `worklog/` 配下の作業記録

詳細は [governance/source-of-truth.md](governance/source-of-truth.md) を参照してください。

### 主なファイル

- [PROJECT.md](PROJECT.md): 何を作るか、何を作らないか
- [CURRENT_STATE.md](CURRENT_STATE.md): 現在の進捗、優先事項、ブロッカー
- [STATUS.md](STATUS.md): 人が素早く見るための要約ステータス
- [FRAMEWORK_STATUS.md](FRAMEWORK_STATUS.md): framework 自体の整備状況
- [WORKFLOW.md](WORKFLOW.md): 企画、実行、改善、承認の運用ルール
- [config/agents.yaml](config/agents.yaml): 役割ごとのモデル、権限、read/write 範囲
- [config/authority.yaml](config/authority.yaml): PM AI が自律承認できる範囲
- [config/workflows.yaml](config/workflows.yaml): 課題検知から修正完了までの流れ
- [agents/AGENTS_INDEX.md](agents/AGENTS_INDEX.md): 役割一覧
- [bootstrap/project-type-router.md](bootstrap/project-type-router.md): project type 判定
- [bootstrap/questions/](bootstrap/questions/): project type ごとの初期質問
- [bootstrap/output-templates/](bootstrap/output-templates/): 最初の live ファイル構成
- [templates/](templates/): 会議メモ、改善提案、テスト計画書などのテンプレート
- [samples/](samples/): `_sample` として使う具体例

## AI の作業開始時の参照順

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
- `human`: 人間の意図、制約、最終判断

常時複数 AI で回す必要はありません。重要判断時だけ使う運用でも成立します。

## 公開前と再利用前の確認

- [FRAMEWORK_STATUS.md](FRAMEWORK_STATUS.md)
- [REPOSITORY_SETUP.md](REPOSITORY_SETUP.md)
- [LICENSE](LICENSE)

GitHub で template repository として使う場合も、最初の案件開始前に bootstrap を一度通してください。
