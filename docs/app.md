
<img width="1536" height="1024" alt="appヘッダー用画像" src="https://github.com/user-attachments/assets/81af8b8e-3e05-48a0-8354-95a34b7dd31f" />

# ChocoNote — Shopify 機能検証ストア

Shopify の **割引設定／自動化／CRM／レビュー／外部導線／LINE連携** などを包括的に検証したプロジェクトです。  
実務で求められる **運用目線の検証** に重点を置き、購買プロセス・顧客管理・在庫管理・配送業務を含む幅広い領域を扱っています。

---

## 🏪 **Store Overview**

- **Store Name** : ChocoNote（検証用）
- **Platform** : Shopify
- **Role** : 設定／構築／検証
- **Theme** : Dawn（拡張設定・カスタムLiquid活用）
- **検証範囲**  
  - ディスカウント設定
  - クーポン配信
  - LINE 連携（CRM PLUS）
  - Shopify Flow 自動化
  - Shopify Forms ポップアップ
  - レビュー（Judge.me）
  - Buy Button channel
  - 顧客タグによるCRMセグメント
  - 在庫監視・通知
  - 配送遅延アラート
  - VIP顧客判定

---

## 🧰 **Tech & App Stack**

| 領域 | 使用アプリ / 機能 |
|---|---|
| ディスカウント | Shopify 標準（Catalog / Discounts） |
| CRM/LINE | CRM PLUS on LINE |
| 自動化 | Shopify Flow |
| フォーム/ポップアップ | Shopify Forms |
| レビュー | Judge.me |
| 外部導線 | Buy Button channel |
| その他 | Shopify Inbox / Messaging / Search & Discovery |

---

## 🏷 **Feature & Testing (実施内容)**

以下は **機能ごとに目的 → 実施 → 結果** を明確にまとめています。

---

### ### 1. 割引設定（Catalog & Discounts）

**目的**  
商品割引やクーポンの実装挙動を検証し、チェックアウトまでの反映を確認する

**実施内容**
- Catalog で 20% 値引きを設定
- 商品カードに割引価格が表示されることを確認
- 全商品10%OFFクーポンの発行とチェックアウト反映を確認
- 無料配送条件（例：¥2,000以上）の動作検証

**結果**
- 商品カード／チェックアウト画面で正常に割引反映
- LINE配信リンク → チェックアウトまで遷移確認

**参考画像**
> `images/catalog_discount.png`  
> `images/discount_checkout.png`

## 📌カタログ
> <img width="364" height="275" alt="カタログ設定（20％）" src="https://github.com/user-attachments/assets/6c113637-1fcc-4711-9fe6-fd8c5da226d8" />
> <img width="374" height="248" alt="カタログ検証①" src="https://github.com/user-attachments/assets/7b99de50-2333-42dc-8912-43d12893beed" />

> <img width="384" height="253" alt="カタログ検証②" src="https://github.com/user-attachments/assets/4eb3183d-74e4-47c5-8aaf-b95484c2b887" />

## 📌ディスカウント
> <img width="574" height="288" alt="ディスカウント検証①" src="https://github.com/user-attachments/assets/8e8c84bc-d837-48ca-a6e2-e87fad9db935" />

---

### ### 2. LINE 連携（CRM PLUS on LINE）

**目的**  
ID連携・セグメント・メッセージ配信などのCRM動作を検証

**実施内容**
- サンクスページに LINE ID 連携誘導
- ストア上に連携バナー表示
- リッチメニュー設定
- 自動あいさつメッセージ動作確認
- Message Manager / 公式LINE 両方で配信テスト
- 10秒後ポップアップ表示（友達追加促進）
- チェックアウトリマインダー1時間後配信

**結果**
- ID連携→メッセージ→通知まで一連動作が成立
- 管理画面／顧客側の挙動差分も把握

**画像例**
> `images/line_thanks.png`  
> `images/line_popup.png`

## 📌サンクスページに LINE ID 連携誘導
> <img width="394" height="254" alt="【LINE】購入完了後のサンクスページでLINE IDを促す" src="https://github.com/user-attachments/assets/e8aafad4-d504-4bd7-ba80-bc32868acfd5" />

## 📌ストア上に連携バナー表示
> <img width="321" height="251" alt="【LINE】②ストアにLINEのID連携を促すバナーを表示する" src="https://github.com/user-attachments/assets/68965231-7d5e-432e-ae6c-bc70093cccce" />

## 📌あいさつメッセージ＆リッチメニュー設定
> <img width="413" height="249" alt="image" src="https://github.com/user-attachments/assets/5b6067f2-0d50-4371-a1a9-5e891834eec4" />

## 📌Message Manager / 公式LINE 両方で配信テスト
> <img width="466" height="260" alt="【LINE】④アプリ、公式LINEよりメッセージ配信、動作検証" src="https://github.com/user-attachments/assets/3aa9c19d-8d53-4a1e-9196-404da45138f2" />

## 📌10秒後ポップアップ表示（友達追加促進）
> <img width="470" height="264" alt="【LINE】⑤10秒後にポップアップ表示" src="https://github.com/user-attachments/assets/02a8fe11-2965-4b37-9dee-9cb381c72ec4" />

☞ [10秒後にポップアップした動画を見る](https://www.youtube.com/watch?v=dFQ22Yr7wi0)

## 📌チェックアウトリマインダー1時間後配信
> <img width="416" height="263" alt="【LINE】⑥チェックアウトリマインド配信" src="https://github.com/user-attachments/assets/7e32938e-6022-4292-8fdb-4ceeafb8415f" />
---


### ### 3. ポップアップ & クーポン（Shopify Forms）

**目的**
顧客情報取得と購入インセンティブの設計検証

**実施内容**
- トップ以外のページで5秒後ポップアップ表示
- 登録完了後クーポンコード自動生成

**結果**
- 顧客データ取得 → 顧客インセンティブ付与の導線確立

**画像**
> `images/forms_popup.png`

---

### ### 4. レビュー導入（Judge.me）

**目的**
CVR改善に寄与するレビュー導入の実装検証

**実施内容**
- Star Ratings（商品詳細）
- Review Widget（商品詳細）
- Cards Carousel（トップ等）
- Legacy Carousel（別レイアウト版）

**結果**
- レビューをフロント複数箇所へ配置可能性を確認

**画像**
> `images/judgeme_widgets.png`

---

### ### 5. 外部導線（Buy Button channel）

**目的**
外部LP → Shopify本番チェックアウト の導線を確立するための検証

**実施内容**
- 「購入する」ボタンからShopifyチェックアウトへ遷移設定

**結果**
- EC外サイト→カート→決済完了まで一連で動作

**画像**
> `images/buybutton_checkout.png`

---

## ⚙ **Shopify Flow 自動化（ユースケースまとめ）**

Flowは **実務で最も重要な領域** なので “運用ユースケース” で整理しています。

---

### **📌 UC-01：ノベルティ自動付与**
|項目|内容|
|---|---|
|条件|特定タグ付き商品購入|
|アクション|ノベルティ商品にタグ付与|
|用途|販促施策・同梱オペレーション|
|結果|購入後にタグ付与を確認|

---

### **📌 UC-02：配送遅延アラート**
|項目|内容|
|---|---|
|条件|購入後1日経過 & 未発送|
|アクション|担当者へメール通知|
|用途|発送遅延防止・CS品質向上|

---

### **📌 UC-03：在庫アラート**
|項目|内容|
|---|---|
|条件|在庫数 ≤ 3|
|アクション|管理メール通知|
|用途|在庫引当調整・仕入判断|

---

### **📌 UC-04：新商品タグの自動解除**
|項目|内容|
|---|---|
|条件|新商品にタグ付与|
|アクション|30日後にタグ自動削除|
|用途|新商品区分の自動管理|

---

### **📌 UC-05：限定品購入通知**
|項目|内容|
|---|---|
|条件|特定商品の購入|
|アクション|顧客タグ＋担当者通知|
|用途|数量限定・シーズナル商品管理|

---

### **📌 UC-06：顧客セグメント（CRM）**
|項目|内容|
|---|---|
|条件|特定コレクション購入|
|アクション|顧客に `チョコレート購入者` 等のタグ付与|
|用途|LINE配信/メルマガ/分析向けセグメント|

---

### **📌 UC-07：VIP判定**
|項目|内容|
|---|---|
|条件|1回20,000円以上購入|
|アクション|顧客タグ `2026_VIP` を付与|
|用途|LTV施策・優待施策|

---

## ✍️ **学びと所感**

- Shopifyは「導入後の運用」が本番となるため  
  **自動化 / 在庫管理 / CRM / 再購買導線** が特に重要
- テーマ改修やLiquid処理よりも  
  **運用実務の再現** がEC構築には不可欠
- FlowやLINE連携により  
  **業務負荷を減らしながら CVR/LTV を改善**できる

---

## 📁 **Repository Structure（例）**

