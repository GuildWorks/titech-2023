---
marp: true
theme: gaia
size: 16:9
header: '　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　Copyright Ryo Imahashi'

page_number: true
paginate: true
---

**Programming Boot Camp**

# Adaloの基本

**東京工業大学 2021/10/23**
　
　
　
　
　
　　　　　　　　　　　　　　　　　　　　　　　　**Ryo Imahashi**

---
## 目次
  - Adaloとは
  - Adaloに登録しよう
  - テンプレートアプリを操作してみよう
  - Adaloでのアプリ開発の概要説明
  - アプリを作ってみよう
  - 演習
  - 時間が余れば話したいこと
  - 次回に向けて

---
## Adaloとは
- [Adalo](https://www.adalo.com/)は、アメリカ発のノーコードツールです。プログラミング不要でアプリを開発することができます。
- 用意されているパーツから使用したいものを選び、それを画面にドラッグ＆ドロップしていくことで、アプリを作ることが可能です。
- ブラウザで表示するWebアプリだけでなく、AndroidやiOS向けのスマートフォンアプリも開発できます。開発したアプリのGooglePlayやAppStoreでの公開も可能です。


---
#### Adaloで作られたアプリの例
- Union: https://union-jp.site/
  - 大学生が開発した、大学生・大学院生・大学教員・大学職員限定のSNS
  - 2021年に1,000万円の資金調達を実施している
    - https://prtimes.jp/main/html/rd/p/000000001.000076669.html
- その他にも、 #MadeInAdalo でたくさん紹介されています
  - https://www.adalo.com/made-in-adalo
---
## Adaloに登録しよう
- AdaloのSignUp画面にアクセスしてください
  - https://app.adalo.com/signup
![w:800px](images/signup.png)

---
- 無料で登録できます
- ご自身のEメールアドレス、パスワード、フルネームを入力してください
- 利用規約への同意のチェックを入れてください
- LET'S DO THIS! ボタンを押して、次の画面に進んでください

---

#### 参考: [無料プラン](https://www.adalo.com/pricing)の制限
<!-- ![w:900px](images/pricing.png) -->
- 外部アプリケーションとの連携ができない
  - ただし、14日間はトライアル利用が可能
- ドメインを変更できない(Adaloのドメインになる)
- ロゴの変更ができない(Adaloのロゴが表示される)
- GooglePlayやAppStoreへの申請ができない
- 1つのアプリで登録できるデータベースのレコード数の上限が50件

:white_check_mark: 実際にサービスを運用していく際は、有料プランへの移行を検討してください

---
#### プラットフォームの選択
- Native Mobile AppとDesktop Web Appが選べます
- 今回は、Native Mobile Appを選択しましょう
![bg 90% right](images/select-native-mobile-app.png)
---
#### テンプレートの選択
- 完成されたアプリがテンプレートとして提供されています
- 今回は、Chatを選択しましょう
![bg 90% right](images/select-chat-template.png)


---
#### ブランディング

- App Name、Primary Color、Secondary Colorを自由に入力してください
  - Primary Colorは、アプリで最も使われるベースになる色です
  - Secondary Colorは、目立たせたい時に使う色です。重要なボタンなどに使われます。
![bg 90% right](images/branding-chat-app.png)
<!-- - ADVANCED OPTIONSは変更せず、そのままで大丈夫です -->
---
- このようなAdaloの管理画面が表示されたらOKです
- 今後はこの管理画面を使って、アプリを開発していきます
![w:900px](images/dev-tool-of-chat-app.png)

---
## テンプレートアプリを操作してみよう
- まずはAdaloで作ったアプリがどのように動作するかを確認するために、先ほど選択したChatアプリを操作してみましょう
- 画面右上のPreviewボタンをクリックしてください

![w:1100px](images/preview-button.png)

---
- プレビュー画面が起動します
- 一緒にChatアプリを操作してみましょう
![w:800px](images/chat-app-preview.png)

---
- Signupしましょう
  - EmailとPasswordはメモしておいてください(後で使います)
![bg 50% right](images/chat-app-signup.png)

---
- まだ会話が行われていないため、リストが空の状態です
- 画面右下の + ボタンを押してみましょう
![bg 50% right](images/chat-app-no-conversation.png)

---
- 作成したばかりのアプリで他のユーザーがいないため、Chatができないようです。。
![bg 50% right](images/no-other-chat-app-user.png)

---
- 作ったアプリを他の人にシェアして会話してみましょう
- Previewモードを左上の×ボタンで閉じて、メニューにあるSHAREをクリックしてください

![w:1100px](images/share-button.png)

---
- SHARE APPボタンをクリックして、COPY LINKを選択してください
- コピーしたリンクを、参加者全員が見られるところ(Slack?Zoom?)に投稿しましょう
![w:800px](images/share-chat-app.png)

---
- 他の人の投稿したリンクをクリックしてその人のアプリにSignupし、メッセージを送りましょう
  - ユーザーのリストにアプリの作成者(と他の登録者)が表示されると思います
![bg 50% right](images/start-conversation.png)

---
- (みんなのアプリにメッセージが送られたであろう頃に、)
自分のアプリのPreview画面をもう一度表示してください
  - メッセージが届いているはずなので、クリックして表示してみましょう
![w:800px](images/preview-got-new-message.png)

---
- メッセージが受信できました :tada:
![bg 50% right](images/messages.png)

---
- 今回試したChat以外にも、いくつかのテンプレートが提供されています。
- 自分たちが作りたいアプリに近いものがあれば、そのテンプレートを流用して開発スピードをアップさせられるかもしれません。時間がある時に、他のテンプレートも試してみましょう。

---
## Adaloでのアプリ開発の概要説明
次に、Adaloでのアプリ開発の概要を説明していきます。

---
### 3つの基本コンセプト
- 基本となる以下3つのコンセプトについて紹介します
  - Components
  - Database
  - Actions

--- 
#### Components
- ユーザーインターフェースを作るために画面上に配置される要素。
- 例:
  - リスト
  - ボタン
  - テキスト
  - 画像
![bg 35% right](images/components.png)

---
#### Database
- 整理されたデータの集合。
- データの登録、読込(表示)、更新、削除が行われる。
- 例: Chatアプリの場合
![w:400px](images/2021-10-19-23-49-03.png)
<!-- ![w:570px](images/2021-10-19-23-39-29.png) -->
![bg 35% right](images/2021-10-19-23-13-47.png)

---
#### Actions
- 特定のコンポーネントをクリックした時に何を行うかを指定するために使われる。
<!-- - コンポーネントとそこで表示するデータベース内のデータを紐付けたり、ユーザー体験をカスタマイズする。 -->
- 例:
  - 別の画面に遷移させる
  - データベースのデータを登録、更新、削除する
![bg 35% right](images/2021-10-19-23-12-42.png)

---
### Adaloの機能説明
次に、Adaloの管理画面で利用できる機能を紹介していきます
![w:900px](images/dev-tool-of-chat-app.png)

---
#### Canvas
- 画面を作る作業領域
- 要素を選択したり、ドラッグアンドドロップで動かしたりできる
![w:680px](images/canvas.png)
<!-- - スクロール、拡大、縮小ができる -->
<!-- ![w:650px](images/2021-10-19-23-57-52.png) -->

---

#### Left Toolbar
左側のツールバーの各機能を紹介します。

![w:60px](images/left-tool-bar.png)

---
###### ![w:60px](images/add-panel.png) Add Panel
- コンポーネントや画面を選択してアプリに追加できる
![bg right 95%](images/2021-10-20-00-37-54.png)
![bg right 93%](images/2021-10-20-00-44-42.png)
<!-- 画面とコンポーネントの追加を実演する -->
---
###### ![w:60px](images/2021-10-20-00-52-07.png) Branding
- 色やフォントを変えられる
![bg right 100%](images/2021-10-20-00-50-02.png)
![bg right 92%](images/2021-10-20-00-50-42.png)
<!-- 色とフォントの変更を実演する -->
---
###### ![w:60px](images/2021-10-20-00-54-44.png) Screens
- 画面の一覧や、その画面の構成を表示できる
![bg right 100%](images/2021-10-20-01-18-20.png)
![bg right 93%](images/2021-10-20-01-14-53.png)

---
###### ![w:60px](images/2021-10-20-01-20-56.png) Database
- データベースの構成や保存されているデータを表示できる
- Collection: 同じ属性(プロパティ)を持ったデータの集まり
![w:214px](images/2021-10-20-01-38-57.png) ![w:878px](images/2021-10-20-01-30-09.png)

---
###### ![w:60px](images/2021-10-20-01-45-09.png) Settings 
- アプリの名前を変えたり、アプリのアイコンを設定したりできる
- キャンバスに関する表示設定ができる
- アプリへのアクセス権限の設定ができる
- アプリの複製や削除ができる
![bg right 90%](images/2021-10-20-01-47-47.png)

---
###### ![w:60px](images/2021-10-20-01-56-00.png)Publish
- 作ったアプリを公開できる(有料プランのみ)
![bg right 90%](images/2021-10-20-01-59-11.png)

---
###### ![w:60px](images/2021-10-20-02-06-34.png) Analytics
- 利用状況を分析したレポートを見ることができる
![bg right 90%](images/2021-10-20-02-07-44.png)

---
#### Top Bar
上部のツールバーの各機能を紹介します。

![w:1150px](images/2021-10-20-02-11-14.png)

---
###### App Switcher
- 開いているアプリの名前が表示される
- アプリを切り替えられる
- 新しいアプリを追加できる

![bg right 90%](images/2021-10-20-02-27-22.png)


---
######  Preview
- アプリを実行して試すことができる
- 画面サイズの異なるデバイスに切り替えて表示の確認ができる
![w:830px](images/2021-10-20-02-42-08.png)

---
###### Share
- アプリをシェアして他の人に使ってもらうことができる。
  Adaloのアカウントを持っていない人でも利用可能。
![w:830px](images/2021-10-20-02-44-28.png)

---
###### Account Menu
- 各種設定ができる
- ヘルプやドキュメントを開ける
- ログアウトできる
![bg right 90%](images/2021-10-20-02-56-33.png)
---
#### 開発に役立つTipsを覚えておこう
- 間違って編集してしまった時は、Windowsなら`Ctrl + Z`、Macなら `Command + Z ` で元に戻せます
- Adaloの開発ツールでは、日本語の直接入力がうまくいかないことがあります。日本語のテキスト入力はコピー＆ペーストで行ってください。

TODO: 他にもあれば追加

---
## アプリを作ってみよう
次に、新しくアプリを作ってみましょう。

<!-- 
データベースにはあまり触れずに作るには？
  - 静的サイトとして作る？
  - データベースは作成済みのテンプレートをクローンしてもらう？ -->

- 今回のレクチャーでは、データベースを使わない静的な(いつどのユーザーがアクセスしても表示される内容が変わらない)画面を作成します。
- 次回のレクチャーで、データベースを使った動的な(ユーザー毎に表示される内容が変わる)画面に仕上げていきます。

---
#### 作りたいアプリのUI
ペットの健康管理アプリを作ってみましょう。
まずはUIを確認していきます。

![h:385px](images/2021-10-20-05-02-23.png)![h:385px](images/2021-10-20-05-06-03.png)![h:385px](images/2021-10-20-04-40-45.png)![h:385px](images/2021-10-20-04-35-13.png)![h:385px](images/2021-10-20-04-36-11.png)![h:385px](images/2021-10-20-04-36-37.png)
<!-- ![h:380px](images/2021-10-20-04-37-19.png) -->


---
###### 会員登録画面
- 以下の項目を入力して会員登録できる
  - Email
  - Password
  - Full Name
- 会員登録済の人向けに、ログイン画面へのリンクがある
![bg right h:700px](images/2021-10-20-05-02-23.png)

---
###### ログイン画面
- 以下の項目を入力してログインできる
  - Email
  - Password
- パスワードを忘れた人向けのリンクがある
- 会員登録画面へのリンクがある
![bg right h:700px](images/2021-10-20-05-06-03.png)

---
###### ペット登録画面
- 名前を入力できる
- 写真を選択できる
- 誕生日を入力できる
- 登録ボタンで確定できる
![bg right h:700px](images/2021-10-20-04-40-45.png)

---
###### ペット一覧画面
- 登録したペットが一覧で表示できる
- 右下のアイコンを押すと、ペット登録画面に遷移できる
![bg right h:700px](images/2021-10-20-04-35-13.png) 

---
###### ペット詳細画面
- 健康記録画面へのリンクがある
- 活動記録画面へのリンクがある
- 誕生日が表示される
- (最新の)体重が表示される
![bg right h:700px](images/2021-10-20-04-36-11.png)

---
###### 健康記録画面
- 体重の遷移を示すグラフが表示される
- 現在の体重を登録できる
![bg right h:700px](images/2021-10-20-04-36-37.png)

<!-- ---
###### 活動記録画面
- 
![bg right h:700px](images/2021-10-20-04-37-19.png) -->


---
#### アプリを新規作成
それでは、実際にアプリを作っていきます。

- CREATE NEW APPを選択してください
![bg right 90%](images/2021-10-20-05-31-12.png)

---
- Native Mobile Appを選択してください
![bg right 90%](images/select-native-mobile-app.png)

---
- テンプレート: Blankを選択してください
![bg right 90%](images/2021-10-20-05-35-47.png)

---
- App Name、Colorを自由に決めてください
- Teamはデフォルトのままで良いです
  (Teamを設定していない人には表示されません)
![bg right 90%](images/2021-10-20-05-40-11.png)

---
- アプリができました
![h:550px](images/2021-10-20-05-45-06.png)

---
#### 画面を作ろう
- 以下6つの必要な画面を作成していきます。

会員登録画面、ログイン画面、ペット登録画面、ペット一覧画面、ペット詳細画面、健康管理画面
![h:385px](images/2021-10-20-05-02-23.png)![h:385px](images/2021-10-20-05-06-03.png)![h:385px](images/2021-10-20-04-40-45.png)![h:385px](images/2021-10-20-04-35-13.png)![h:385px](images/2021-10-20-04-36-11.png)![h:385px](images/2021-10-20-04-36-37.png)

---
###### 会員登録画面、ログイン画面

:white_check_mark: 会員登録画面、ログイン画面はデフォルトで生成されるようになっています。
![h:400px](images/2021-10-20-05-53-24.png)

---
プレビュー機能で動作を確認してみましょう。

- 会員登録画面
  - 会員登録をすると、Home画面に遷移します
  - Home画面右上のアイコンからログアウトしましょう
![bg right h:600px](images/2021-10-20-06-09-56.png)
![bg right h:600px](images/2021-10-20-06-11-03.png)

---
- ログイン画面
  - 先程会員登録したのと同じEmail、Passwordでログインすると、Home画面に遷移します

![bg right h:600px](images/2021-10-20-06-16-03.png)
![bg right h:600px](images/2021-10-20-06-11-03.png)

---
会員登録画面、ログイン画面はそのままで問題ないことがわかりました。
その他の4画面を作成していきましょう。

---
###### ペット登録画面
- 名前を入力できる
- 写真を選択できる
- 誕生日を入力できる
- 登録ボタンで確定できる

こちらの画面を作りましょう
![bg right h:700px](images/2021-10-20-04-40-45.png)

---
- ADD SCREENからFormを選択します
![bg right h:700px](images/2021-10-20-06-26-12.png)

---
- Screen Nameを入力します
![w:900px](images/2021-10-20-06-28-11.png)


---
画面が追加されました。

![bg right h:700px](images/2021-10-20-06-30-39.png)


---
###### ペット一覧画面
- 登録したペットが一覧で表示できる
- 右下のアイコンを押すと、ペット登録画面に遷移できる
![bg right h:700px](images/2021-10-20-04-35-13.png) 

---
###### ペット詳細画面
- 健康記録画面へのリンクがある
- 活動記録画面へのリンクがある
- 誕生日が表示される
- (最新の)体重が表示される
![bg right h:700px](images/2021-10-20-04-36-11.png)

---
###### 健康記録画面
- 体重の遷移を示すグラフが表示される
- 現在の体重を登録できる
![bg right h:700px](images/2021-10-20-04-36-37.png)

---


---

---
## 演習
TODO

--- 
#### 演習の回答

TODO

---
## 時間が余れば話したいこと
- Home画面、Welcome画面の設定
- 他のテンプレートの紹介

---
## まとめ
:white_check_mark: 

---
## 次回に向けて

TODO

---
# 以上です！
# お疲れさまでした！
---
## 参考
- [Adalo Resourcesメモ](https://www.notion.so/Adalo-Resources-3b58f37ac0894b038c30d6b0d8274370)
- https://hashikake.jp/articles/adalo-no-code-app-creation-platform-ep01
- https://www.no-code.tv/course/nocode135

---
メモ
- [1対1のリレーションがないことについて](https://help.adalo.com/database)
>While One-to-One relationships do not exist in Adalo, sometimes it is necessary to adapt the One-to-Many relationship type for this purpose. These instances are rare, but do crop up from time to time. For example, if an event host can only be assigned one event at a time and the event can only have one host. The "Many" side of the relationship can be disregarded.
- [配色](https://note.com/tomokortn/n/n0d3d9da16907)