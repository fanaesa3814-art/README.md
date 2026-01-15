
# 📚 Shopify制作デモサイト：「ChocoNote」

<img width="1080" height="1080" alt="モックアップ" src="https://github.com/user-attachments/assets/3e277d9b-71cd-4104-bc83-9dcdb9f5c417" />


## 📚 自己紹介
IT業界20年の現場対応力 × IT業界で約20年、カスタマーエンジニア（保守・フィールド対応）と法人向けルート営業を経験してきました。
現場での迅速なトラブル解決から、代理店への販売支援（年間売上達成率210%）まで、一気通貫で顧客の課題を解決することを強みとしています 。

今後は、これまでに培った **「ヒアリング力」** と **「継続的なフォロー体制」** を活かし、Shopifyを用いたECサイトの構築・運用支援に注力していきます。  
単に「サイトを作って終わり」ではなく、その後の **売上向上・リピート率アップ・運用効率化** まで見据えた「伴走型サポート」を提供することを目指しています。


## 📌 デモサイト情報
- **URL:** [ChocoNote デモサイト](https://choconote.myshopify.com/)
- **パスワード:** `test1234`
- **コンセプト:** チョコレートブランドの世界観を活かした高機能ECサイト　　　

## 📌Liquid Section Customization (Dawn Theme)

📍**ランキング表示セクション（8位まで表示可能）**
- 売れ筋／人気商品などをランキング形式で表示
- 最大8位までの順位表示に対応

💡こだわりポイント：教材をベースにしつつ、実用性を高めるために自力でロジックをカスタマイズしました。

**教材の仕様:** 4位まで表示  
**カスタマイズ後:** 最大8位まで表示に拡張

教材をそのままコピーするのではなく、Liquidの `case` 文の構造を理解した上で条件分岐を拡張し、  
**5〜8位の商品もバッジ付きで表示** できるようにロジックをカスタマイズしています。  
8位以降のバッジは `c_rank-other` を付与し、見た目も分かりやすく調整しました。
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
  




📍**商品タブ切替セクション**
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




📍**カート拡張機能**
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

主なカスタム: Heroバナー、レビューセクション、FAQ、ランキング表示、商品タブ切替、カートオプション など


## 💼 できること・スキルセット

### 🧩 Shopify構築・カスタマイズ
- **テーマ編集:** Dawn等のOS 2.0テーマのカスタマイズ、セクション追加。
- **独自実装:** メタフィールドを活用した商品情報の拡張表示、レスポンシブ対応。

### ⚙️ 運用自動化・アプリ連携
- **CRM連携:** 「CRM PLUS on LINE」によるステップ配信・カゴ落ち対策。
- **自動化:** 「Shopify Flow」を用いた顧客タグ付与・在庫アラート構築。
- **主要アプリ:** Judge.me（レビュー）、Shopify Inbox（チャット）等の導入設定。

### 🤝 テクニカルサポート
- **トラブル解決:** 20年の経験に基づく、PC・ネットワーク等のインフラ環境を含めた総合的なサポート。
- **伴走支援:** 専門用語を使わない丁寧な説明と、マニュアル作成による運用フォロー。


## 🛠 使用技術
- **Languages:** Liquid, HTML5, CSS3, JavaScript
- **Tools:** Shopify Flow, CRM PLUS on LINE, GitHub


## 📌工夫したポイント

- **ランキング表示**  
　人気商品を可視化することで回遊性と商品理解を促進。

- **タブ切替**  
　ジャンル・カテゴリを整理し、ユーザーが迷わず比較できるUIを実装。

- **商品ラベル／タグ表示**  
　割引・人気・新作などの情報を視覚的に伝えることで購入動機を補強。

- **運用導線の検証（LINE連携）**  
　LINE登録 → クーポン → 商品導線 → 販売 までのマーケティング導線を検証。



