# Project Type Router

最初に次を聞きます。

`何を作ろうとしていますか。`

回答を以下のいずれかに分類します。

- `game`
- `web_app`
- `mobile_app`
- `test_plan`
- `planning_workshop`
- `sales_plan`
- `general_project`

判定後、対応する `bootstrap/questions/` 配下の質問ファイルを読みます。

## 判定の目安

- gameplay、player、engine、level design、combat などが出るなら `game`
- browser product、SaaS、dashboard、website、frontend なら `web_app`
- iOS、Android、app store、smartphone なら `mobile_app`
- テスト計画書、テスト方針、試験計画、品質評価、試験仕様の準備が中心なら `test_plan`
- 会議設計、論点整理、意思決定、合意形成が中心なら `planning_workshop`
- 営業戦略、パイプライン、売上計画、顧客戦略が中心なら `sales_plan`
- 上記のどれでもなければ `general_project`
