# 🌐 GitHub Pages 公開手順

## 📋 前準備

### 1. GitHubリポジトリの作成
1. [GitHub](https://github.com) にログイン
2. 「New repository」をクリック
3. リポジトリ名: `PremiumSuccessPlan` (または任意の名前)
4. 「Public」を選択 (GitHub Pages には必須)
5. 「Create repository」をクリック

### 2. ローカルファイルのアップロード

#### Git を使用する場合
```bash
# PremiumSuccessPlanフォルダで実行
git init
git add .
git commit -m "Initial commit: Premium Success Plan proposal"
git branch -M main
git remote add origin https://github.com/[ユーザー名]/PremiumSuccessPlan.git
git push -u origin main
```

#### GitHub Desktop を使用する場合
1. GitHub Desktop を開く
2. 「File」→「Add local repository」
3. PremiumSuccessPlan フォルダを選択
4. 「Publish repository」をクリック
5. 「Keep this code private」のチェックを外す
6. 「Publish repository」をクリック

## ⚙️ GitHub Pages の設定

### 1. Settings での設定
1. GitHubリポジトリページで「Settings」タブをクリック
2. 左サイドバーの「Pages」をクリック
3. Source: 「Deploy from a branch」を選択
4. Branch: 「main」を選択
5. Folder: 「/ (root)」を選択
6. 「Save」をクリック

### 2. カスタムドメイン設定（オプション）
独自ドメインを使用する場合:
1. DNS設定でCNAMEレコードを設定
2. GitHub Pages設定の「Custom domain」に独自ドメインを入力
3. 「Enforce HTTPS」をチェック

## 🎯 公開後の確認事項

### アクセス URL
- **GitHub Pages URL**: `https://[ユーザー名].github.io/PremiumSuccessPlan`
- **カスタムドメイン**: `https://[独自ドメイン]` (設定した場合)

### 表示確認項目
- [ ] README.md が正しく表示される
- [ ] 画像バッジが表示される
- [ ] Mermaid図が正しくレンダリングされる
- [ ] テーブルが適切にフォーマットされている
- [ ] リンクが正常に動作する

## 🔧 最適化設定

### _config.yml ファイルの作成
```yaml
# PremiumSuccessPlan/_config.yml
title: Premium Success Plan
description: リスティング広告運用最適化サービス
theme: jekyll-theme-minimal
plugins:
  - jekyll-mermaid

# SEO設定
author: [あなたの会社名]
lang: ja
```

### カスタムCSSの追加（オプション）
```css
/* PremiumSuccessPlan/assets/css/style.scss */
---
---

@import "{{ site.theme }}";

/* カスタムスタイル */
.badge {
  display: inline-block;
  margin: 2px;
}

table {
  width: 100%;
  margin: 1em 0;
}

.mermaid {
  text-align: center;
  margin: 2em 0;
}
```

## 📊 Analytics 設定

### Google Analytics 追加
```html
<!-- _includes/head.html -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

## 🚨 トラブルシューティング

### よくある問題と解決法

#### 1. ページが表示されない
- リポジトリがPublicになっているか確認
- GitHub Pages設定でブランチが正しく選択されているか確認
- 数分待ってから再度アクセス

#### 2. 画像が表示されない
- 画像ファイルのパスが正しいか確認
- ファイル名の大文字小文字が一致しているか確認
- 画像ファイルサイズが大きすぎないか確認

#### 3. Mermaid図が表示されない
- ```mermaid ブロックの記法が正しいか確認
- _config.yml にjekyll-mermaidプラグインが追加されているか確認

#### 4. 日本語フォントが崩れる
- CSSでwebfontを指定
```css
body {
  font-family: "Noto Sans JP", "Hiragino Kaku Gothic ProN", Meiryo, sans-serif;
}
```

## 🎉 公開完了後のチェックリスト

### 基本機能
- [ ] メインページ（README.md）の表示
- [ ] 全ドキュメントファイルへのナビゲーション
- [ ] レスポンシブデザインの動作確認
- [ ] モバイル表示の確認

### SEO対策
- [ ] ページタイトルの設定
- [ ] メタディスクリプションの設定
- [ ] OGP画像の設定
- [ ] サイトマップの生成

### 使いやすさ
- [ ] 目次の自動生成
- [ ] ページ内リンクの動作
- [ ] 外部リンクの動作確認
- [ ] 連絡先情報の確認

## 📈 更新とメンテナンス

### 定期更新手順
1. ローカルでファイルを編集
2. Git commit & push
3. GitHub Pages で自動デプロイ（数分後に反映）

### パフォーマンス監視
- Google PageSpeed Insights での定期チェック
- Google Analytics でのアクセス状況確認
- 外部リンク切れの定期チェック

---

> 💡 **ヒント**: GitHub Pages は静的サイトなので、変更が反映されるまで数分かかることがあります。焦らずお待ちください。