# LINE カウントダウンアプリ 🎯

LINEのLIFF (LINE Front-end Framework) を使用したリアルタイムカウントダウンアプリです。グループごとに異なるイベントを設定でき、美しいグラデーション背景とともにカウントダウンを表示します。

![App Screenshot](https://img.shields.io/badge/Platform-LINE%20LIFF-00C300?style=for-the-badge&logo=line)
![Version](https://img.shields.io/badge/Version-2.1-blue?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Production%20Ready-success?style=for-the-badge)

## ✨ 主な機能

### 🎨 モダンなデザイン
- **グラスモーフィズム**効果とグラデーション背景
- **レスポンシブデザイン**（縦横画面対応）
- **Font Awesome**アイコンと**Inter**, **JetBrains Mono**フォント
- **スムーズなアニメーション**とホバーエフェクト

### 📅 イベント管理
- **カスタムイベント名**入力
- **日時選択**（datetime-local）
- **背景画像アップロード**（最大5MB）
- **リアルタイムカウントダウン**（日/時間/分/秒）

### 👥 コンテキスト対応
- **個人トーク**専用イベント
- **グループトーク**専用イベント
- **複数人トーク**専用イベント
- 各トークで**独立したイベント管理**

### 🔄 高度な制御機能
- **一時停止/再開**機能（⏸️/▶️ボタン）
- **リセット機能**（🔄ボタン）
- **完全な状態永続化**（アプリ再起動対応）
- **自動保存**（10秒間隔）
- **LINEシェア機能**（Flex Message）
- **設定編集**機能
- **エラーハンドリング**

## 🚀 セットアップ手順

### 1. LINE Developers Console 設定

1. [LINE Developers Console](https://developers.line.biz/console/) にアクセス
2. **新しいプロバイダー**を作成
3. **LINE Login**チャネルを作成
4. **LIFF**タブで新しいLIFFアプリを追加:
   - **アプリ名**: `カウントダウンアプリ`
   - **サイズ**: `Tall`
   - **エンドポイントURL**: `https://your-vercel-url.vercel.app`
   - **BLE機能**: `使用しない`
5. **LIFF ID**をコピー（例: `2007738618-kePDJ6ez`）

### 2. コード設定

1. `index.html`の**518行目**のLIFF IDを更新:
```javascript
await liff.init({ liffId: "YOUR_ACTUAL_LIFF_ID" });
```

### 3. デプロイ方法

#### 📖 Vercel (推奨)
```bash
# GitHubリポジトリ作成
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/your-username/your-repo.git
git push -u origin main

# Vercelでデプロイ
# 1. https://vercel.com にアクセス
# 2. GitHubでログイン
# 3. リポジトリを選択して「Deploy」
```

#### 📁 その他のホスティング
- **Netlify**: ドラッグ&ドロップで`index.html`をアップロード
- **GitHub Pages**: リポジトリ設定でPages有効化
- **AWS S3**: 静的ウェブサイトホスティング設定

### 4. LIFF設定完了

1. デプロイURLを**LIFF エンドポイントURL**に設定
2. LINEアプリでテスト

## 📱 使用方法

### 基本的な流れ

1. **LINEアプリ**でLIFF URLにアクセス
2. **イベント名**を入力（例: 誕生日パーティー）
3. **イベント日時**を選択
4. **背景画像**をアップロード
5. **「カウントダウン開始」**をタップ
6. **リアルタイムカウントダウン**が表示

### コンテキスト別使用例

| コンテキスト | 使用例 | 表示 |
|------------|--------|------|
| 個人トーク | 自分の目標達成日 | 📱 個人トークのイベント |
| グループトーク | チーム旅行出発日 | 👥 グループのイベント |
| 複数人トーク | 友達との約束 | 👫 複数人トークのイベント |

### 操作方法

**カウントダウン制御**
- **⏸️ 一時停止**: 右上の一時停止ボタン
- **▶️ 再開**: 停止中に再生ボタンをタップ
- **🔄 リセット**: カウントダウンを初期状態に戻す
- **⚙️ 設定編集**: イベント設定を変更
- **📤 シェア**: Flex Messageで現在の状態をシェア

**状態の保持**
- アプリを閉じても状態が自動保存される
- 一時停止した状態も完全に復元される
- 10秒ごとに自動でデータ保存

## 🛠️ 技術仕様

### フロントエンド
- **HTML5** + **CSS3** + **Vanilla JavaScript**
- **LIFF SDK v2** (LINE Front-end Framework)
- **Font Awesome 6.0** (アイコン)
- **Google Fonts** (Inter, JetBrains Mono)

### 機能詳細
- **グラスモーフィズム**: `backdrop-filter: blur()` + `rgba()` 背景
- **レスポンシブ**: CSS Grid + Flexbox + Media Queries
- **アニメーション**: CSS `@keyframes` + `transition`
- **完全な状態管理**: 一時停止/再開/リセット対応
- **データ永続化**: `localStorage` (ユーザー/グループ別)
- **自動保存**: 10秒間隔で状態を自動保存
- **状態復元**: アプリ再起動時の完全な状態復元

### ブラウザ対応
- **LINEアプリ内ブラウザ** (必須)
- **iOS Safari** (LIFF対応)
- **Android Chrome** (LIFF対応)

## 📂 ファイル構造

```
Linecountdown1/
├── index.html          # メインアプリケーションファイル
├── README.md          # このファイル
└── .git/              # Gitリポジトリ
```

## 🔧 開発・カスタマイズ

### CSS変数でテーマ変更
```css
:root {
  --primary-gradient: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  --card-background: rgba(255, 255, 255, 0.08);
  --border-color: rgba(255, 255, 255, 0.1);
}
```

### 新機能追加例
```javascript
// 新しいカウントダウン形式追加
addCustomCountdownFormat() {
    // 週/月/年単位のカウントダウン
}

// 通知機能追加
addNotificationFeature() {
    // イベント1時間前通知
}
```

## 🐛 トラブルシューティング

### よくある問題

1. **「LIFF初期化に失敗しました」**
   - LIFF IDが正しく設定されているか確認
   - LINEアプリ内で開いているか確認

2. **「画像が表示されない」**
   - 画像サイズが5MB以下か確認
   - 対応形式: JPG, PNG, GIF, WebP

3. **「データが保存されない」**
   - ブラウザの`localStorage`が有効か確認
   - プライベートモードではない事を確認

4. **「一時停止状態が復元されない」**
   - 10秒以上経過してからアプリを再起動
   - `localStorage`の容量制限を確認

5. **「カウントダウンがずれる」**
   - 一度リセットボタンを押して再計算
   - 端末の時刻設定を確認

6. **「シェアできない」**
   - LINEアプリ内でアクセスしているか確認
   - ネットワーク接続を確認

### デバッグ方法
```javascript
// ブラウザのコンソールで確認
console.log('Context:', liff.getContext());
console.log('Profile:', await liff.getProfile());
console.log('Saved Data:', localStorage.getItem('countdown_' + contextType + '_' + contextId));

// 状態管理の確認
const app = new CountdownApp();
console.log('Current Settings:', app.currentSettings);
console.log('Is Paused:', app.isPaused);
console.log('Paused Time:', app.pausedTime);
```

## 📄 ライセンス

MIT License - 自由に使用・改変・配布可能

## 🤝 コントリビューション

1. このリポジトリをフォーク
2. 機能ブランチ作成 (`git checkout -b feature/amazing-feature`)
3. 変更をコミット (`git commit -m 'Add amazing feature'`)
4. ブランチをプッシュ (`git push origin feature/amazing-feature`)
5. プルリクエスト作成

## 📞 サポート

- **GitHub Issues**: [問題報告・機能要望](https://github.com/unkey057/Linecountdown1/issues)
- **LINE Developers**: [公式ドキュメント](https://developers.line.biz/ja/docs/liff/)

## 🙏 謝辞

- **LINE Corporation** - LIFF プラットフォーム提供
- **Font Awesome** - 美しいアイコン
- **Google Fonts** - 優れたWebフォント
- **Claude Code** - 開発アシスタント

---

**開発者**: [unkey057](https://github.com/unkey057)  
**バージョン**: 2.1  
**最終更新**: 2025年7月13日  
**主要アップデート**: カウントダウン状態の完全永続化、一時停止/再開/リセット機能追加

🤖 Generated with [Claude Code](https://claude.ai/code)