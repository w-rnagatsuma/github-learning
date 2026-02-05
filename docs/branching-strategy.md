# ブランチ戦略

## ブランチ命名規則

### 基本フォーマット
```
<type>/<issue-number>-<short-description>
```

### タイプ一覧
- `feature/` - 新機能開発
- `fix/` - バグ修正
- `hotfix/` - 緊急修正
- `refactor/` - リファクタリング
- `docs/` - ドキュメント更新
- `test/` - テスト追加・修正
- `chore/` - ビルド設定等

### 例
```
feature/123-add-user-authentication
fix/456-resolve-login-error
hotfix/789-critical-security-patch
docs/update-api-documentation
```

## ブランチ運用方法

### GitHub Flow（シンプル）
```
main (常にデプロイ可能)
  ↑
  └── feature/xxx (機能開発)
```

**フロー:**
1. `main`から`feature`ブランチを切る
2. 作業してコミット
3. PRを作成して`main`にマージ
4. `main`から自動デプロイ

**向いているケース:**
- 継続的デリバリーを実施
- リリースサイクルが短い
- シンプルな運用を好む

### Git Flow（複雑だが明確）
```
main (本番)
  ↑
develop (開発の最新)
  ↑
  ├── feature/xxx
  ├── release/x.x.x
  └── hotfix/xxx → main
```

**フロー:**
1. `develop`から`feature`ブランチを切る
2. 作業完了後`develop`にマージ
3. リリース時に`release`ブランチを作成
4. テスト後`main`と`develop`両方にマージ
5. 緊急修正は`main`から`hotfix`を切って修正
6. `hotfix`を`main`にマージ後、**`develop`にもバックマージ**（重要！）

**向いているケース:**
- 定期リリース（週次、月次等）
- 複数バージョンの並行管理
- リリース前の検証期間が必要

## ブランチの削除

### ローカルブランチ削除
```bash
git branch -d feature/xxx    # マージ済みのみ
git branch -D feature/xxx    # 強制削除
```

### リモートブランチ削除
```bash
git push origin --delete feature/xxx
```

## ベストプラクティス

- ✅ ブランチは小さく、短命に
- ✅ 定期的に`main`/`develop`から最新を取り込む
- ✅ マージ後は速やかにブランチを削除
- ✅ 作業前に必ずブランチを切る
- ❌ 長期間放置しない
- ❌ 複数の機能を1つのブランチに詰め込まない
