
<img width="2474" height="500" alt="Frame 3" src="https://github.com/user-attachments/assets/c648708a-cd84-44e7-89d8-6f34d138ff35" />



# Shopify Liquid カスタマイズ 一覧
---

## 📁 UI / 導線改善

## 📌 **LINE登録バナー固定表示**  
　画面下部にLINE誘導バナーを固定し登録率を改善  

<img width="580" height="337" alt="LINE固定バナー" src="https://github.com/user-attachments/assets/7f061f2a-ee1c-4068-bb44-bf5d9a0b6cd0" />
<br><br>



## 📌**メニュー横にアイコン追加**  
　ナビゲーション横にアイコンを配置し視認性向上  

<img width="563" height="138" alt="メニュー横にアイコン表示" src="https://github.com/user-attachments/assets/749f84cf-c302-4958-a044-b30a5b695212" />
<br><br>



## 📌 **フッターSNSにLINEアイコン追加**  
　SNSリンクにLINEを追加して導線を拡張  

<img width="628" height="231" alt="③フッターにLINEアイコン追加" src="https://github.com/user-attachments/assets/850da035-eb21-4ced-bc6e-a6240a69463b" />
<br><br>


## 📌 **ブログ記事に関連商品表示**  
　ブログ記事から商品ページへの動線を確保  

<img width="866" height="876" alt="④ブログ記事に関連商品追加" src="https://github.com/user-attachments/assets/182dd212-03c7-4336-9fb6-10a653d76361" />
<br><br>

## 📌 **会社概要ページ追加**  
　固定ページとして企業情報を表示可能に  

<img width="913" height="681" alt="⑤会社概要" src="https://github.com/user-attachments/assets/40ba4005-c7da-48e4-a30d-1090fbfb7bed" />


---

## 🛍 商品表示カスタマイズ（UI / 情報設計）

- **商品ラベル追加**  
　例：新作 / 送料無料 / 限定 / セール などを上乗せ表示

- **商品タグ表示**  
　例：ギフト向け / ○○入り / 人気 などの商品属性を表示

- **ランキング表示（1〜8位対応）**  
　人気商品を順位付きで表示（最大8位まで）

---

## 🧾 カート拡張 / 入力フォーム（line_item.properties対応）

- **あといくらで送料無料**  
　送料無料ラインまでの残額を表示

- **添付ファイルアップロード**  
　注文情報に画像等を添付可能（upload）

- **名前入れ（名入れ）**  
　ギフト用途で文字入力可能（propertiesに格納）

- **メッセージ入力欄**  
　ギフトカード等のメッセージ入力に対応

- **ギフトラッピング可否**  
　無料/有料のラッピング選択項目を追加

- **配送日時指定（カレンダー対応）**  
　年月日＋時間帯を指定可能（attributes / cart note）

---

## 🧩 技術的分類（Shopify的理解）

### **✔ Liquid Template / Snippet**
- カスタムラベル表示（条件分岐）
- タグ表示（`product.tags` 利用）
- ランキング表示（index分岐）

### **✔ Section / Block**
- ブログ内関連商品セクション
- 固定ページテンプレート追加

### **✔ Cart Properties**
- `line_item.properties` で名入れ/メッセージ/ラッピングに対応

### **✔ Theme Editor設定**
- 動的コンテンツ管理（画像 / 文言 / 商品選択）

---

## 🗂 PDFソース

> **出典：shopify【Liquid】カスタマイズ集.pdf**  
　UI・カート・商品表示のカスタマイズ例を収録

※PDFはGitHubに添付して参照可能

---

## 📌 備考

- カート拡張機能はECのギフト・注文導線の改善に有効
- Liquid実装はテーマに依存するためDawnやOS2.0で検証推奨
- Shopify FlowやCRM PLUSと組み合わせるとCRM施策も可能

---



---

## 📂 実装セクション

### 1. ランキング表示（ranking-section.liquid）
- 人気商品を最大8位まで表示
- 順位ラベルを表示（1位〜8位）
- 画像 / タイトル / 価格を表示
- 表示対象商品は管理画面から変更可能

### 2. 商品タブ切替（product-tabs.liquid）
- タブ操作で商品一覧を切り替え
- コレクションとの紐付け対応
- PC / SP レスポンシブ対応

### 3. カート拡張（cart-options.liquid）
- 無料ギフトラッピングの選択
- 配送日時指定フォーム
- 注文メモ / 属性への反映可能
- 運用を想定した構成

---

## 🎥 動画 / スクリーンショット

- `ranking-section.mp4`
- `product-tabs.mp4`
- `cart-options.mp4`
（GitHub上にアップロードしてリンク予定）

---

## 🔧 テーマエディタ対応

- タイトル、画像、商品を管理画面から編集可能
- Liquid `schema` による設定構造化
- 運用担当者がコードを触らずに変更できる状態を意識

---

## 🛠 使用技術

- Shopify Liquid
- HTML / CSS / JavaScript
- メタフィールド
- テーマエディタ設定 (`{% schema %}`)

---

必要に応じて動画やコード断片を追加できます。
