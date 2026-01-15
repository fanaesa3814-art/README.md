
# 📚 Shopify制作デモサイト：「ChocoNote」

<img width="1080" height="1080" alt="モックアップ" src="https://github.com/user-attachments/assets/3e277d9b-71cd-4104-bc83-9dcdb9f5c417" />


## 📌デモサイトURL
https://choconote.myshopify.com/

PWD：test1234

Shopify の Dawn テーマをベースに、チョコレートブランド向けの商品ページ・コレクションページを構築したデモサイトです。デザインの世界観と商品ビジュアルを活かした構成を意識しています。　　　　

## 📌Liquid Section Customization (Dawn Theme)

📍ランキング表示セクション（8位まで表示可能）
- 売れ筋／人気商品などをランキング形式で表示
- 最大8位までの順位表示に対応

💡こだわりポイント：教材をベースにしつつ、実用性を高めるために自力でロジックをカスタマイズしました。

教材の仕様: 4位までの表示  
カスタマイズ後: 最大8位までの表示に対応

単純なコピーではなく、Liquidのcase文の構造を理解した上で条件分岐を拡張し、8位以降のバッジデザイン（c_rank-other）の出し分けまで実装しています。
<img width="1028" height="770" alt="ランキング表示" src="https://github.com/user-attachments/assets/cb9543b7-c5e6-45bb-9c50-be81c4325cc4" />



```liquid
{% if section.settings.show_ranking %}
  {% case forloop.index %}
    {% when 1 %}
      <span class="c_ranking-badge c_rank-{{ forloop.index }}">{{ forloop.index }}</span>
    {% when 2 %}
      <span class="c_ranking-badge c_rank-{{ forloop.index }}">{{ forloop.index }}</span>
    {% when 3 %}
      <span class="c_ranking-badge c_rank-{{ forloop.index }}">{{ forloop.index }}</span>
    {% when 4 %}
      <span class="c_ranking-badge c_rank-{{ forloop.index }}">{{ forloop.index }}</span>
    {% when 5 %}
      <span class="c_ranking-badge c_rank-{{ forloop.index }}">{{ forloop.index }}</span>
    {% when 6 %}
      <span class="c_ranking-badge c_rank-{{ forloop.index }}">{{ forloop.index }}</span>
    {% when 7 %}
      <span class="c_ranking-badge c_rank-{{ forloop.index }}">{{ forloop.index }}</span>
    {% when 8 %}
      <span class="c_ranking-badge c_rank-other">{{ forloop.index }}</span>
  {% endcase %}
{% endif %}
```
  




📍商品タブ切替セクション
- 商品リストをタブ（カテゴリ）切替で表示
- タブ操作により該当商品のみを即時切替

💡こだわりポイント: Liquidでの動的な商品取得と、JavaScriptによるDOM操作を連携させる実装を学びました。

外部ライブラリを使用せずバニラJSで記述することで、サイトの読み込み負荷を抑えつつ、ユーザーが直感的にカテゴリを選べるUIを実現しています。

https://github.com/user-attachments/assets/43a1cafa-a0be-4f4f-a2f5-f29379c35fc2


```liquid

<div class="tab-content" data-tab="daily_gift" id="content-daily_gift">
    <div class="products">
      {% for product in collections.daily_gift.products %}
        <div class="product">
          <a href="{{ product.url }}">
            <img src="{{ product.featured_media | image_url: width: 500 }}" width="500" height="500">
            <p class="product-title">{{ product.title }}</p>
            <p class="product-price">
               {% if product.compare_at_price_max > product.price %}
                <span class="price-compare">{{ product.compare_at_price_max | money }}</span>
                <span class="price-sale">{{ product.price | money }}</span>
              {% else %}
                {{ product.price | money }}
              {% endif %}
            </p>
          </a>
        </div>
      {% endfor %}
    </div>
  </div>

<script>
  window.addEventListener('load', function(){
    // デイリーボタンをクリックした際
    document.querySelector("#btn-daily_gift").addEventListener("click", function(){
       // クリックされた時の処理
       document.querySelector("#content-daily_gift").style.display = "block";
       document.querySelector("#content-premium_gift").style.display = "none";
       // デイリーボタンをアクティブにする
       document.querySelector("#btn-daily_gift").classList.add("active");
      // プレミアムボタンを非アクティブにする
      document.querySelector("#btn-premium_gift").classList.remove("active");
    });
</script>
```




📍カート拡張機能
- カート画面に以下の追加オプションを実装  
　✔ 無料ギフトラッピングの可否選択  
　✔ 配送日時指定フォーム
- 入力内容は注文データに反映（メモや属性に格納可能）

💡こだわりポイント： カート画面に「無料ギフトラッピング」の選択肢を追加しました。

単にボタンを置くだけでなく、お客さまが選んだ内容が、お店側の管理画面（注文データ）に自動で反映される仕組みを実装しています。 
これにより、運営者が注文を確認する際に、ラッピングの有無を一目で判断できる「実務に役立つカスタマイズ」を意識しました。

https://github.com/user-attachments/assets/10b2f773-1543-4cb7-95d0-f7b8f7eae695



```
{%- when 'gift' -%}
  <p class="cart-attribute__field">
   <input type="hidden" name="attributes[無料ギフトラッピング]" value="No" form="cart">
   <input type="checkbox" name="attributes[無料ギフトラッピング]" value="Yes"{% if cart.attributes["無料ギフトラッピング"] == "Yes" %} checked{% endif %} form="cart">
   <label>🎀 無料ギフトラッピング</label>
  </p>
```






## 📌実装概要

テーマ: Dawn 12.x

カスタム: hero-banner, review-section, FAQ など

## 📌使った技術

- Liquid

- Shopify Theme Editor

- HTML/CSS/JS

## 📌できること

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


## 🛠 使用技術（Tech Stack）

- Shopify Liquid
- HTML / CSS
- JavaScript(基礎）

---

## 📌工夫したポイント

- **ランキング表示**  
　人気商品を可視化することで回遊性と商品理解を促進。

- **タブ切替**  
　ジャンル・カテゴリを整理し、ユーザーが迷わず比較できるUIを実装。

- **商品ラベル／タグ表示**  
　割引・人気・新作などの情報を視覚的に伝えることで購入動機を補強。

- **運用導線の検証（LINE連携）**  
　LINE登録 → クーポン → 商品導線 → 販売 までのマーケティング導線を検証。

## 📦 使い方（Usage）

1. このリポジトリをクローンまたはダウンロードします。

```bash
git clone https://github.com/あなたのユーザー名/リポジトリ名.git


