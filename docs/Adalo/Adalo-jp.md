---
marp: true
theme: gaia
size: 16:9
header: '　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　Copyright Ryo Imahashi'

page_number: true
paginate: true
---

**Programming Boot Camp**

# Adaloでのアプリ開発と外部連携

**東京工業大学 2023/11/3**
　
　
　
　
　
　　　　　　　　　　　　　　　　　　　　　　　　**Ryo Imahashi**

---
## 目次
  - Adaloとは
  - Adaloに登録しよう
  - テンプレートアプリを操作してみよう
  - Adaloでのアプリ開発の概要説明
  - アプリを作ってみよう
  - サンプルアプリを改善しよう
  - 外部連携
  - まとめ

---
## Adaloとは
- [Adalo](https://www.adalo.com/)は、アメリカ発のノーコードツールです。プログラミング不要でアプリを開発することができます。
- 用意されているパーツから使用したいものを選び、それを画面にドラッグ＆ドロップしていくことで、アプリを作ることが可能です。
- ブラウザで表示するWebアプリだけでなく、AndroidやiOS向けのスマートフォンアプリも開発できます。開発したアプリのGooglePlayやAppStoreでの公開も可能です。
- シンプルで分かりやすいので、ノーコード開発を初めて学ぶためのツールに適しています。

--- 
#### 注意点
- 一つのアプリを複数人で同時編集するのが難しく、Development Phaseでのチーム開発に利用するのはあまりおすすめできません
  - ただし、画面の開発を担当するのが1人だけで、それ以外のメンバーは全員APIの開発を担当するという分担であれば、問題なく使えます


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
![w:600px](images/signup.png)
- 使用するブラウザは、Google Chromeを推奨します
  - インストール: https://www.google.com/intl/ja_jp/chrome/

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
<!-- - ドメインを変更できない(Adaloのドメインになる)
- ロゴの変更ができない(Adaloのロゴが表示される)
- GooglePlayやAppStoreへの申請ができない -->
- 1アプリで登録できるデータベースのレコード数の上限が200件
- 月間アクション(ボタンクリック時等に行われる処理)回数の上限が1000回

:white_check_mark: 実際にサービスを運用していく際は、有料プランへの移行を検討してください

---
- 利用目的を聞かれるので、 For teaching or taking a class を選択して、Go Build Apps! ボタンを押してください
![w:900px](images/2023-10-29-13-06-38.png)

---
#### プラットフォームの選択
- Responsive AppとMobile Onlyが選べます
- PCとMobileの両方に対応できる、Responsive Appを選択しましょう

![bg 90% right](images/2023-10-29-13-09-34.png)

---
#### テンプレートの選択
- 完成されたアプリがテンプレートとして提供されています
- 今回は、Chatを選択しましょう
![bg 90% right](images/2023-10-29-13-34-34.png)

<!-- - ADVANCED OPTIONSは変更せず、そのままで大丈夫です -->

---
#### ブランディング

- App Name、Primary Color、Secondary Colorを自由に入力してください
  - Primary Colorは、アプリで最も使われるベースになる色です
  - Secondary Colorは、目立たせたい時に使う色です。重要なボタンなどに使われます。
![bg 90% right](images/2023-10-29-13-36-48.png)

---
- このようなAdaloの管理画面が表示されたらOKです
- 今後はこの管理画面を使って、アプリを開発していきます
![w:900px](images/2023-10-29-13-37-30.png)

---
## テンプレートアプリを操作してみよう
- まずはAdaloで作ったアプリがどのように動作するかを確認するために、先ほど選択したChatアプリを操作してみましょう
- 画面右上のPreviewボタンをクリックしてください

![w:1100px](images/preview-button.png)

---
- プレビュー画面が起動します
- 一緒にChatアプリを操作してみましょう
![w:800px](images/2023-10-29-14-41-39.png)

---
- Signupしましょう
  - EmailとPasswordはメモしておいてください(後で使います)
![w:900px](images/2023-10-29-14-44-05.png)


---
- まだ会話が行われていないため、リストが空の状態です
- 画面右上の NEW CHAT ボタンを押してみましょう
![w:900px](images/2023-10-29-14-46-41.png)

---
- サンプルユーザーのリストが表示されます
- Will Wを選んでクリックしてください
![w:900px](images/2023-10-29-14-48-59.png)

---
- メッセージを送信できます
![w:900px](images/2023-10-29-14-50-08.png)

---
他にも以下のような機能がありますので、試してみましょう。
- プロフィール写真の更新
- パスワードの変更
- ログアウト
- ログイン
  - 以下のように入力すると、サンプルユーザーの Will W としてログインができます
    - Email: will@email.com
    - Password: 123

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
![w:400px](images/2023-10-29-15-08-00.png)
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
![w:900px](images/2023-10-29-15-10-32.png)

---
#### Canvas
- 画面を作る作業領域
- 要素を選択したり、ドラッグアンドドロップで動かしたりできる
![w:670px](images/2023-10-29-15-11-49.png)
<!-- - スクロール、拡大、縮小ができる -->
<!-- ![w:650px](images/2021-10-19-23-57-52.png) -->

---

#### Left Toolbar
左側のツールバーの各機能を紹介します。

![w:70px](images/2023-10-29-15-13-02.png)

---
###### ![w:60px](images/add-panel.png) Add Panel
- コンポーネントや画面を選択してアプリに追加できる
- 機能のテンプレートを追加することも可能
![bg right 95%](images/2023-10-29-15-16-43.png)
![bg right 95%](images/2023-10-29-15-17-09.png)
<!-- 画面とコンポーネントの追加を実演する -->
---
###### ![w:60px](images/2021-10-20-00-52-07.png) Branding
- 色やフォントを変えられる
![bg right 98%](images/2023-10-29-15-25-23.png)
![bg right 94%](images/2023-10-29-15-25-47.png)
<!-- 色とフォントの変更を実演する -->

---
###### ![w:60px](images/2021-10-20-00-54-44.png) Screens
- 画面の一覧や、その画面の構成を表示できる
![bg right 100%](images/2023-10-29-15-26-42.png)
![bg right 93%](images/2023-10-29-15-27-37.png)

---
###### ![w:60px](images/2021-10-20-01-20-56.png) Database
- データベースの構成や保存されているデータを表示できる
- Collection: 同じ属性(プロパティ)を持ったデータの集まり
![w:200px](images/2023-10-29-15-29-22.png) ![w:850px](images/2023-10-29-15-30-54.png)

---
###### ![w:60px](images/2021-10-20-01-45-09.png) Settings 
- アプリの名前やアイコンを設定できる
- キャンバスに関する表示設定ができる
- アプリへのアクセス権限の設定ができる
- アプリの複製や削除ができる
- 位置情報機能を使うためのAPIキーの設定ができる
![bg right 80%](images/2023-10-29-15-32-03.png)

---
###### ![w:60px](images/2021-10-20-01-56-00.png)Publish
- 作ったアプリを公開できる(有料プランのみ)
![bg right 90%](images/2023-10-29-15-33-39.png)

---
###### ![w:60px](images/2021-10-20-02-06-34.png) Analytics
- 利用状況を分析したレポートを見ることができる
![bg right 95%](images/2023-10-29-15-34-38.png)

---
###### ![w:60px](images/2022-11-02-08-01-35.png) Version History
- バージョン履歴を作成したり、アプリをバージョン履歴作成時と同じ状態に戻すことができる(有料プランのみ)
![bg right 80%](images/2022-11-04-23-29-30.png)

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
######  Preview, Share
- アプリを実行して試すことができる
![w:930px](images/2023-10-29-15-36-52.png)

---
###### Account Menu
- 各種設定ができる
- ヘルプやドキュメントを開ける
- Adaloのエキスパートを探せる
- ログアウトできる
![bg right 90%](images/2023-10-29-15-41-03.png)

---
#### 開発に役立つTipsを覚えておこう
- 間違って編集してしまった時は、Windowsなら`Ctrl + Z`、Macなら `Command + Z ` で元に戻せます
- Adaloの開発ツールでは、日本語の直接入力がうまくいかないことがあります。日本語のテキスト入力はコピー＆ペーストで行ってください。


<!-- ---
## チュートリアル
Learn Adaloのコンテンツをやってみる？ -->

---
## アプリを作ってみよう
次に、新しくアプリを作ってみましょう。


---
#### 作りたいアプリのUI
ペットの健康管理アプリを作ってみましょう。
まずはUIを確認していきます。

![h:383px](images/2023-11-02-18-52-28.png) ![h:383px](images/2023-11-02-18-53-10.png) ![h:383px](images/2023-11-02-18-47-35.png) ![h:384px](images/2023-11-02-18-48-18.png) ![h:383px](images/2023-11-02-18-50-07.png) ![h:383px](images/2023-11-02-18-50-36.png)


---
###### 会員登録画面
- 以下の項目を入力して会員登録できる
  - Email
  - Password
  - Full Name
- 会員登録済の人向けに、ログイン画面へのリンクがある
![bg right h:700px](images/2023-11-02-18-52-28.png)

---
###### ログイン画面
- 以下の項目を入力してログインできる
  - Email
  - Password
- パスワードを忘れた人向けのリンクがある
- 会員登録画面へのリンクがある
![bg right h:700px](images/2023-11-02-18-53-10.png)

---
###### ペット登録画面
- 名前を入力できる
- 写真を選択できる
- 誕生日を入力できる
- 登録ボタンで確定し、ペット一覧画面に遷移できる
![bg right h:700px](images/2023-11-02-18-47-35.png)

---
###### ペット一覧画面
- 登録したペットが一覧で表示できる
- ペットをクリックすると、そのペットのペット詳細画面に遷移できる
- 右下のアイコンを押すと、ペット登録画面に遷移できる
![bg right h:700px](images/2023-11-02-18-48-18.png)

---
###### ペット詳細画面
- 誕生日が表示される
- 最新の体重が表示される
- 体重記録画面へのリンクがある
![bg right h:700px](images/2023-11-02-18-50-07.png)


---
###### 体重記録画面
- 体重の遷移を示すグラフが表示される
- 現在の体重を入力できる
- ボタンを押して体重を追加できる
![bg right h:700px](images/2023-11-02-18-50-36.png)


---
#### アプリ作成
それでは、実際にアプリを作っていきます。

- CREATE NEW APPを選択してください
![bg right 95%](images/2023-10-29-18-03-42.png)

---
- Responsive Appを選択してください
![bg right 95%](images/2023-10-29-18-04-45.png)

---
- テンプレート: Blank Mobile First を選択してください
![bg right 95%](images/2023-10-29-18-05-48.png)

<!-- モバイルを提供するのであれば、まずモバイルから始めることをお勧めします。画面を小さくするよりも、画面を大きくしてコンポーネントを並べ替える方が簡単です。このシナリオでは、コンポーネントがモバイルの画面からはみ出す傾向があります。 -->
<!-- We definitely recommend starting with mobile first if you plan to offer it. It's easier to make screens bigger and rearrange components, than it is to make them smaller - components tend to hang off the mobile screen in that scenario. -->



---
- App Name、Users of this app、Colorを自由に決めてください
![bg right 95%](images/2023-10-29-18-07-55.png)

---
- アプリができました
![h:550px](images/2023-11-01-07-56-10.png)


---
#### データベースを学ぼう
アプリ開発の最初にそのアプリで扱うデータを定義しておくことで、その後の開発をスムーズに進めることができます。

まずは、データベースがどのようなものかを確認します。

---
###### Database(復習)
- 整理されたデータの集合。
- データの登録、読込(表示)、更新、削除が行われる。
- 例: Chatアプリの場合
![w:400px](images/2023-10-29-15-08-00.png)
<!-- ![w:570px](images/2021-10-19-23-39-29.png) -->
![bg 35% right](../Adalo1/images/2021-10-19-23-13-47.png)

---
- データベースはよく「表計算ソフトのようなもの」と例えられます。
- データベースを使ってデータを作成(CREATE)、読み取り(READ)、更新(UPDATE)、削除(DELETE)することができます。 これらの操作を総称してCRUDと呼びます。

![bg right w:630px](images/2023-11-01-21-39-53.png)

---
###### Adaloのデータベースの基本
![w:60px](../Adalo1/images/2021-10-20-01-20-56.png) このアイコンからAdaloのデータベースにアクセスできます。
Adaloのデータベースの構成要素は、以下の3つです。
- Collection
- Property
- Record

---
###### Collectionとは
同じ属性(Property)を持ったデータの集まり
![w:250px](images/2023-11-01-21-38-02.png) ![w:700px](images/2023-11-01-21-39-53.png)

---
- Collectionは、データベースで扱う様々なデータをデータの種類ごとに分割し、整理するためのものです。(類似の言葉として、テーブルがあります)
- ユーザーが1度の操作で登録や更新、削除といった操作をするデータのまとまりがCollectionになることが多いです。<!-- (名詞として表現できるものがCollectionになることが多いと言われます) -->
- デフォルトでは、UsersがCollectionとして用意されており、それ以外は開発するアプリに合わせて追加していきます。

※ どのようなCollectionを追加するかを決めるのはとても難しいです。練習しながら慣れていきましょう。(悩んだ時は、メンター陣に相談するのもおすすめです)

---
###### Recordとは
- Recordは、Collection内へ情報を保存する際の単位です。
  - 画像の1行が1つのRecordとなります。
- Users Collectionの例では、1人のユーザーが持つ情報をまとめて1Recordとして登録します。
![w:550px](images/2023-11-01-21-39-53.png)

---
- Recordは基本的にアプリの画面上のフォームから登録できるようにしますが、Recordの表示中に右上の「+Add xxxx」ボタンを押して、右の画像のようなフォームから登録することも可能です。
- Collection内のRecordの検索や、CSVファイルのアップロード(インポート)・ダウンロードも可能です。
![bg right h:460px](images/2023-11-01-21-41-59.png)

---
###### Propertyとは
- Propertyは、Recordを構成する一つ一つの項目です。
- Users Collectionは、Eメール、パスワード、ユーザー名、氏名といったPropertyで構成されます。
- Propertyの値は空で登録される場合もあります。

![bg right h:450px](images/2021-11-05-16-25-58.png)

---
Propertyがどのようなデータかを定義するため、Property追加時はTypeを選択します。
- Text
- Number
- True/False
- Date/Time
- Date
- Image
- File
- Location

![bg right h:600px](images/2022-11-05-12-38-25.png)

---
Relationshipとは
- 1つのRecordに対して多数のPropertyを保存する代わりに、Relationshipと呼ばれる複数のCollectionを関連づけるための特別なPropertyを設定します。これにより、Collectionを扱いやすい形に分割することができます。

---
- 例えば、Chatアプリでユーザーが送信したメッセージはUsers Collectionとは別のMessages Collectionに保存され、これら2つのCollectionはRelationshipで関連づけられます。
  - Users側にはMessagesというRelationshipが、Messages側にはSenderという(Usersとの)Relationshipが登録されています。

![bg right h:450px](images/2023-11-01-21-45-10.png)
![bg right h:350px](images/2023-11-01-21-46-52.png)

---
Relationshipの種類
- AdaloのRelationshipでは、Collection間で紐付けられるRecordの数に応じて、1対多と多対多という2つの種類のいずれかを選択します。 

---
1対多のRelationship
- 1つのRecordが、別のコレクションにある複数のRecordと関係を持つことを意味します。 
- Relationshipを設定しようとしているCollectionを1と多のどちらにするかで、2種類の選択肢が現れます。

![bg right h:320px](images/2022-11-05-12-42-56.png)

---
1対多のRelationshipの例
- Chatアプリでは1人のユーザーが複数のメッセージを送信しますが、メッセージの送信者は1人のユーザーなので、Users CollectionとMessages CollectionのRelationshipは1対多になります。

![h:250px](images/2023-11-01-21-48-22.png) ![h:250px](images/2023-11-01-21-51-33.png)

<!-- 例えば、主催者がイベントに対して1人だけいる場合の、主催者とイベントのRelationshipは1対多です。 -->
<!-- 例えば、1人のユーザーが複数のイベントを主催したり、複数のイベントに1人の主催者がいたりしますが、どちらも真の1対多の関係を表しています。 -->

---
多対多のRelationship
- 両方のCollectionの1Recordが、もう一方のCollectionの複数のRecordに紐付けられることを意味します。

![bg right h:140px](images/2022-11-05-12-48-16.png)
<!-- ![bg right h:140px](images/2022-11-05-12-45-59.png) -->

---
多対多のRelationshipの例
- Chatアプリでは1人のユーザーが複数の会話(誰とどんなメッセージをやりとりしたかを管理するもの)を持ち、1つの会話には複数のメンバー(ユーザー)が所属するので、Users CollectionとConversations CollectionのRelationshipは多対多になります。

![h:260px](images/2023-11-01-21-53-05.png) ![h:260px](images/2023-11-01-21-53-42.png)

<!-- - 例えば、参加者は複数のイベントに参加できるし、イベントには複数の参加者がいるという場合の、参加者とイベントのRelationshipは多対多です。 -->
<!-- 例えば、イベントが複数のホストを持ち、ホストが複数のイベントを持つことが可能です。 -->
<!-- ---
「イベントには主催者が1人だけいる」「参加者は複数のイベントに参加できるし、イベントには複数の参加者がいる」と定義するリレーションを作りたいとします。そこで、選択肢を「User」という言葉で読むのではなく、「User」を「Host」という言葉に置き換えることで、どの選択肢を選べばよいのかをより明確にすることができます。この場合は、選択肢1となります。 もし、「参加者」と「イベント」の関係を作るとしたら、あなたはどちらを選びますか？ 実際に試してみてください。
>コレクションのレコードをクリックすると、そのコレクション内のレコードも表示されるので、リレーションシップを含むプロパティは、Adaloのデータベースの列としても視覚化できます。 -->

---
#### データベース設計

<!-- ---
TODO: 演習の前に一度テンプレートのアプリを例にデータベース設計の手順を紹介して、一度流れを理解してもらう? -->

次に、実際にデータベースを設計しましょう。

---
###### データベースを設計してみよう
サンプルアプリのUIを見ながら、データベースを設計してみましょう。手順は次のページで紹介します。
![h:383px](images/2023-11-02-18-52-28.png) ![h:383px](images/2023-11-02-18-53-10.png) ![h:383px](images/2023-11-02-18-47-35.png) ![h:384px](images/2023-11-02-18-48-18.png) ![h:383px](images/2023-11-02-18-50-07.png) ![h:383px](images/2023-11-02-18-50-36.png)

---
###### データベース設計の手順
1. UIを見ながら、保存が必要になるデータをリストアップしましょう。テキストエディタ(メモ帳アプリ等)に書き起こしてください。
2. リストアップしたデータがどのようなCollectionに分類できるかを考えて、Adaloのデータベースに必要なCollectionを作成しましょう。
3. 1でリストアップしたデータを適切なCollectionにPropertyとして追加してください。その際、適切なTypeを選択してください。
4. 他のCollectionと関連を持つCollectionには、Relationship Propertyを設定しましょう。

--- 
※ 次のスライド以降に解説がありますが、答えを見る前に一度自分で手を動かして考えてみることをおすすめします。

※ 絶対的な正解はないです。悩んだら、直感に従って進めてみてください。

---
###### 解説
UIを見ながら、保存が必要になるデータをリストアップすると、以下のようになりました。
```
- ユーザーのEmail
- ユーザーのパスワード
- ユーザーのFullName
- ペットの名前
- ペットの写真
- ペットの誕生日
- ペットの体重
- ペットの体重の登録日時
```

- その他のデータを挙げられた人がいれば、教えてください！

<!-- ![](images/2021-11-03-13-57-56.png) -->

---
リストアップしたデータがどのようなCollectionに分類できるかを考えて、今回はこの3つに分類することにします。
```
- Users
- Pets
- PetWeightLogs
```

- ユーザーのCollectionとペットのCollectionの2つを用意した人は多いのではないでしょうか？
- ペットの体重記録のCollectionは用意しなかった人もいるかもしれません。(ペットの体重とその登録日時をペットのCollectionに含める方法も間違いではないです。後ほど解説します。)
- その他のCollectionの分類をした人はいますか？
<!-- 極論、1Collectionでもやれなくはないよ -->

---
Collectionの分類に関する補足
- 「Aが決まればBが1つに決まる」という関係が成り立つ時、AをCollectionに、BをそのCollectionのPropertyにする場合が多いです。
  - ユーザーが決まれば、ユーザーのEmail、パスワード、FullNameがそれぞれ1つに決まります。
  - ペットが決まれば、ペットの名前、写真、誕生日がそれぞれ1つに決まります。
- 「Aに対してBが複数存在する」という関係が成り立つ時、AとBは別々のCollectionに分割することが多いです。
  - (1匹の)ペットに対して、ペットの体重とその登録日時は複数存在します。

<!-- ※ TODO: 従属性についてわかりやすい言葉で解説 -->
<!-- コツは、関連性の強い複数のデータを一つに決めることができるものを、Collection名にする -->
<!-- ※ Email,パスワード、FullNameは、ユーザーが決まれば一つに決まるので、UsersというCollectionにまとめる。
※ ペットの名前、写真、誕生日は、ペットが決まれば一つに決まるので、PetsというCollectionにまとめる。 -->

<!-- ※ ペットの体重とその登録日時は同時に登録されるため、セットで扱う -->
<!-- ※ ペットの体重とその登録日時は、1匹のペットに対して複数登録されるので、Collectionを分ける(ペットとペットの体重が1対多の関係になる) -->

---
- CollectionをAdaloのデータベースに登録しておきます。
  - ADD TO DATABASE > Add Collectionから手動で追加してください
  - Magic Add は追加したい機能をテキスト入力するとAIがデータベースの変更を提案してくれますが、今回は使いません
  <!-- 追加したい機能をテキストで入力するとAIがデータベースの変更を提案してくれますが、毎回結果が異なるので、 -->
- Usersはデフォルトで作成されています。
![bg right h:550px](images/2023-11-01-22-10-13.png)

---
次に、1でリストアップしたデータを適切なCollectionの配下にPropertyとして追記すると、以下のようになりました。()の中は選択するTypeです。
```
- Users
  - Email(Text)
  - Password(※Password)
  - FullName(Text)
- Pets
  - Name(Text)
  - Image(Image)
  - Birthday(Date)
- PetWeightLogs
  - WeightKg(Number)
  - RegisteredTime(Date&Time)
```
※ Passwordはデフォルトで設定される特殊なTypeです。
<!-- Textを暗号化したものになります。 -->

---
- Adaloで実際にPropertyを追加します。
- Users Collectionはデフォルトで設定済みで、必要な項目は含まれています。
- Usernameは不要ですが、削除できないのでそのままにしておきます。
![bg right h:500px](images/2021-11-03-15-40-03.png)

---
- Pets CollectionのPropertyはこのようになります。
![bg right h:400px](images/2021-11-03-15-42-07.png)

---
- PetWeightLogs CollectionのPropertyはこのようになります。
- Collection追加時にデフォルトで設定されるName Propertyは不要なので、削除します。
  - ドラッグアンドドロップで順番がCollection内の一番上でなくなるように移動すれば、削除できます。

<!-- ![](images/2021-11-03-15-36-02.png) -->
![bg right h:300px](images/2021-11-03-15-45-14.png)

---
最後に、他のCollectionと関連を持つCollectionには、Relationship Propertyを設定します。

- Users Collectionを選択して、Pet Collectionとの1対多のRelationshipを追加します。
![w:530px](images/2021-11-03-15-50-06.png)

![bg right h:700px](images/2023-11-01-22-18-31.png)

---
- Pets Collectionを確認すると、Users Collection側でRelationshipの設定をしたので、自動でUsers CollectionとのRelationshipが追加されています。
  - Users Collection側が1なので、末尾のsが省略されて、Userという Property名になっています。

![bg right h:550px](images/2023-11-01-22-19-28.png)

---
- Pets Collectionに、PetWeightLogs CollectionとのRelationshipを追加します。
  - Pets Collectionを選択して、PetWeightLogs Collectionとの1対多のRelationshipを追加します。
![w:490px](images/2021-11-03-15-58-38.png)
![bg right h:700px](images/2023-11-01-22-20-54.png)

---
PetWeightLogs Collectionを確認すると、Pets Collection側でRelationshipの設定をしたので、自動でPets CollectionとのRelationshipが追加されています。
  - Pets Collection側が1なので、末尾のsが省略されて、Petという Property名になっています。

![bg right h:500px](images/2023-11-01-22-21-35.png)

---
参考: Pets Collectionにペットの体重とその登録日時を含めた場合どうなるか

以下のようにレコードが登録されますが、この場合、少し困ることが出てきます。
![w:1200px](images/2021-11-03-14-47-07.png)

---
困ること
- 1匹のペットに対して異なるペットの体重とその登録日時が結合されたRecordが複数登録されるため、ペットの情報(Name,Image,Birthday)が重複して登録されてしまう。
  - 1匹のペットの情報を変更するために、重複して登録されたRecordを全て更新しないといけなくなり、処理が複雑になる。
- Adaloには一つのCollectionを選んでそこにRecordを登録するためのフォームを自動生成する便利な機能があるが、データを登録する単位でCollectionが分かれていないので、それが使えなくなる。

---
データベース設計は以上です。

※ この後の作業で混乱しないために、Adaloのデータベースを資料と同じ状態に設定しておくことをおすすめします。

---
#### データベースを使ってアプリを開発しよう
設計したデータベースを使って、サンプルアプリを開発していきましょう。

---
###### 会員登録画面、ログイン画面

:white_check_mark: 会員登録画面、ログイン画面はデフォルトで生成されるようになっています。
- 画面右上のPREVIEWボタンをクリックして、プレビュー機能で動作を確認してみましょう。
![bg right h:600px](images/2023-11-01-07-59-08.png)


<!-- TODO: welcome画面を消す？ -->

---
Mobile Firstでアプリを作っていくため、ここからはブラウザの開発者ツールを使い、Mobileサイズでプレビューをします。
- Chromeの場合、以下の手順で開発者ツールを開きます
  - 右上の三点リーダ > More Tools > Developer Tools 
![h:400px](images/2023-11-01-08-30-43.png)

---
Chromeの開発者ツールでは、様々なデバイスの画面サイズで表示を確認することができます。
- iPhone 12 Proを選択してプレビューをします
![h:450px](images/2023-11-01-08-32-23.png)

---

- 会員登録画面
  - 会員登録をすると、Home画面に遷移します
  - ブラウザの戻るボタン(←)で戻り、 ALREADY HAVE AN ACCOUNT? をクリックしてログイン画面に遷移しましょう
![bg right h:600px](images/2023-11-01-08-37-06.png)
![bg right h:600px](images/2023-11-01-08-39-34.png)

---
- ログイン画面
  - 先程会員登録したのと同じEmail、Passwordでログインすると、Home画面に遷移します
![bg right h:600px](images/2023-11-01-08-42-17.png)
![bg right h:600px](images/2023-11-01-08-39-34.png)

---
会員登録画面、ログイン画面はそのまま使えることがわかりました。
- App Nameと表示されている部分を、自分が決めたアプリ名に変更しておきましょう。
![w:600](images/2023-11-02-19-01-02.png)

続いて、その他の4画面を作成していきましょう。

---
###### ペット登録画面
- 名前を入力できる
- 写真を選択できる
- 誕生日を入力できる
- 登録ボタンで確定し、ペット一覧画面に遷移できる

こちらの画面を作りましょう
![bg right h:700px](images/2023-11-02-18-47-35.png)

---
- ADD SCREENからBlank Mobile Firstを選択します
![bg right h:700px](images/2023-11-01-22-48-24.png)

---
- Screen Nameを入力します
![w:900px](images/2021-10-20-06-28-11.png)


---
Screenが追加されました。

この上に必要なコンポーネントを追加していきます。

![bg right h:700px](images/2023-11-01-22-51-44.png)

---
- ADD COMPONENTからApp Barを選択します
![bg right h:650px](images/2023-11-01-22-53-38.png)

---
- 画面上に配置します
![bg right h:700px](images/2023-11-01-22-54-12.png)

---
- Title > Textの値を画面名(PetRegistration)に変えます
![bg right h:700px](images/2023-11-01-22-55-53.png)

---
- ADD COMPONENTからFormを選択します
![bg right h:700px](images/2023-11-01-22-57-45.png)

---
- 画面上に配置します
![bg right h:700px](images/2023-11-01-22-59-55.png)

---
- Which data collection?でPetsを選択します
  - 選択したCollectionに合わせたフォームが自動生成されます
- What do you want the form to do?でCreate New petを選択します
![bg right h:450px](images/2023-11-01-23-06-42.png)

---
- FieldsのBirthdayとImageの順番をドラッグ&ドロップで入れ替えます
![bg right h:580px](images/2023-11-01-23-08-54.png)

---
- Submit ButtonのClickActionsにCreate Petが設定されていることを確認します
![bg right h:580px](images/2023-11-01-23-10-32.png)

---
まだ導線がなく、表示することができないので、表示できるようにしましょう
- ログイン状態の時に最初に表示されるHome Screenに設定します
  - Screensからペット登録画面を選び、Screen Navigation TypeをHome Screenに変更します
![bg right h:400px](images/2021-10-20-07-28-52.png)
---
- ログイン画面の Form > Submit buttonを開き、ClickActionsに設定されているLinkのScreenをペット登録画面に変更します
![bg right h:600px](images/2023-11-01-23-29-51.png)

---
ペット登録画面の動作を確認してみましょう。
- プレビュー機能でログインをすると、ペット登録画面が表示できます。
- 名前の入力、画像の選択、誕生日の選択ができます。
- CREATE PETボタンを押して、ペットを登録できます
![bg right h:700px](images/2023-11-01-23-34-29.png)

---
ペットの登録後、データベースのPets CollectionにRecordが登録されたらOKです。
![w:300](images/2023-11-01-23-37-16.png) ![w:800](images/2023-11-01-23-36-05.png)

これで、ペット登録画面は完成です。

---
###### ペット一覧画面
- 登録したペットが一覧で表示できる
- ペットをクリックすると、そのペットのペット詳細画面に遷移できる
- 右下のアイコンを押すと、ペット登録画面に遷移できる
![bg right h:700px](images/2023-11-02-18-48-18.png)

次は、こちらの画面を作りましょう

---
- ADD SCREENからBlank Mobile Firstを選択して、Screen Nameを入力します
![h:500px](images/2023-11-01-22-48-24.png) ![h:300px](images/2023-11-02-05-01-05.png)

---
- ADD COMPONENTからApp Barを選択して、画面上に配置します
- Title > Textの値を画面名(MyPets)に変えます
![bg right h:600px](images/2023-11-02-05-07-19.png)

---
- ADD COMPONENTからCard Listを選択して、画面上に配置します
![bg right w:600px](images/2023-11-02-05-10-27.png)

---
- What is this a list of?でPetsを選択します
- FilterでLogged In User > Petsを選択します
- Columnsの値を1に変更します
![bg right h:600px](images/2023-11-02-05-13-14.png)

---
- 不要なSubtitleとBodyのトグルをOFFにして、非表示にします
![bg right h:600px](images/2023-11-02-05-16-40.png)

---
次に、ペット登録画面への導線を追加します
- ADD COMPONENTからAction Buttonを選択してください
![bg right h:500px](images/2023-11-02-05-18-12.png)

---
- 画面右下に配置してください
- Icon and Text ColorをDefault Background(White)に変更してください
![bg right h:600px](images/2023-11-02-05-19-29.png)

---
- ADD ACTION -> Link -> PetRegistration を選択してください
- TransitionはNoneのままでOKです
![bg right h:500px](images/2023-11-02-05-20-09.png)

---
ペット登録画面からペット一覧画面への導線も追加しておきましょう
- ペット登録画面で Form > Submit Button を選択してください
- ADD ANOTHER ACTION -> Link -> MyPets を選択してください
![bg right h:500px](images/2023-11-02-05-24-39.png)

---
- SignUp画面のSIGNUPボタンとLogin画面のLOGINボタンの遷移先も、HomeからMyPetsに変更しておきましょう
![bg right h:450px](images/2023-11-02-05-26-39.png)

---
- デフォルトで作成されていたHome画面は不要になったので、削除しましょう
![bg right h:600px](images/2023-11-02-05-29-02.png)

---
ペット一覧画面の動作を確認しましょう。
- ペット登録画面のプレビューをした時と同様に、ペット一覧画面のScreen Navigation TypeをHome Screenに変更してください
- プレビュー機能でログインをすると、ペット一覧画面が表示できます。
![bg right h:700px](images/2023-11-02-05-36-18.png)

---
- ペット登録画面でペットを追加すると、ペット一覧画面にも表示されます

これで、ペット一覧画面は完成です。
![bg right h:700px](images/2023-11-02-05-34-18.png)

---
###### ペット詳細画面
- 誕生日が表示される
- 最新の体重が表示される
- 体重記録画面へのリンクがある

次は、こちらの画面を作りましょう
![bg right h:700px](images/2023-11-02-18-50-07.png)

---
- ADD SCREENからBlank Mobile Firstを選択して、Screen Nameを入力します
![h:500px](images/2023-11-01-22-48-24.png) ![h:300px](images/2023-11-02-06-41-40.png)

---
- ADD COMPONENTからApp Barを選択して、画面上に配置します
- Title > Textの値を画面名(PetDetail)に変えます
![bg right h:600px](images/2023-11-02-06-44-49.png)

---
- ADD COMPONENTからImageを選択して、画面上に配置します
![bg right w:500px](images/2023-11-02-07-48-13.png)

---
Image Sourceに表示したい特定のペットの画像を表示したいですが、そのままでは選択肢にありません。

※ Logged In User's > Pets > ... と選べそうに思えますが、ユーザーはペットを複数持つので、ペット1匹を特定できません

![bg right w:600px](images/2023-11-02-06-47-41.png)

---
この画面への導線を設定することで、表示したい特定のペットが選択肢に追加されます
- ペット一覧画面のCardListでADD ACTIONをクリックし、PetDetailへのLinkを追加しましょう
![bg right h:600px](images/2023-11-02-06-56-07.png)

---
- 追加したLinkのSend This Data to PetDetail ScreenにCurrent Petが自動で設定されています。

![bg right h:500px](images/2023-11-02-07-00-07.png)

---
- ペット一覧画面からのLinkのSend This Data to PetDetail ScreenにCurrent Petが設定されたため、ペット詳細画面のAvailable Data内にLinked Dataとして Current Petが設定されています。
  - これにより、ペット詳細画面でペット一覧画面で選択したペット(Current Pet)を扱えるようになります。
![bg right h:350px](images/2023-11-02-07-01-51.png)

---
- ImageコンポーネントのImageSourceに Database > Current Pet > Image を設定します
![h:400](images/2023-11-02-07-03-10.png)

これで、特定のペットの画像が表示されるようになりました。

---
その他の項目も追加していきます。
- ADD COMPONENTからTextを追加し、Birthdayというラベルとその値を表示します
  - 値の表示は、Add Magic TextでCurrent Pet's > Birthdayを選択します
![bg right h:700px](images/2023-11-02-07-08-35.png)

---
- Textのpet birthdayの右側の編集アイコンから、Data Formatを No Formattingに変更します
![bg right h:400px](images/2023-11-02-08-35-08.png)

---
- ADD COMPONENTからTextを追加し、Latest Weightというラベルを表示します
![bg right h:700px](images/2023-11-02-07-14-08.png)

---
Latest Weightの値の表示は、少し工夫が必要です。

- ADD COMPONENTからTextを追加し、Make Listでリストにします。
![bg right h:400px](images/2023-11-02-07-17-47.png)

--- 
- What is this a list of?でPetWeightLogsを選択
- Filterで Current Pet > PetWeightLogsを選択
- SortingでWeightRegisteredTime - Newest to Oldestを選択
- Maximum number of itemsに1を設定

![bg right h:600px](images/2023-11-02-07-19-58.png)

これにより、最新の1件だけに絞り込まれます。

---
- List内のTextコンポーネントの値は、Current PetWeightLog's > WeightKg に設定します
![bg right h:600px](images/2023-11-02-07-24-05.png)


---
- プレビュー画面で動作を確認しましょう

まだPetWeightLogのデータが登録されていないので、Latest Weightは表示されませんが、現時点ではこれでOKです。
![bg right h:700px](images/2023-11-02-08-37-34.png)

---
###### 体重記録画面
- 体重の遷移を示すグラフが表示される
- 現在の体重を入力できる
- ボタンを押して体重を追加できる

最後に、こちらの画面を作りましょう
![bg right h:700px](images/2023-11-02-18-50-36.png)


---
ペット詳細画面に、体重記録画面への導線となるボタンを追加します
- ADD COMPONENTからButtonを選択して、画面上に配置します
- TextをWeight Logに変更します
- Iconをchevron_rightに変更します
![bg right h:600px](images/2023-11-02-08-00-48.png)

---
- ADD ACTION > Link > New Screenを選択します
![bg right h:600px](images/2023-11-02-08-02-53.png)

---
- Screen Nameを入力し、Blank Mobile Firstを選択して、画面を作成します
 ![bg right h:600px](images/2023-11-02-08-04-30.png)

---
作成された画面では、ペット詳細画面から受け渡されたCurrent Petのデータを扱えるようになっています
![bg right h:440px](images/2023-11-02-08-09-20.png)

---
- ADD COMPONENTからApp Barを選択して、画面上に配置します
- Title > Textの値を画面名(PetWeightLog)に変えます
![bg right h:600px](images/2023-11-02-07-46-39.png)

---
次に、過去に登録したペットの体重がグラフとして表示されるようにしていきます。
- ADD COMPONENTからEXPLORE MARKETPLACEを選択
- Chart KitをINSTALL

![bg right h:450px](images/2021-11-04-03-52-55.png)　![bg right h:170px](images/2023-11-02-07-51-53.png)

---
- Line Chartを画面に追加
![bg right h:400px](images/2023-11-02-07-54-16.png)


---
Line Chartを設定します。
- What is this a chart of?でPetWeightLogsを選択
- FilterでCurrent Pet > PetWeightLogsを選択
- Custom Filterに WeightRegisteredTime Is after 30 days ago を設定し、表示期間を指定
- SortingでWeightRegisteredTime - Oldest to Newestを選択

![bg right h:700px](images/2023-11-02-08-12-17.png)

---
- X Axis ValueにPetWeightLog > WeightRegisteredTimeを設定
  - Date FormatにDate / Timeを設定
- Y Axis ValueにPetWeightLog > WeightKgを設定
![bg right h:350px](images/2023-11-02-08-13-12.png)
![bg right h:250px](images/2021-11-04-04-13-46.png)

これで、グラフを表示するための設定ができました。

---
次に、体重を記録できるようにしましょう。

- ADD COMPONENTから、Text Inputを追加してください
- TypeをNumberに変更してください
- PlaceholderをEnter current weightに変更してください
![bg right h:500px](images/2023-11-02-08-17-51.png)

---
- ADD COMPONENTからTextを追加してください
- 値をWeight(kg)に変更してください
![bg right h:500px](images/2023-11-02-08-18-37.png)

---
- ADD COMPONENTからButtonを追加してください
- TextをAddに変更してください
- ADD ACTIONからCreate > PetWeightLogを選択してください
![bg right h:500px](images/2023-11-02-08-20-46.png)

---
Actionに対して、以下のように設定します。
- WeightKg: Other Components > Input
- WeightRegisteredTime: Date & Time > Current Time
- Pet: Current Pet
![bg right h:500px](images/2023-11-02-08-22-46.png)

これで体重記録画面が作成できました。

---
画面を行き来して動作が確認できるように、ヘッダーの戻るアイコンにリンクを設定しましょう。
- ペット登録画面、ペット詳細画面のそれぞれで、App BarのLeft IconにMyPetsへのリンクを追加します
![bg right h:450](images/2023-11-02-08-50-25.png)

---
- 体重記録画面では、App BarのLeft Iconのリンクで、Backを選択します
![bg right h:550](images/2023-11-02-08-53-32.png)

<!-- ---
参考: 体重記録画面で、App BarのLeft Iconのリンク先を、ペット詳細画面にしてしまうと、CurrentPetの情報が失われてしまいます
![bg right h:450](images/2023-11-02-08-56-14.png) -->
<!-- →実際に試すと、動作に問題なかった -->

---
Preview機能でグラフの表示を確認しましょう。体重を複数追加すると、グラフが描画されます。

※ 体重の登録日時が長く、省略して表示されてしまいます。同じ日に複数の体重を登録してテストをしたかったのでDate&Time型にしていますが、本来はDate型にして、1日に1回しか登録できないよう制御する方が良さそうです。
<!-- 、連続で異なる体重を追加するとLineが上下に伸びてしまう -->
<!-- ![bg right h:700px](images/2021-11-04-04-15-38.png) -->
![bg right h:700px](images/2023-11-02-08-28-21.png)

---
ペット詳細画面でLatest Weightが表示されるようになったことも確認できます。
![bg right h:700px](images/2023-11-02-09-01-42.png)


---
アプリの画面を一通り作成することができました :tada:

![h:383px](images/2023-11-02-18-52-28.png) ![h:383px](images/2023-11-02-18-53-10.png) ![h:383px](images/2023-11-02-18-47-35.png) ![h:384px](images/2023-11-02-18-48-18.png) ![h:383px](images/2023-11-02-18-50-07.png) ![h:383px](images/2023-11-02-18-50-36.png)

---
#### クローン用URL
- 以下のURLの右下のCLONE APPボタンでアプリをクローンできますので、答え合わせに使ってください
https://ryo-imahashis-team-6.adalo.com/pethealthlog

![bg right h:350px](images/2023-11-02-08-32-08.png)

---

## 演習1
1. 登録済のペットの情報を編集できる、ペット編集画面を作成しましょう
2. 登録済のペットを削除できる、ペット削除機能を追加しましょう

---
#### ヒント
- ペット編集画面を作る時は、ペット登録画面の作り方が参考になります
- ペット削除機能のために新規の画面は不要なので、どこに削除ボタンを追加するのが良いかを考えてください
- ACTIONを追加する時に、UpdateやDeleteが選べます
![h:300](images/2023-11-02-19-44-50.png)


---
# :hourglass_flowing_sand:
# :hourglass_flowing_sand:
# :hourglass_flowing_sand:
# :hourglass:
# :hourglass:

---
#### 演習1の答え合わせ
まずは自分でやってみて、その後でここから先を見てください :pray:

---
###### ペット編集画面
登録したペットの情報を更新できるペット編集画面を新たに作ります。


---
まず、ペット詳細画面にペット情報編集画面への導線を追加します。
- ADD COMPONENTからAction Buttonを追加
- Iconをeditに変更
- Icon and Text ColorをDefault Background(white)に変更
![bg right h:600px](images/2023-11-03-00-06-25.png)

---
- ADD ACTIONからLink > New Screenを選択
![bg right h:630px](images/2023-11-03-00-08-11.png)


---
- Blank Mobile Firstを選択し、EditPetInfoスクリーンを作成
![bg right h:620px](images/2023-11-03-00-09-03.png)

---
- App Barを追加してTitleをEditPetInfoに変更
- Formを追加して、以下を設定
  - Which data collection?でPetsを選択
  - What do you want the form to do?でUpdate Current Petを選択
- FieldsでBirthdayとImageの順番を入れ替え

![bg right h:460px](images/2023-11-03-00-13-30.png)
<!-- 更新不要な項目があれば、その入力箇所は削除できそう -->

---
- FormのSubmit Buttonに戻るリンクを追加
![bg right h:600px](images/2023-11-03-00-22-10.png)

---
- App BarのLeft Iconに戻るリンクを追加
![bg right h:600px](images/2023-11-03-00-15-38.png)


---
Preview機能でペット情報編集画面が使えることを確認しましょう。

![bg right h:700px](images/2023-11-03-00-25-31.png)

---
参考
- FormコンポーネントのFieldのRequired Error Textにはデフォルトでチェックが入っており、その項目が入力されていない場合にはエラーメッセージが表示されます。
- 未入力のままUPDATE PETをクリックして確認してみましょう
![bg right h:600px](images/2023-11-03-00-27-27.png)
![bg right h:600px](images/2023-11-03-00-28-44.png)

---
###### ペット削除機能
ペット詳細画面に、登録したペットを削除できるボタンを追加します。

---
- App Barを選択し、Right Icon 1のトグルをONにする
- Iconをdeleteに変更
- ADD ACTIONからDelete > Current Petを選択
- ADD ANOTHER ACTIONからLink > Mypetsを選択
![bg right h:550px](images/2023-11-03-00-32-55.png)

<!-- TODO: 削除の前に本当によろしいですか？ を挟みたい-->
---
Preview機能で削除を試してみましょう。

削除が完了してペット一覧画面に遷移すると、削除したペットは表示されません。

![bg right h:600px](images/2023-11-03-00-34-40.png)
![bg right h:600px](images/2023-11-03-00-34-58.png)

---
## サンプルアプリを改善しよう
まだ紹介していないAdaloの機能を使いながら、サンプルアプリを改善していきます。

---
#### ログアウト
- ペット一覧画面のAppBarを選択し、Right Icon 1を有効化
- Iconをlogoutに変更する
- ADD ACTION > More... > User Login > Log Outを選択
- ADD ANOTHER ACTION > Link > Loginを選択
![bg right h:580px](images/2023-11-03-00-56-10.png)

---
Preview機能で確認しましょう。
追加したアイコンをクリックするとログアウトし、ログイン画面に遷移するようになりました。

----
#### Actionの実行条件設定
ペットが未登録の場合にペット一覧画面を表示した場合、ペット登録画面へ遷移させます。
- ペット一覧画面でActions > ADD ACTION > Link > Pet Registrationを選択
- SHOW ADVANCEDをクリックし、When does this happen?をSometimesに変更
![bg right h:600px](images/2023-11-03-00-59-14.png)

---
- This action will only happen if...でMore > Logged In User's > Pets' > Count を選択
- Is equal to の下の数値を0に変更
![bg right h:600px](images/2023-11-03-01-00-58.png)

---
Preview機能で確認しましょう。
新しいユーザーでSignupすると、ペット一覧画面からペット登録画面に遷移します。

---
#### 選択式入力フォーム
ペットの情報に性別を追加し、入力フォームで選択式入力ができるようにします。

---
選択式入力フォームで使う選択肢は、データベースにCollectionを追加してレコードとして用意します。
- データベースにGenders Collectionを追加(PropertyはデフォルトのままでOK)
- 0 Records > ADD GENDERとクリックし、MaleとFemaleの2つのRecordを追加
![h:400px](images/2023-11-03-01-02-28.png)

---
- Genders CollectionにPets Collectionとの1対多のRelationshipを追加する
  - 1匹のペットは1つの性別を持ち、1つの性別は複数のペットに対して設定されるため
![bg right h:600px](images/2021-11-05-00-46-10.png)

---
- ペット登録画面のフォームを選択
- Fields > ADD VISIBLE FIELD > Genderを選択
![bg right h:600px](images/2023-11-03-01-04-12.png)

---
- ペット詳細画面に性別の表示欄を追加
![bg right h:500px](images/2023-11-03-01-06-07.png)

---
Preview機能で確認しましょう。

- ペット登録画面で性別が選択できます。
- 選択した性別がペット詳細画面に表示されます。

![bg right h:620px](images/2023-11-03-01-07-18.png)
![bg right h:620px](images/2023-11-03-01-07-56.png)

---
補足
- 性別を選択できるようになる前に登録したペットで空欄が表示されることが気になるようであれば、Pet CollectionのRecordを表示してそのペットをクリックし、性別を手動で設定してもOKです。
![h:420px](images/2023-11-03-01-08-51.png)

---
参考

複数選択式の入力フォームは、MarketplaceのMultiselectDropdownを使って作れます。

必要になったら、試してみてください。
![bg right h:400px](images/2023-11-03-01-09-51.png)


---
#### 条件によってコンポーネントの表示or非表示を切り替える
体重が未登録であれば、ペット詳細画面のLatest Weightは非表示にします。

![bg right h:620px](images/2023-11-03-01-07-56.png)

---
- Latest Weightというラベルとその値を選択し、グループ化します
![bg right h:500px](images/2023-11-03-01-12-04.png)

---
- Change Visibilityを選択します

![bg right h:500px](images/2023-11-03-01-13-04.png)

---
- VisibilityをSometimes Visibleに変更
- Will be visible if...でCurrent Pet > PetWeightLogs > Countを選択
- Is not equal to 0と設定
![bg right h:620px](images/2023-11-03-01-14-11.png)

---
Preview機能で確認すると、体重が未登録であれば、Latest Weightが非表示になりました。

![bg right h:620px](images/2023-11-03-01-14-40.png)


サンプルアプリの改善は一旦ここまでとします。

---
#### クローン用URL
- 以下のURLの右下のCLONE APPボタンでアプリをクローンできますので、答え合わせに使ってください
https://ryo-imahashis-team-6.adalo.com/improvedpethealthlog
![h:400px](images/2023-11-03-01-15-43.png)


---
## 外部連携
Adaloだけで実現できないことがある場合、外部サービスと連携することでそれを実現できるかもしれません。

その方法をご紹介します。

---
以下4種類の外部連携の方法を紹介します。
- Marketplaceの外部連携コンポーネント
- Custom Action
- External Collection
- 連携サービス

---
#### Marketplaceの外部連携コンポーネント
Marketplaceから外部連携を可能にするコンポーネントを追加できます。

![bg right h:480px](images/2023-11-02-23-54-00.png)

---
まずはアプリを新規作成しましょう。
- Adaloにログイン
https://app.adalo.com/login
- CREATE NEW APPをクリック
![bg right h:300px](images/2021-11-26-22-00-12.png)
---
- PlatformはResponsive Appを選択
![bg right h:500px](images/2023-10-29-13-09-34.png)

---
- TemplateはBlank Mobile Firstを選択
![bg right h:500px](images/2023-11-02-20-25-53.png)

---
- App NameにはMarketplaceComponentTrialを入力
- その他の項目は自由に設定してください
![bg right h:500px](images/2023-11-02-20-27-20.png)

---
##### Twitter Timeline コンポーネント
- +ボタンを押してADD COMPONENTの中のExplore Marketplaceをクリック
![bg right h:700px](images/2023-11-02-20-49-56.png)


---
- Twitter TimelineコンポーネントをINSTALL
![bg right h:450px](images/2023-11-02-20-50-46.png)

---
Twitter Timelineコンポーネントを配置します。
- Home ScreenにTwitter用画面へのLinkボタンを追加
![bg right h:600px](images/2023-11-02-20-52-04.png)

---
- ADD ACTIONからNew ScreenへのLinkを追加
![bg right h:600px](images/2023-11-02-20-52-41.png)

---
- Blank Mobile Firstを選択し、TwitterTimeline画面を作成
![bg right h:600px](images/2023-11-02-20-54-06.png)

---
- Twitter Timelineコンポーネントを配置
![bg right h:600px](images/2023-11-02-20-55-36.png)

---
- Twitter Handle Nameに "tokyotech_jp" と入力
  - 好きなTwitterアカウントのHandle Nameに変更してもOKです
![bg right h:550px](images/2023-11-02-20-57-01.png)

---
Preview機能でSignupして、HomeのTwitterボタンをクリックすると、TwitterTimeline画面に入力したHandle NameのTwitterアカウントの投稿が一覧表示されます
![bg right h:700px](images/2023-11-02-20-58-47.png)

<!-- --- -->
<!-- スライドの枚数的に時間が足りなくなりそうなので、割愛します... -->
<!-- - Users CollectionにTwitterHandleName Propertyを追加
  - TypeはTextを選択
![bg right h:700px](images/2021-11-26-22-33-36.png)

---
- Signup画面のFormをクリック
- Fields > ADD VISIBLE FIEDLD > TwitterHandleName
- Not Requiredに変更
![bg right h:500px](images/2021-11-26-22-41-05.png)

---
- "ALREADY HAVE AN ACCOUNT?"というリンクがフォームに重なってしまっていたので、下に移動
![bg right h:700px](images/2021-11-26-22-57-22.png)

---
登録済のユーザーにTwitterHandleNameを設定しておきましょう
- Users Collectionの "1 Record" ボタンをクリック
![bg right h:500px](images/2021-11-26-22-44-36.png)

---
- 登録済のユーザーのレコードをクリック
- TwitterHandleNameを入力(自分のアカウントでも、好きなアカウントでもOK)
![bg right h:500px](images/2021-11-26-22-49-11.png)

---
- Twitter TimelineコンポーネントのTwitter Handle Nameを"Logged In User's TwitterHandleName"に変更
![bg right h:500px](images/2021-11-26-22-51-21.png)

---
理論上はこれでログインユーザー自身が設定したTwitterアカウントの投稿一覧が表示されるはずです。

Preview機能で確認してみましょう。

---
最初はエラーが起きると思います。

一度戻るボタンでホーム画面に戻ってから再度タイムラインを表示すると、設定したTwitterアカウントの投稿一覧が表示されます。
![bg right h:700px](images/2021-11-26-22-59-00.png)
![bg right h:700px](images/2022-11-12-12-06-22.png)

---
Twitter Timelineは有志の方が無償公開してくれているコンポーネントです。

誰かが作ってくれているものが、いつも自分の思い通りに動くとは限りません。

「不具合があったりもするんだな」くらいは覚えておいてもらえると嬉しいです。
![bg right h:380px](images/2022-11-12-12-08-17.png) -->

---
この他にも外部サービスと連携するためのコンポーネントがいくつか提供されています。興味があれば、試してみましょう。

例: 
- Youtube(無料)
- Google Map(クレジットカードの登録が必要だが、無料枠で利用可能)

---
#### Custom Action
外部連携コンポーネントの次は、APIから取得したデータをAdaloの画面上で扱う方法を紹介します。

---
参考
>アプリケーションプログラミングインタフェース（API、英: Application Programming Interface）とは、広義ではソフトウェアコンポーネント同士が互いに情報をやりとりするのに使用するインタフェースの仕様である。

https://ja.wikipedia.org/wiki/%E3%82%A2%E3%83%97%E3%83%AA%E3%82%B1%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%97%E3%83%AD%E3%82%B0%E3%83%A9%E3%83%9F%E3%83%B3%E3%82%B0%E3%82%A4%E3%83%B3%E3%82%BF%E3%83%95%E3%82%A7%E3%83%BC%E3%82%B9

---
まずは、API連携を試してみましょう。
無料で試せるThe Cat APIを使います。以下のURLにアクセスしてください。
https://thecatapi.com/

![h:400px](images/2023-11-02-21-05-32.png)

---
参考: 犬派の人のために、The Dog APIもあります。おそらくThe Cat APIと同様のことができると思います。(試せていないので、まずは一緒にThe Cat APIを使うことをおすすめします)
https://www.thedogapi.com/

![h:400px](images/2023-11-02-21-06-15.png)

<!-- APIキーなしでできる範囲でやる -->
<!-- 
---
APIを使用する際には、APIの提供者からAPIキーを発行してもらう必要がある場合が多いです。
The Cat APIでもAPIキーが必要になりますので、発行してもらいましょう。
- 下にスクロールしてPricingの欄の "SIGNUP FOR FREE" をクリック
![bg right h:600px](images/2021-11-26-17-08-19.png)

---
- E-mail、App Description、type of projectを入力し、 "SIGNUP" をクリック
![bg right h:600px](images/2023-11-02-21-08-44.png)

---
- メールで送られてきたAPIキーを確認(後で使います)
![h:580px](images/2023-11-02-21-12-30.png) -->

---
APIドキュメントでAPIの使い方を確認しましょう。
- 以下のURLへアクセス
https://docs.thecatapi.com/

---
トップページに記載されている、ランダムな子猫の画像を取得するAPIを使います。
https://api.thecatapi.com/v1/images/search
![w:900](images/2023-11-02-21-41-46.png)

---
- Adaloの管理画面でCREATE NEW APP
- 設定は以下の通り
  - Platform: Responsive App
  - Template: Blank Mobile First
  - App Name: ApiIntegrationTrial

![bg right h:250px](images/2021-11-27-02-15-47.png)

---
- Home画面に子猫画像表示画面へのリンクボタンを追加
- ADD ACTIONからNew ScreenへのLinkを設定
![bg right h:500px](images/2023-11-02-21-49-44.png)

---
- TemplateにBlank Mobile Firstを選択し、Kitten画面を作成
![bg right h:500px](images/2023-11-02-21-50-08.png)

---
- Imageコンポーネントを画面上に配置
- コンポーネントの設定はそのままにしておく(後で設定します)
![bg right h:500px](images/2023-11-02-21-51-28.png)

---
- Change Kitten Image Buttonを追加
![bg right h:550px](images/2023-11-02-21-54-13.png)

---
- ADD ACTIONからNew Custom Actionを選択
![bg right h:650px](images/2021-11-27-03-57-01.png)

---
14日間のフリートライアル(無料)の開始を促されます。
- "START FREE TRIAL" をクリック
![bg right h:400px](images/2023-11-02-21-28-44.png)

---
トライアルが開始しました。
- "CREATE NEW CUSTOM ACTION" をクリック
![h:500px](images/2023-11-02-21-27-32.png)

---
- 以下を入力してNEXTをクリック
  - Name: GetRandomKitten
  - Type: Create

![h:400px](images/2021-11-27-04-25-58.png)

---
- 送信するAPI Requestを以下のように設定します。
  - API Base URL: https://api.thecatapi.com/v1/images/search
  - Method: GET
- 設定後、"RUN TEST REQUEST" をクリック
![bg right h:450px](images/2023-11-02-21-59-14.png)

---
Testが成功すると、APIから取得したデータが表示されます。これらは、後続のアクションで使用できます。
- "SAVE CUSTOM ACTION" をクリック
![h:450px](images/2023-11-02-22-03-17.png)

---
次に、APIから取得した子猫の画像のURLをImageコンポーネントのImage Sourceに設定します。

そのままでは、選択肢の中にAPIから取得したデータは出てきません。
![h:100px](images/2021-11-27-05-52-10.png)

![bg right h:500px](images/2021-11-27-05-54-04.png)
![bg right h:500px](images/2023-11-02-22-08-34.png)

---
- Text Inputコンポーネントを画面上に追加
- Nameを "Invisible Kitten Image URL Input" に変更
![bg right h:550px](images/2023-11-02-22-09-43.png)

---
- "Change Kitten Image Button" をクリック
- ADD ANOTHER ACTION から More > Change Input Value を選択

![bg right h:550px](images/2023-11-02-22-10-48.png)

---
- Inputに "Invisible Kitten Image URL Input" を設定
- Valoueに "GetRandomKitten > url" を設定
- "DONE" をクリック
![bg right h:500px](images/2021-11-27-06-02-37.png)

---
- Imageコンポーネントをクリック
- URLに Other Components > Invisible Kitten Image URL Input を設定
![bg right h:550px](images/2023-11-02-22-12-28.png)

---
- "Invisible Kitten Image URL Input" のLAYOUTタブを開き、Visible On...で3つある目のアイコンをそれぞれクリックして、非表示にする
![bg right h:358px](images/2023-11-02-22-17-03.png)

---
Preview機能で確認します。

CHANGEボタンをクリックすると、子猫の画像が表示されました。
![bg right h:700px](images/2023-11-02-22-19-13.png)

---
補足

- Custom ActionでAPIから取得したデータは、後続のActionで使用できます。そのデータをコンポーネントで使いたい場合は、以下のいずれかの方法を使いましょう。
  - 今回のように、後続のActionのChange Input Valueで同一画面上のText InputのValueにデータを設定し、それを読み込みましょう。
  - あるいは、そのデータを後続のActionでデータベースに保存して、それを他のコンポーネントから読み込むことも可能です。
    - 例: https://help.adalo.com/integrations/custom-actions

<!-- ![bg right h:400px](images/2021-11-27-06-13-06.png) -->

---
注意事項

現状、Custom Actionにはいくつかの制限があります。
- Custom ActionはFormコンポーネントのSubmitボタンでは動作しません。
- Custom Actionが画面全体のActionとして使用されている場合、APIのレスポンスとして取得したデータは後続のActionで使用できません。
- アプリをCloneしてもCustom Actionはコピーされません。Custom Actionを含むアプリをCloneしたら、手動で作成し直してください。
<!-- https://help.adalo.com/integrations/custom-actions -->


---

#### External Collection
APIから取得したデータをAdaloのCollectionとして扱う方法を紹介します。

複数のデータを一括取得してそれらを画面上に一覧表示するような場合はCustom Actionではなく、External Collectionを使います。

---
先ほどのAPIの末尾に ?limit=10 を付け加えて、猫の画像を10件取得します。
https://api.thecatapi.com/v1/images/search?limit=10
![h:450px](images/2023-11-02-22-25-58.png)

---
- DatabaseのExternal Collectionsで "ADD COLLECTION" をクリック
![bg right h:700px](images/2023-11-02-22-27-40.png)

---
- 以下を設定して、NEXTをクリック
  - Collection Name: Kittens
  - Base URL: https://api.thecatapi.com/v1/images/search?limit=10
![bg right h:530px](images/2023-11-02-22-28-51.png)


---
Adaloでは、APIでアクセスするリソース(この例ではKittens)毎に5つのEndpoints(アクセス方法)が設定できます。

APIの仕様によってはそれに合わせるための修正が必要になりますが、今回はそのままNEXTをクリックしてOKです。
<!-- (使用するEndpointである Get All はデフォルトでAPIの仕様を満たす設定になっています) -->
![bg right h:500px](images/2023-11-02-22-30-19.png)

---
- テストを実行して成功したら、"SAVE COLLECTION" をクリック
![bg right h:650px](images/2023-11-02-22-30-57.png)


---
External Collectionが作成されました。

APIから取得するデータが全てプロパティとして設定されています。
![bg right h:400px](images/2023-11-02-22-31-55.png)

---
取得したデータを一覧表示しましょう。
- Home画面に "Kitten List Link" ボタンを追加
- ADD ACTIONからNEW SCREENヘのLINKを追加
![bg right h:600px](images/2023-11-02-22-34-20.png)

--- 
- BlankMobileFirstを選択して、"KittenList"スクリーンを作成
![bg right h:600px](images/2023-11-02-22-35-30.png)

---
- ADD COMPONENTからImage Listを追加
![bg right h:420px](images/2023-11-02-22-38-15.png)


---
- Kittens Collectionのリストとして設定
- ImageのURLに "kitten url" を設定
- "If there's no image..." に "Don't show anything" を設定
![bg right h:600px](images/2023-11-02-22-41-37.png)


---
- TextとIconは不要なので非表示にする
![bg right h:500px](images/2023-11-02-22-46-58.png)


---
Preview機能で確認すると、猫のリストが表示されました。
![bg right h:700px](images/2023-11-02-22-48-01.png)


---
#### 連携サービス
Custom ActionやExtenal Collectionでは、連携先のサービスのAPIの仕組みをドキュメントから理解するのが大変かもしれません。

次は、もっと簡単に外部サービスとの連携ができるサービスをご紹介します。

---
連携サービスにも色々なものがありますが、今回はAdaloに組み込まれているZapierというサービスを紹介します。
![h:500px](images/2021-11-26-16-42-00.png)


---
Adaloにはメール送信機能がありません。

今回は、Zapierを使って、AdaloとGmailを連携させることで、アプリへSignUpした人に自動でWelcomeメールが送信されるようにしていきます。

![bg right h:200px](images/2022-11-12-19-46-27.png)

---
- Gmailを使うために必要なので、Googleアカウントを作成します。
  - 既に持っていればそのアカウントを使えば良いので、作成は不要です。
  - 持っていない人は、こちらのURLから私と一緒に作成してください。
https://accounts.google.com/signup/v2/webcreateaccount?continue=https%3A%2F%2Faccounts.google.com%2FManageAccount%3Fnc%3D1&dsh=S50453738%3A1637917137418951&biz=false&flowName=GlifWebSignIn&flowEntry=SignUp


---
Googleアカウントが用意できたら、Zapierとの連携を設定していきます。
- ApiIntegrationTrialアプリのSign Up画面でSubmit Buttonを選択
- ADD ANOTHER ACTION > New Integration > Gmail を選択
![bg right h:650px](images/2023-11-02-23-09-00.png)

---
- 一番上のSend Gmail emails for new Adalo recordsのUse this Zapをクリック
![bg right h:400px](images/2023-11-02-23-11-50.png)


---
- Continueをクリック
![bg right h:400px](images/2023-11-02-23-12-46.png)


---
Zapierの設定画面が開きます
- 右側のConnect AdaloのSign Inをクリック
![w:1000](images/2023-11-02-23-14-09.png)


---
- Adaloにログイン
![w:1000](images/2023-11-02-23-15-37.png)

---
- ALLOW ACCESSをクリック
![bg right w:400](images/2023-11-02-23-16-44.png)

---
- Triggerを設定
  - App: ApiIntegrationTrial
  - Collection: Users
![bg right w:400](images/2023-11-02-23-18-45.png)

---
- Test triggerをクリック
![bg right w:400](images/2023-11-02-23-19-28.png)


---
- レコードが見つかったら、Continue with selected recordをクリック
![bg right w:400](images/2023-11-02-23-20-08.png)


---
-  Connect GmailのSign inをクリック
![bg right w:400](images/2023-11-02-23-20-54.png)


---
- アカウントを選択
![bg right w:400](images/2023-11-02-23-22-03.png)

---
- 許可をクリック
![bg right w:400](images/2023-11-02-23-22-29.png)

---
Actionを設定します。
- Fromに自分のGmailアドレスを設定
- From Nameにアプリ名を設定
- Subject, Bodyを自由に入力
- Continueをクリック
![bg right h:700px](images/2023-11-02-23-27-14.png)


---
- to: のアドレスが実際の自分のメールアドレスになっていれば、"Test step"をクリックしてメール受信を確認する
  - 実際の自分のメールアドレスになっていなければ、"Skip test"をクリック(testをするとメール送信が失敗するため)
![bg right h:700px](images/2023-11-02-23-29-13.png)

---
- Publishをクリック

これで、Zapierとの連携設定ができました。
![bg right h:600px](images/2023-11-02-23-29-49.png)

---
AdaloのApiIntegrationTrialアプリでWelcomeメールが送信されることを確認しましょう。
- Preview機能で、実際の自分のメールアドレスを入力してSignupすると、2分以内にメールが届きます
![w:500](images/2023-11-02-23-31-10.png)


---
参考: 2分待たなくても、Zapの一覧画面から、手動ですぐにZapを実行することもできます。
- https://zapier.com/app/zaps にアクセス
- 実行したいZapを選んで"Run Zap"をクリック
![h:500px](images/2023-11-02-23-43-58.png)

---
Zapierを使えば、他にも様々なサービスを連携させることができます。

Adaloだけでうまく実現できないことが出てきた時には、他のサービスと組み合わせることで実現できないかを考えてみると良いかもしれません。
![bg right h:480px](images/2023-11-02-23-46-22.png)

---

Adaloでの外部連携についての紹介は以上です。

---
## 演習2
- アプリを1つ自由に開発してください。
- 作りたいアプリが思い浮かばない人は、以下の機能を持つチームメンバー管理アプリを開発しても良いです。
    - チームメンバーの登録
    - メンバー一覧の表示
    - メンバー詳細の表示
    - メンバー情報の更新
    - メンバー削除
    - 自分で考えたオリジナル機能(いくつあっても良い)

---
※ (時間が許せば)最後は全員に発表していただきたいと考えています。

※ アプリが使えるようになったら、SlackでURLを共有して、みなさんに見てもらいましょう。

---
演習における注意事項
- NoCodeツールでは、簡単にアプリを作れる反面、複雑なUIや機能を実現できない場合があります
  - 行き詰まった時は、どうすれば自分がやりたいことをシンプルなUI、機能で実現できるか考えてみてください
    - 例: 1画面に多くのコンポーネントを含めず、画面を分ける 等

---
参考
- クローンできるAdaloのアプリが公開されているので、やりたいことに近いものがないか探してみると良いかもしれません。
  - App Templates
  https://www.adalo.com/app-templates
  - UI & Functional Kits
  https://www.adalo.com/cloneable-kits

---
クローンできるアプリの例
- Eventカレンダー https://www.adalo.com/cloneables/event-calendar
- SNSのフォロー機能 https://www.adalo.com/cloneables/follow-function
- Facebookのクローン https://www.adalo.com/cloneables/facebook-clone
- ブログアプリ https://www.adalo.com/cloneables/minimal-blog-app
- 商品販売アプリ https://www.adalo.com/cloneables/ecommerce-app


---
# :hourglass_flowing_sand:
# :hourglass_flowing_sand:
# :hourglass_flowing_sand:
# :hourglass:
# :hourglass:

---
#### 演習結果の発表
演習で作ったアプリについて発表してください。

---
## まとめ
- Adaloについて紹介し、データベースの設計方法を学んだ上で、ペットの健康管理アプリを題材にアプリを開発しました。
- 外部サービスとの連携方法として以下4つを紹介しました。
  - Marketplaceの外部連携コンポーネント
  - Custom Action
  - External Collection
  - 連携サービス

---
- ここまでの内容を踏まえて、Development Phaseで自分たちが作りたいアプリがAdaloで実現できそうかは、チームで考えてみると良いと思います。
- 次回はノーコードツールBubbleのレクチャーです。お楽しみに！

---
# 以上です！
# お疲れさまでした！
