# コミットメッセージ規約

## 基本フォーマット

### Conventional Commits形式（推奨）
```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

### 例
```
feat: ユーザー認証機能を追加

ログイン・ログアウト機能を実装
- JWT認証を採用
- セッション管理を実装

Closes #123
```

## タイプ一覧

| Type | 説明 | 例 |
|------|------|-----|
| `feat` | 新機能 | `feat: 検索フィルター機能を追加` |
| `fix` | バグ修正 | `fix: ログインエラーを修正` |
| `docs` | ドキュメント | `docs: READMEにセットアップ手順を追加` |
| `style` | コードスタイル | `style: インデントを修正` |
| `refactor` | リファクタリング | `refactor: ユーザーサービスを整理` |
| `perf` | パフォーマンス改善 | `perf: データベースクエリを最適化` |
| `test` | テスト追加・修正 | `test: ログイン機能のテストを追加` |
| `build` | ビルド設定 | `build: webpackの設定を更新` |
| `ci` | CI設定 | `ci: GitHub Actionsのワークフロー追加` |
| `chore` | その他 | `chore: 依存パッケージを更新` |
| `revert` | コミット取り消し | `revert: feat: 検索機能を削除` |

## 書き方のルール

### 1. 件名（Subject）
- ✅ 50文字以内を目標
- ✅ 命令形で書く（「追加する」→「追加」）
- ✅ 先頭は小文字でも大文字でもOK（プロジェクトで統一）
- ✅ 末尾にピリオド不要
- ❌ 「〜を修正した」のような過去形は避ける

### 2. 本文（Body）
- 72文字で改行
- 「何を」「なぜ」変更したかを説明
- 「どのように」は詳細が必要な場合のみ
- 箇条書きを活用

### 3. フッター（Footer）
- Issue番号への参照: `Closes #123`, `Refs #456`
- Breaking Change: `BREAKING CHANGE: APIの認証方式を変更`

## 実践例

### 良い例 ✅
```
feat: パスワードリセット機能を実装

ユーザーがパスワードを忘れた際にメールで
リセットリンクを送信できるようにした

- トークンの有効期限は24時間
- メールテンプレートを作成
- セキュリティトークンを実装

Closes #234
```

### 悪い例 ❌
```
update

色々修正した
```
（何を変更したか不明、詳細がない）

## スコープの使い方（オプション）

スコープでコンポーネントや影響範囲を明示:
```
feat(auth): ログイン機能を追加
fix(api): ユーザー取得エンドポイントを修正
docs(readme): インストール手順を更新
```

## Breaking Changeの表記

後方互換性のない変更:
```
feat!: API認証方式をOAuthに変更

BREAKING CHANGE: Basic認証を廃止し、OAuth 2.0に移行
既存のAPIキーは無効になります
```

## Tips

### コミットの粒度
- ✅ 1コミット = 1つの論理的な変更
- ✅ レビューしやすい単位で分割
- ❌ 関係ない変更を混ぜない

### コミット前のチェック
```bash
# 変更内容を確認
git diff

# 部分的にステージング
git add -p

# コミット前に再確認
git status
```

### コミットの修正
```bash
# 直前のコミットメッセージを修正
git commit --amend

# 対話的にコミットを整理（リベース）
git rebase -i HEAD~3
```

## 参考リンク

- [Conventional Commits](https://www.conventionalcommits.org/)
- [Angular Commit Guidelines](https://github.com/angular/angular/blob/main/CONTRIBUTING.md#commit)
