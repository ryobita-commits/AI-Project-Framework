# bootstrap チェックリスト

初期質問の回答が揃ったら、この順で進めます。

## 1. Project Type を確定する

- `bootstrap/project-type-router.md` の判定結果を確定する
- 結果を `bootstrap/initial-answers.md` に記録する
- `PROJECT.md` に project type を反映する

## 2. 最初の canonical file を作る

- `PROJECT.md` を埋める
- `CURRENT_STATE.md` を更新する
- `STATUS.md` を更新する
- `templates/design-spec.md` から最初の design spec を作る
- `tasks/todo.md` に最初の plan を書く
- `tasks/lessons.md` を初期化する
- `templates/meeting-note.md` から最初の meeting note を作る
- `bootstrap/output-templates/` の該当ファイルを確認する

## 3. 最初の計画成果物を作る

- `issues/backlog.md` に最初の backlog を作る
- `templates/implementation-plan.md` から最初の implementation plan を作る
- `tasks/todo.md` の plan 項目を実行可能な粒度にする
- 大きな判断が必要なら最初の change request を作る
- 最初の spec または work package を作る

## 4. framework を案件に合わせる

- `server_dev` が必要か確認する
- QA と release role が今すぐ必要か確認する
- PM council の構成を確認する
- 承認しきい値を確認する
- `config/agents.yaml` の `project_type_profiles` から active role set を選ぶ

## 5. 自動化とテンプレートを整える

- `_sample` ファイルは見本と割り切り、live ファイルに置き換える
- 自動化が必要なら `.github/workflows/ci_sample.yml` を実運用 CI に差し替える
- 判断が拘束力を持ち始めたら ADR を追加する
