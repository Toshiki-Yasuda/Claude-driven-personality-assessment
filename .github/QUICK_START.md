# 🚀 GitHub Pages デプロイ完全セットアップガイド

## ✅ 現在の状態

ワークフローが簡素化され、**環境保護ルール不要**のセットアップになりました。

---

## 📋 必要な設定（GitHub リポジトリ）

### ステップ 1: GitHub Pages を有効化

1. **GitHub リポジトリ → Settings**
2. 左メニュー → **Pages**
3. **Source** セクションで：
   - **Deploy from a branch** を選択
   - Branch: **main** または **claude/check-status-c7g27** を選択
   - Folder: **/ (root)** を選択
4. **Save** をクリック

**パス**: `Settings → Pages → Source`

---

### ステップ 2: ワークフロー実行を確認

1. リポジトリ → **Actions** タブ
2. **Deploy to GitHub Pages** ワークフローを確認
3. ✅ 緑のチェックマークが出るまで待つ

**期待される時間**: 1〜3 分

---

### ステップ 3: デプロイ完了を確認

1. **Settings → Pages** に戻る
2. 「Your site is live at」に URL が表示される
3. または以下の URL でアクセス：
   ```
   https://Toshiki-Yasuda.github.io/Claude-driven-personality-assessment/yasuda_toshiki_uiux.html
   ```

---

## 🐛 トラブルシューティング

### パターン 1: ワークフローが失敗する場合

**確認事項:**

1. **HTML ファイルが存在するか**
   - リポジトリのルートに `yasuda_toshiki_uiux.html` があるか確認

2. **Actions タブでログを確認**
   - 失敗したワークフロー → ログを展開
   - エラーメッセージを探す

3. **ファイル検証ステップをチェック**
   ```
   ✓ yasuda_toshiki_uiux.html found
   ```
   このメッセージが出れば、ファイルは存在します

### パターン 2: デプロイ成功だが、ページが見つからない

**原因**: GitHub Pages が完全に初期化されていない

**解決策**:
- 3〜5 分待つ
- ブラウザのキャッシュをクリア（Ctrl+Shift+Delete）
- 別のブラウザで試す

### パターン 3: URL にアクセスできない

**確認**:
1. Settings → Pages で URL が表示されているか
2. Public リポジトリになっているか
3. URL の大文字小文字は正しいか

---

## 📊 各ステップの詳細

### GitHub Pages Source の設定

```
Settings
  └─ Pages
      ├─ Source: Deploy from a branch ✓
      ├─ Branch: main (or claude/check-status-c7g27)
      └─ Folder: / (root)
```

### ワークフロー実行確認

```
Actions
  └─ Deploy to GitHub Pages
      └─ 最新ワークフロー実行結果を確認
          ├─ ✅ All checks passed
          └─ ❌ エラーがあれば詳細ログを確認
```

---

## 🎯 期待される URL

```
https://Toshiki-Yasuda.github.io/Claude-driven-personality-assessment/yasuda_toshiki_uiux.html
```

- **Toshiki-Yasuda**: GitHub ユーザー名
- **Claude-driven-personality-assessment**: リポジトリ名
- **yasuda_toshiki_uiux.html**: ファイル名

---

## ✨ ワークフローの流れ

```
Push to main / claude/check-status-c7g27
         ↓
Actions トリガー
         ↓
Checkout コード
         ↓
Pages 設定
         ↓
ファイル検証（yasuda_toshiki_uiux.html が存在するか）
         ↓
artifact アップロード
         ↓
Pages にデプロイ
         ↓
✅ 公開 URL でアクセス可能
```

---

## 📞 よくある質問

**Q: 何のファイルをデプロイしてますか？**
A: リポジトリ全体（`.github/` 以下を除く）がデプロイされます

**Q: CSS や JavaScript は正しく表示されますか？**
A: はい。`.nojekyll` ファイルがあるため、すべてのファイルがそのまま提供されます

**Q: 複数のブランチからデプロイできますか？**
A: はい。`main` および `claude/check-status-c7g27` からデプロイ可能です

**Q: デプロイ後、どれくらいで反映されますか？**
A: 通常 1〜3 分。時間がかかる場合は 5 分お待ちください

---

## 🔄 再デプロイ方法

もし何か変更した場合：

1. ファイルをコミット＆プッシュ
2. GitHub の Actions タブで自動的にワークフロー実行
3. 完了後、ページをリロード（キャッシュクリア推奨）

または、手動トリガー：

1. Actions タブ
2. Deploy to GitHub Pages ワークフロー
3. **Run workflow** ボタン
4. ブランチ選択して実行

---

## ✅ セットアップ完了チェックリスト

- [ ] GitHub Pages Source が「Deploy from a branch」に設定
- [ ] Branch が「main」または「claude/check-status-c7g27」に設定
- [ ] Folder が「/ (root)」に設定
- [ ] Save をクリック
- [ ] Actions タブでワークフロー実行中 / 完了
- [ ] Settings → Pages で「Your site is live at」に URL が表示
- [ ] URL にアクセスして HTML ページが表示される

---

**最終更新**: 2026年1月14日
**ワークフロー**: Simplified Version (環境保護ルール不要)
