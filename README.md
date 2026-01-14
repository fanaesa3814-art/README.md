# My Vue.js Library App
# 📚 プロジェクト名

<img width="1080" height="1080" alt="モックアップ" src="https://github.com/user-attachments/assets/3e277d9b-71cd-4104-bc83-9dcdb9f5c417" />


📌デモサイトURL
https://choconote.myshopify.com/

PWD：test1234

Shopify の Dawn テーマをベースに、チョコレートブランド向けの商品ページ・コレクションページを構築したデモサイトです。デザインの世界観と商品ビジュアルを活かした構成を意識しています。

📌Liquid Section Customization (Dawn Theme)

📍ランキング表示（8位まで表示可能）
<img width="1163" height="640" alt="ランキング（8位まで）" src="https://github.com/user-attachments/assets/ab4dd5cd-433b-453b-8fe9-05940b9fd60d" />





📍商品タブ切替

https://github.com/user-attachments/assets/43a1cafa-a0be-4f4f-a2f5-f29379c35fc2




📍無料ギフトラッピング、配送日時指定

https://github.com/user-attachments/assets/10b2f773-1543-4cb7-95d0-f7b8f7eae695









📌実装概要

テーマ: Dawn 12.x

カスタム: hero-banner, review-section, FAQ など

📌使った技術

Liquid

Shopify Theme Editor

HTML/CSS/JS

📌できること

### 🧩 テーマカスタマイズ（Liquid）
- Dawnテーマのセクション追加・編集
- 商品ページ・コレクションページのカスタマイズ
- メタフィールドを使った商品情報の拡張表示
- テーマエディタから変更できる構造の実装
- PC / SP のレスポンシブ対応
- HTML / CSS / Liquid での構築

### 🛍 店舗設定 / 運用
- 商品登録（商品・バリエーション・在庫）
- コレクション設定（自動 / 手動）
- クーポン設定（割引コード）
- 配送設定（送料・エリア）
- 決済設定（Shop Pay / クレカ）
- メールテンプレートの編集
- カタログ：商品ごとの割引表示・適用状況のチェック
- ディスカウント設定：割引コード、自動割引、クーポンの設定内容・条件・制限の確認

### 🛠 アプリ活用
■ Shopify アプリ連携 / 自動化設定（検証）
- CRM / 自動化領域の検証を中心に、ステップ配信・タグ付与・アラートなど運用に直結する機能を確認。

◎ CRM PLUS on LINE
- 自動ステップ配信（Welcome / 購入後など）
- LINE ID連携（顧客データ連携）
- バナー設置（誘導導線の追加）
- Checkoutリマインダー（カゴ落ち対策）
- その他：クーポン配信、シナリオ管理 など

◎ Shopify Flow
- 顧客タグ自動付与
- 在庫アラート（在庫閾値監視）
- ノベルティ自動処理（条件分岐）
- 未発送アラート（スルー防止）
- 条件 × トリガー × アクションによる自動化検証

■ その他運用理解のあるアプリ
マーケティング / 導線改善 / 顧客対応を中心に、実際の運用に必要なアプリを理解。

◎ コミュニケーション / CRM
- Shopify Inbox（問い合わせチャネル設定）
- Shopify Messaging（チャット導線追加）

◎ マーケティング / 顧客獲得
- Shopify Forms（メール取得・クーポン配布）
- Judge.me（レビュー表示・評価ウィジェット）

◎ 商品体験 / 導線改善
- Shopify Bundles（セット商品作成）
- Shopify Search & Discovery（検索・おすすめ・フィルタ）

◎ 販路拡張
- Buy Button Channel（外部サイトに埋め込み購入導線）

・コードのサンプル
（3行〜10行で”理解できる量”だけ）

# 🛒 Shopify デモセクション集

Shopify のデモストアを参考にして作成したセクションコードをまとめたリポジトリです。  
1〜2個のセクションから少しずつ増やしていくことを想定しています。

---

## ✨ このリポジトリでできること

- Shopify テーマにコピペして使えるセクションのサンプルコードを確認できる
- デモストア風の構成・クラス名・ブロック構造を学べる
- 既存テーマ（例：Dawn）をベースにデザインをカスタマイズする練習ができる

---

## 📂 収録セクション一覧

### 1. ヒーローバナーセクション（`hero-banner.liquid`）

- 大きなメインビジュアルとキャッチコピーを表示
- CTAボタン（例：「ショップを見る」「今すぐチェック」）を設置
- 背景画像・見出し・サブテキストをテーマエディタから変更可能

### 2. 特集商品グリッドセクション（`featured-collection-grid.liquid`）

- 特定のコレクションの商品をグリッド表示
- 商品画像・タイトル・価格をシンプルに一覧表示
- 表示する商品数や列数を設定で変更可能

※最初はこの2セクションからスタートし、今後少しずつ追加していく想定です。

---

## 🛠 使用技術（Tech Stack）

- Shopify Liquid
- HTML / CSS
- JavaScript(基礎）

---

## 📦 使い方（Usage）

1. このリポジトリをクローンまたはダウンロードします。

```bash
git clone https://github.com/あなたのユーザー名/リポジトリ名.git


