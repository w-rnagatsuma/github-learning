# GitHub/Git 学習プロジェクト

実際の業務でよく利用される機能やその目的についてまとめます。

## 📚 ドキュメント

- [ブランチ戦略](docs/branching-strategy.md) - ブランチの命名規則と運用方法
- [コミット規約](docs/commit-conventions.md) - コミットメッセージの書き方
- [命名規則](docs/naming-conventions.md) - ブランチ、PR、Issue等の命名ルール

---

## Pull Request
### 目的
- レビューのやり取りを残すため
- CIと紐づけ（Branch protection rules）
### よくある運用
- main直push禁止、必ずPR経由
- Branch protection rules
    - Required status checks（CI成功必須）
    - Required reviews（承認必須）
    - 仕組みとしてテストが通った変更しか入らないように
- CODEOWNERSで「このディレクトリはこのチームが必ずレビュー」みたいに自動アサイン
    - `.github/CODEOWNERS`

## Branch protection
## GitHub Actions（CI/CD）
## Git tag / Releases（リリース管理）
## Issues / Projects（タスク管理）
## GitHub Wiki / Markdownドキュメント（docs/）
## Code scanning / Dependabot（セキュリティ系）
## Environments / Secrets（機密情報と環境管理）
## GitHub Apps / Integrations（Slack、Jira、Snyk等）
## 権限管理（Org / Team / Repo permissions）
