---
marp: true
theme: gaia
size: 16:9
header: '　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　Copyright Ryo Imahashi'

page_number: true
paginate: true
---

**Programming Boot Camp**

# 応用編

**東京工業大学 2021/11/27**
　
　
　
　
　
　　　　　　　　　　　　　　　　　　　　　　　　**Ryo Imahashi**



---
## 目次
  - 今回やることの確認
  - 外部連携
  - ノーコードツールでの共同作業のTips
  - Adaloでの共同作業演習
  - Bubbleでの共同作業演習
  - ふりかえり

---
## 今回やることの確認

---
## 外部連携

---
### 外部連携とは
AdaloやBubbleだけで実現できないことがある場合、外部サービスと連携することでそれを実現できるかもしれません。

---
### 外部連携の方法
Adalo
- Zapier
- API
- データソース？
Bubble
- Zapier
- API

---
- Zapierというサービスを使えば、案内に従って操作することで、簡単に外部サービスを連携させられます。試してみましょう。
  https://zapier.com/apps/adalo/integrations

---
ZapierでAdaloと連携させることが可能な外部サービスの例
- Google Spreadsheet
- Google Calender
- Slack
- Zoom
- Twitter
- Instagram
- Spotify
- Bubble
- Google Meet
- Strava


---
外部連携で作るものの
- Instagramの投稿(Adalo)
- Twitterの投稿(Bubble)
- +α ベストエフォートで、複数サービスとの連携?

その他の候補
- Youtube連携
- Spotifyのプレイリストなど、自分の考えや好きなものを集約したページを作る(ユーザーごとに連携先サービスへの認証をさせる必要がある)
- 超調整さん(Adaloで作ったフォームで入力したイベントの出欠情報をGoogle Spreadsheetで一覧表示させる。Calendlyに負けそうではある。)
<!-- - 会議室予約管理システム(インターフェースはAdalo,データはGoogleCalender)
![bg right h:400px](images/2021-11-20-18-02-06.png) -->
- Zoom or meetの会議参加者管理システム
- facebook-groupsからポストを抽出して山田道場ホームページ？
- stravaで運動ログを ?

---
bubbleとのzapier連携
- notion


---
#### Adaloでの外部連携

---
やること

- Market Placeの外部連携コンポーネント
  - TODO: フリートライアル期間かどうかでMarket Placeのコンポーネント数が変わるのかは要確認
  - Youtube(固定の動画を見せられるだけ)
  - Twitter(アカウント名を入れたら、その人の投稿一覧が表示できる)
    - DBからアカウント名を動的に取得すると、エラー。。 ![](images/2021-11-26-05-42-47.png)
  - Google Sign-In (Google Developer Accountが有料なのでやらない: アカウントを作成するには、1 回限りの登録料として 25 ドルをお支払いいただく必要があります。アカウントの登録を完了するには、有効な身分証明書による本人確認が求められることがあります。ご本人であることを確認できなかった場合、登録料の払い戻しは行われません。)
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
  - 郵便番号 https://www.youtube.com/watch?v=7k4x2CaAbCI

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
Integromat
![](images/2021-11-25-23-10-17.png)

---
SheetDB
![](images/2021-11-26-03-42-06.png)

---

---
メモ
- APIの利用にクレジットカードが必要になる場合が多い
- DeepL
- GCP

-> 今橋が登録して、アクセスキーをシェアする？
---
###### 外部コレクション


---



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
## ノーコードツールでの共同作業のTips
---
#### (再掲)
- チームメンバーと一つのアプリを共同編集するには、Settings > AppAccess > Add Team Member > Invite New Team Memberを選択してチームメンバーのメールアドレスを入力しましょう。

![bg right h:600px](images/2021-11-04-20-14-37.png)

---
※ 他のメンバーと同時に一つのアプリを編集する際、他の人が行った編集は自分の画面にリアルタイムで反映されません。(リロードが必要なようです)

※ 同時に複数人が同じ画面を編集すると、先に行われた編集が後から行われた編集に上書きされてしまいます。それぞれが別の画面を編集するか、みんなで同じPCを見ながら一緒に編集しましょう。



---
- Bubbleは複数人が同じアカウントで同じ画面を同時編集しても、もう1人の画面にリアルタイムで反映される
- 同じエレメントに対する編集は、後勝ち
- 画面さえ分ければ、難なく開発できそう
- データベースもWorkflowも他の人の操作がリアルタイムで反映されるので、消えてしまうことはなさそう。 

---
- Adaloだと、同じ画面を同時編集したら、リアルタイムでは反映されないし、最後に編集した人の画面の状態になる。(別コンポーネントを編集していても、その編集は取り消される)
- 別画面の同時編集なら、どちらも保存される。
- 画面ごとの分担は必須になるけど、共同編集もできなくはなさそう。
- 他の人の担当画面をうっかり触ってしまわないように、画面を話して開発する　といったコツは必要になりそう。
- DatabaseへのCollection追加も、同時編集したら、最後に編集した人の状態で上書きされる(先に追加したCollectionは消える)
- Actionも同じ画面に同時に追加すると、後の方だけが保存される。 (edited) 

---
TODO: 共同編集について検証した内容を実演して見せられるようにする

---
###### 共同編集のルール
Bubbleは、同じエレメントの同時操作はダメなので、それを起こさないために、同じ画面の同時編集はやめましょう。
Adaloは、同じ画面を同時操作すると消えてしまうので、同じ画面の同時編集はやめましょう。データベースも、誰か1人が更新するようにしましょう。

---
モブプログラミングの紹介?
- ドライバーとナビゲーターみたいなお話を盛り込む？
---
## 共同作業演習
DevelopmentPhaseのチームで、新たに一つアプリを開発してみてください。
DevelopmentPhaseで開発予定のアプリとは異なるアプリにしましょう。
AdaloかBubbleのどちらを使うかは自由です。
DevelopmentPhaseで使う予定の方を選んでも良いですし、両方を選んでも良いです。
全員が手を動かすようにしましょう (画面を分担する、ドライバーとナビゲーターは15分毎に交代するなど)

---
分担のやり方の例
- データベース設計は最初にみんなでやろう
- 登録画面担当、一覧画面担当、詳細画面担当を決めよう
など

---
## ふりかえり

---
# 以上です！
# お疲れさまでした！
