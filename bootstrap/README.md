# bootstrap

このフォルダは、新しいプロジェクトを起動するための入口です。

## 基本フロー

1. 何を作るかを確認する
2. `bootstrap/project-type-router.md` で project type を決める
3. 対応する質問ファイルに沿って情報を集める
4. 回答を `bootstrap/initial-answers.md` に記録する
5. `bootstrap/bootstrap-checklist.md` と `bootstrap/session-bootstrap_template.md` に従って最初の live ファイルを作る
6. 必要なら `samples/` の `_sample` ファイルを参照する

## 主なファイル

- `project-type-router.md`: project type の判定ルール
- `questions/`: 種別ごとの初期質問
- `initial-answers.md`: 初期質問の回答整理
- `bootstrap-checklist.md`: 起動手順のチェックリスト
- `session-bootstrap_template.md`: 回答を正本ファイルに変換するルール
- `session-bootstrap_sample.md`: 起動例
- `output-templates/`: 種別ごとの推奨初期成果物

## 追加された project type

`test_plan` を正式追加しています。  
テスト計画書、テスト方針整理、システムテスト仕様書準備などの案件は、まず `test_plan` を選ぶと運用しやすいです。

また、複数人や複数 AI で論点整理や意思決定を行う案件向けに `planning_workshop` を強化しています。  
会議起点の企画案件では、`planning_workshop` から始めると企画ブリーフ、アジェンダ、選択肢比較、判断メモへつなげやすくなります。
