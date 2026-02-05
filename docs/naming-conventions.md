# 命名規則

## ブランチ名

### フォーマット
```
<type>/<issue-number>-<description>
```

### ルール
- 小文字とハイフンを使用
- スペース不可
- 英数字のみ（日本語不可）
- 簡潔で分かりやすく

### 例
```
feature/123-user-registration
fix/456-login-timeout-error
hotfix/789-security-vulnerability
docs/update-api-guide
```

## コミットメッセージ

詳細は [commit-conventions.md](./commit-conventions.md) を参照

### 基本形式
```
<type>: <description>
```

## Pull Request（PR）

### タイトル
```
[<type>] <description>
```

### 例
```
[Feature] ユーザー登録機能を実装
[Fix] ログインタイムアウトエラーを修正
[Refactor] 認証ロジックを整理
[Docs] API仕様書を更新
```

### ルール
- 何を変更したか一目で分かるように
- Issue番号を含めると良い: `[Feature] #123 ユーザー登録機能`

## Issue

### タイトル
```
[<label>] 具体的な内容
```

### 例
```
[Bug] ログイン画面でタイムアウトが発生する
[Feature Request] パスワードリセット機能が欲しい
[Question] デプロイ手順について
```

### ラベル
- `bug` - バグ報告
- `enhancement` - 機能追加
- `documentation` - ドキュメント
- `question` - 質問
- `good first issue` - 初心者向け
- `help wanted` - 協力者募集
- `wontfix` - 対応しない

## タグ（リリース）

### Semantic Versioning
```
v<major>.<minor>.<patch>
```

### 例
```
v1.0.0    # 初回リリース
v1.1.0    # 新機能追加
v1.1.1    # バグ修正
v2.0.0    # 破壊的変更
```

### バージョンの上げ方
- **Major**: 後方互換性のない変更
- **Minor**: 後方互換性のある機能追加
- **Patch**: 後方互換性のあるバグ修正

### プレリリース
```
v1.2.0-alpha.1
v1.2.0-beta.2
v1.2.0-rc.1
```

## ファイル・ディレクトリ

### 一般的な規則

| 言語/FW | 規則 | 例 |
|---------|------|-----|
| JavaScript/TypeScript | camelCase / PascalCase | `userService.ts`, `UserModel.ts` |
| Python | snake_case | `user_service.py` |
| Java | PascalCase | `UserService.java` |
| C# | PascalCase | `UserService.cs` |
| Ruby | snake_case | `user_service.rb` |

### ディレクトリ構造の例
```
project/
├── src/              # ソースコード
├── docs/             # ドキュメント
├── tests/            # テスト
├── scripts/          # スクリプト
├── config/           # 設定ファイル
└── .github/          # GitHub設定
    ├── workflows/    # GitHub Actions
    └── CODEOWNERS    # コードオーナー
```

## 環境変数

### フォーマット
```
SCREAMING_SNAKE_CASE
```

### 例
```
DATABASE_URL
API_SECRET_KEY
NODE_ENV
MAX_RETRY_COUNT
```

## 定数

### JavaScript/TypeScript
```typescript
const MAX_RETRY_COUNT = 3;
const API_BASE_URL = 'https://api.example.com';
```

### Python
```python
MAX_RETRY_COUNT = 3
API_BASE_URL = 'https://api.example.com'
```

## GitHub Actions ワークフロー

### ファイル名
```
.github/workflows/<name>.yml
```

### 例
```
ci.yml
deploy-production.yml
test-pull-request.yml
release.yml
```

## Tips

### DO ✅
- 一貫性を保つ
- プロジェクト全体で統一
- チームで合意した規則に従う
- 分かりやすく明確に

### DON'T ❌
- 略語の乱用
- 規則の途中変更（移行計画なしに）
- 曖昧な名前
- 文脈なしで理解できない名前

### ツールで自動化
- **ESLint**: JavaScript/TypeScript
- **Prettier**: コードフォーマット
- **commitlint**: コミットメッセージ
- **branch-naming-check**: ブランチ名検証
