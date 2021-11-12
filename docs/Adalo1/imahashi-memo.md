---
marp: true
theme: gaia
size: 16:9
header: '　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　Copyright Ryo Imahashi'

page_number: true
paginate: true

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
- List系のコンポーネントはデータベースと紐付けないと要素が表示されないので、今回は使えない
---
- Formコンポーネントはコレクションと1対1で紐付けないといけない
![bg right h:400px](images/2021-10-21-23-40-18.png)
---
- ClickActionでの追加もコレクションと1対1でないといけないみたい
![bg right h:400px](images/2021-10-21-23-57-05.png)
- 多分即答できない質問が出てくるので、随時休憩時間に調べることリストに追加しよう
- RGBAとは、ディスプレイ画面で色を表現するために用いられる、赤（Red）、緑（Green）、青（Blue）の3色に、アルファ（Alpha）と呼ばれる透過度の情報を加えたもの
https://www.weblio.jp/content/RGBA

- Missing component: @protonapp/material-components.Icon ???
  - 同じものを作り直したら直った

- 静的、動的 https://kt-life.net/seitekisite-doutekisite/# 
  - 静的サイト(視覚的な動きはある)の例: https://recruit.uuum.co.jp/

