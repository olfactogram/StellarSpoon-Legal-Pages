# Stellar Spoon Legal Pages

このフォルダには、Stellar Spoon アプリの法的文書を表示するための GitHub Pages サイトが含まれています。

## 📁 ファイル構成

```
github-pages/
├── index.html              # メインページ（法的文書一覧）
├── terms-of-service.html   # 利用規約
├── privacy-policy.html     # プライバシーポリシー
├── commercial-law.html     # 特定商取引法に基づく表記
├── css/
│   └── style.css           # スタイルシート
└── README.md               # このファイル
```

## 🚀 GitHub Pages でのデプロイ方法

### 1. リポジトリの作成
```bash
# 新しいリポジトリを作成
git init stellarspoon-legal
cd stellarspoon-legal

# ファイルをコピー
cp -r /path/to/recipe_book_prj/github-pages/* .

# Git に追加・コミット
git add .
git commit -m "Add legal pages for Stellar Spoon"

# GitHub にプッシュ
git remote add origin https://github.com/yourusername/stellarspoon-legal.git
git branch -M main
git push -u origin main
```

### 2. GitHub Pages の有効化
1. GitHub リポジトリページを開く
2. Settings タブをクリック
3. 左サイドバーの "Pages" をクリック
4. Source で "Deploy from a branch" を選択
5. Branch で "main" を選択
6. Folder で "/ (root)" を選択
7. "Save" ボタンをクリック

### 3. カスタムドメインの設定（オプション）
1. GitHub Pages設定で "Custom domain" に `legal.stellarspoon.app` を入力
2. DNS設定で CNAME レコードを追加：
   ```
   legal.stellarspoon.app → yourusername.github.io
   ```

## 🔗 URL 構成

デプロイ後のURL例：
```
https://yourusername.github.io/stellarspoon-legal/
https://yourusername.github.io/stellarspoon-legal/terms-of-service.html
https://yourusername.github.io/stellarspoon-legal/privacy-policy.html
https://yourusername.github.io/stellarspoon-legal/commercial-law.html
```

カスタムドメインを設定した場合：
```
https://legal.stellarspoon.app/
https://legal.stellarspoon.app/terms-of-service.html
https://legal.stellarspoon.app/privacy-policy.html
https://legal.stellarspoon.app/commercial-law.html
```

## 📱 アプリでの実装

Flutter アプリで以下のようにURLを設定：

```dart
class LegalUrls {
  static const String baseUrl = 'https://yourusername.github.io/stellarspoon-legal';
  // または: static const String baseUrl = 'https://legal.stellarspoon.app';
  
  static const String privacyPolicy = '$baseUrl/privacy-policy.html';
  static const String termsOfService = '$baseUrl/terms-of-service.html';
  static const String commercialLaw = '$baseUrl/commercial-law.html';
}

// 利用例
void _openPrivacyPolicy() async {
  final url = Uri.parse(LegalUrls.privacyPolicy);
  if (await canLaunchUrl(url)) {
    await launchUrl(url, mode: LaunchMode.inAppWebView);
  }
}
```

## 🎨 デザイン特徴

- **レスポンシブデザイン**: モバイル・タブレット・デスクトップ対応
- **Stellar Spoon ブランド**: アプリと統一されたカラーテーマ
- **読みやすさ重視**: 法的文書に適した文字サイズ・行間
- **ナビゲーション**: 各ページ間の移動が簡単
- **アクセシビリティ**: スクリーンリーダー対応

## 🔄 更新方法

1. HTMLファイルを編集
2. Git にコミット・プッシュ
3. GitHub Pages が自動的に更新（通常1-2分）

```bash
# ファイルを編集後
git add .
git commit -m "Update privacy policy"
git push origin main
```

## 🛡️ セキュリティ

- **HTTPS 強制**: GitHub Pages は自動的に HTTPS
- **個人情報なし**: 法的文書のみでユーザーデータは含まない
- **静的サイト**: セキュリティリスクが低い

## 📝 カスタマイズ

### 色の変更
`css/style.css` の以下の値を変更：
```css
:root {
  --primary-color: #6A9C89;
  --secondary-color: #F5EEC2;
  --accent-color: #A3D39C;
  --background-color: #F7F5EB;
  --text-color: #2E4057;
}
```

### フォントの変更
```css
body {
  font-family: 'YourFont', -apple-system, BlinkMacSystemFont, sans-serif;
}
```

## ⚖️ 法的注意事項

- 実際の事業者情報（名前、住所、電話番号）を記入してください
- 具体的な料金を設定してください
- 法的要件に応じて内容を調整してください
- 定期的に法令改正に応じて更新してください

## 📞 サポート

法的文書の内容やサイトの技術的な問題については：
- support@stellarspoon.app
- プライバシーに関する問い合わせ: privacy@stellarspoon.app