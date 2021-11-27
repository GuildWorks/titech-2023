---
marp: true
theme: gaia
size: 16:9
header: '　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　Copyright Ryo Imahashi'

page_number: true
paginate: true

---
## 参考
- やること

- Market Placeの外部連携コンポーネント
  <!-- - Youtube(固定の動画を見せられるだけ) -->
  - Twitter(アカウント名を入れたら、その人の投稿一覧が表示できる)
    - DBからアカウント名を動的に取得すると、エラー。。 ![](images/2021-11-26-05-42-47.png)
  <!-- - Google Sign-In (Google Developer Accountが有料なのでやらない: アカウントを作成するには、1 回限りの登録料として 25 ドルをお支払いいただく必要があります。アカウントの登録を完了するには、有効な身分証明書による本人確認が求められることがあります。ご本人であることを確認できなかった場合、登録料の払い戻しは行われません。) -->
  <!-- - Map(Google Map) GCPアカウント用にクレジットカード登録が必要なので、割愛 -->
  - Video Calling
    - 通話できた。1440 Minutesまで無料らしい。 https://app.garlik.io/

<!-- - IFTTTという選択肢もある？→ Adaloなかった -->
<!-- - pipedreamも使える？https://pipedream.com/apps/adalo/integrations/google-sheets
  - AdaloのアクションがGet all collection recordsしかない(Adaloのトリガーは0)ので断念 -->
- External CollectionでのCRUD(5 endpoint actions) 
  - 参考: https://qwerty.work/blog/2021/06/adalo-sheetdb-googlespreadsheet.php
  - SheetDB API Doc: https://docs.sheetdb.io/#sheetdb-api
  - 作ったアプリ: https://previewer.adalo.com/434969fa-d5c1-4a08-87a1-1fba0027073b
  - メモ
    - Current xxx のページ間の受け渡し後の詳細画面、編集画面等ではGet One RecordのAPIは呼ばれていない(受け渡されているので)
      - Adaloではリストの選択や絞り込みで1リソースを表示するので、Get One Recordは不要っぽい
    - id以外のColumnを使ってもAPIコールできる? -> {{}}で指定できそうだけど、エラーになるのでダメみたい。idを使うことにしよう。
    - External Collection のEdit Settingsを開くと毎回EndPointsが初期値になるので、要注意
<!-- Get All Records
Get One Record
Create a Record
Update a Record
Delete a Record -->
  <!-- - AirTableの説明は流石に盛り込めないので、GoogleSpreadSheetにしよう -->
- External CollectionでマスタデータをGET(CRUD全部を必要としない場合もあるよね)
  - 参考: https://qiita.com/wakiwaki/items/5016404ce0c15a755188
  - メモ
    - Auth(api-key)のセットアップも紹介する

- Custom Action
  - 郵便番号からの住所入力 https://www.youtube.com/watch?v=7k4x2CaAbCI

- API Documentを読み込んで設定をするのは大変なので、便利なツールを使いましょう
  - zapierは断念 https://community.zapier.com/general-questions-3/bad-request-error-when-connecting-to-adalo-12739
  - 使うツール: Integromat https://www.integromat.com/en/integrations/google-sheets
    - GoogleSpreadSheet連携 https://www.integromat.com/en/integration/8256-add-new-adalo-records-to-google-sheets
      - TODO: Googleアカウント作成
      - 15分に一回連携される
      - 一度Runしないと、Collection内のプロパティが選択できない
      - 空行を入れると、その上にレコードが挿入される
      - レコードの更新はWatch対象をUpdatedAtにすると連携されるが、新たな行が挿入されて重複してしまう
      - 手動でのスプレッドシート側の行挿入とか更新とかどうなるかは要検証
    - Slack連携 https://www.integromat.com/en/integration/8257-get-slack-messages-for-new-adalo-records
      - 管理者権限を持つSlackのワークスペースが必要(そこから教える？)
    <!-- - Twitterは有料プラン限定なので断念 -->
    - メール送信
      - HTMLなら改行を<br>で入れる
    - Zoomは後でもう一度試す
    - TODO: Google Map
    - TODO: Webhook

External Collections -> Custom Action -> Integromat の流れが良い？

※ Adaloの変更が反映されなかったり、連携先のツールが動かなくなったりするタイミングがあります。

---
- データベースの一番上のプロパティは消せないよ

--




--- 
参考
https://help.adalo.com/integrations/external-collections-with-apis

https://andd.live/7970/adalo-resource%E3%83%BBapi%E3%81%AB%E3%82%88%E3%82%8B%E5%A4%96%E9%83%A8%E3%82%B3%E3%83%AC%E3%82%AF%E3%82%B7%E3%83%A7%E3%83%B3%E3%80%81%E5%A4%96%E9%83%A8%E3%82%B3%E3%83%AC%E3%82%AF%E3%82%B7%E3%83%A7/

https://qwerty.work/blog/2021/06/adalo-sheetdb-googlespreadsheet.php

https://qiita.com/sakuraya/items/6f1030279a747bcce648#%E3%83%A1%E3%82%BF%E6%83%85%E5%A0%B1%E3%81%AF%E3%83%98%E3%83%83%E3%83%80%E3%81%A7%E3%81%BE%E3%81%8B%E3%81%AA%E3%81%88%E3%82%8B%E3%81%93%E3%81%A8%E3%81%8C%E5%A4%9A%E3%81%84

Instagramは大変なわりに開発者の投稿しか表示できないっぽい(ユーザー自身で認証して投稿を取得させるには、アプリレビューが必要)ので、断念 
https://www.e-pokke.com/blog/instagram-basic-display-api.html
>テストユーザーとして登録したご自身のInstagramアカウントについては、追加の権限の設定が不要なため、アプリを公開（ライブモード）する際に 「アプリレビュー」が不要 となっています。

Micro API https://m3o.com/

---