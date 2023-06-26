# 職務経歴書

2023/3/19 現在  

名前: 森恭平  
生年月日: 1999年7月27日(23歳)


## 経歴要約

2021年10月にアルサーガパートナーズ株式会社に入社。受託開発にて主にフロントエンドのエンジニアとして約1年半ほど勤務。コンポーネント設計から実装、改修、レビューまで担当してきました。2022年9月には、フロントチームのリーダー代理を任され、見積もり対応やタスクの割り振り等を行う。また、コンポーネントの肥大化による品質低下問題に着目し、技術スタックやコンポーネント設計の見直しを提案し、品質向上に貢献しました。

## 経験技術

TypeScript / JavaScript / Vue(Composition API / Options API) / Nuxt2 / Vuex / CSS / SCSS / VonageVideoAPI / Atomic Design　/ Storybook / GraphQL / Prisma / Rails 

## 職務経歴

アルサーガパートナーズ株式会社（2021/10 ~ 2023/6）


<details>
<summary>プロジェクト1(2022/6~11)</summary>

#### 概要
オンラインセミナー開催プラットフォームの分析機能の開発

#### メンバー
- PM: 1人
- フロント： 2 ~ 4人
- サーバー： 3 ~ 4人
- QA： 1人

#### 担当
フロントチームのリーダー代理（途中から）、コンポーネント設計・技術スタックの見直し、フロントエンドの機能実装、改修作業、リファクタ、レビュー対応、見積もり対応、チケット振り分け、API実装少し

#### 技術
TypeScript, Vue2(Composition API), SCSS, Atomic Design, Rails, RSpec

<!-- <details>
<summary>職務詳細</summary> -->

#### 課題・問題点
- コンポーネントの肥大化による、コードの可読性、保守性、再利用性の低下。それによるバグの発生。
- 今後の保守運用フェーズを考えると、コンポーネント設計や技術スタックを見直す必要があった。

#### 原因
- 適切なコンポーネントの分割ができておらず、同じようなUIのコンポーネントを作ってしまっていること（コンポーネント分割は個人任せ）
- ロジックをほとんどVueファイル内に書いてしまっていること
- リアクティブなデータやVueのライフサイクルフックなどを切り出せないこと

#### 対応
アプローチとして、技術スタックをJavascript, Vue(Options API)という構成からTypeScrpitとCompositioAPIという構成に変更。
コンポーネント設計はアトミックデザインをベースとしたものに変更することにした。

> CompositioAPIを導入することで、リアクティブなデータやそのデータが絡むロジック、ライフサイクルフックまで外部ファイルに切り出すことができるようになるので、コンポーネント内のコード量の削減、関心ごと単位でデータやロジックを切り出せるといったメリットがあるため、コードの可読性やコンポーネントの再利用性や保守性が高くなると思い選定し提案しました。

> TypeScrpitについては、型推論やエディタ補完による開発速度の向上や早期のコンパイルエラーの発見、コード自体がドキュメントの側面を持つメリットがあり、
開発者がTypeScriptの経験者であることも加味して提案しました。

> アトミックデザインベースのコンポーネント設計にしたのも、コンポーネントの分け方に一貫性を持たせることや責務や役割をしっかりわけることで、コンポーネントの再利用性と保守性を上げるために提案しました。

スケジュールとの兼ね合いもあるため、新規で作成する画面や機能に関しては上記の構成にし、既存部分の特に肥大化している部分を優先してリプレイスしていく方針とした。

上記対応により、肥大化コンポーネントの解消、コードの可読性や開発効率の向上、コンポーネントの責務を分けたことによる再利用性、保守性の向上に繋がり、
QAエンジニアが算出していた品質数値を、60から80以上まで上げることに成功した。


#### その他工夫した点・取り組み
- vueファイルにおいて、computedを使わずtemplateにmethodを使っている部分やリアクティブなデータの余計な更新など、無駄なレンダリングやスタイルガイドに沿っていない部分のリファクタ対応をした。

- コードレビューでは、なるべく柔らかい言い回しを使い、感嘆符や絵文字などを少し使うことや、指摘した点についての記事や公式ドキュメントのURLも添付するなど、徹底的に相手のことを考えたレビューを心がけていた。

- 見積もり対応では、UI、機能、繋ぎ込み、レビュー、の細かく分けてすることで、より正確な見積もりができるように努めた。

- 初期描画時に複数のAPIを叩く場面が多く、それにより表示が遅かったり、ラグが生じることが多かったため、Promise.allで処理をまとめることや、初期描画ではすぐに必要ないAPIのタイミングをずらしたりすることで、初期描画の遅さを緩和。

- API取得時にラグがある場合のローディングUIの導入、検索時の検索ボタンやページネーションボタンの制御などの指摘されていない部分のUX改善も積極的に行なった。

<!-- </details> -->

</details>

---


<details>
<summary>プロジェクト2(2022/12~6)</summary>
  
#### 概要
冠婚葬祭の着物等の見積書・契約書作成システムの改修

#### メンバー
- PM: 1人
- フロント： 6~9人
- QA： 1人

#### 担当
改修、バグ修正、機能追加、APIとの繋ぎ込み、メンバーのレビュー

#### 技術
TypeScript, Nuxt2(Composition API), SCSS, Storybook

#### 取り組み・工夫した点

- 子コンポーネントでpropsで来た値をrefの初期値として定義している部分が多数あり、親コンポーネントと子コンポーネントで整合性がとれていない部分があったため、不具合の原因にもなると思い、親コンポーネント側で値を管理するよう改修した。
  
- 見積書の復元機能の実装において、似たような処理の流れになる部分が多くなると思い、非同期処理とcomputedやリアクティブなデータ関連の複雑な部分の実装や共通関数などを先に実装することで、経験の浅いメンバーが自分のプルリクを参考に実装しやすくなるように工夫した。

- APIを他社が開発しており、不具合が多く正常な値や型で返ってこないことが多かったため、フロント側の開発時、正常な値が来た場合の処理と仮の処理を書くことで、レビュアーが動作確認しやすくするかつAPI修正完了時にすぐに対応できるように工夫した。

- 経験の浅いメンバーのプルリクのレビューの際に、不具合箇所の指摘に加え、参考記事やドキュメントを添付し自身で考えて解決するよう促したり、期限が近づいている場合はどの辺を修正するかまで書いたり、状況に応じて工夫した。

- 既存の処理の長い関数内の不具合を修正する際、即時関数を使い、切り出すほどではない処理をまとめるかつ変数のスコープを小さくした。
  
- QAの方が起票したチケットの期待値に違和感があったため、PMに確認し先回りしてフィックスさせ、実装者に迷いなく修正できるようアシストした。

- 新機能実装時、QAに渡す前に簡易的なテストケースを作成し、再度全体を確認することでバグを一件だけに抑えられた。

  
</details>

---

<details>
<summary>プロジェクト3(2022/3~5)</summary>

#### 概要
オンラインセミナー開催プラットフォームのリアルタイム配信機能のフロントエンド開発

#### メンバー
- PM: 1人
- フロント：3人
- サーバー：2人
- QA：1人

#### 担当
フロント実装全般、レビュー

#### 技術
JavaScript, Vue2(Options API), SCSS, VonageVideoAPI

#### 主に実装した機能
- 画面共有機能
- デバイス選択機能
- 画面録画機能
- 視聴者強制退出・強制ミュート機能
- 入室許可機能
- 入室・退出機能
- 配信開始終了機能
- 視聴ログ取得機能
- スピーカー・マイクテスト機能
- チャット画面UI

<!-- <details>
<summary>取り組み・工夫した点</summary> -->
  
#### 取り組み・工夫した点

VonageVideoAPIというWebRTC技術を使ったAPIを使い、リアルタイムでセミナー配信をする機能のフロント側の実装を担当しました。

- リアルタイム配信のAPIを使うのが初めてであったのと、今回の開発の肝となる部分であったため、休日も使いながら、自分でAPIを使っていくつか簡単な機能を作ってみることで理解を深めていった。また、そのサンプルコードをメンバーに共有して、フロントチーム内でVonageVideoAPIへの理解を少しでも深めるよう努めた。

- 実装する中で使い勝手が悪いような部分に関しては、積極的に開発リーダーやPMに別案を提案し、少しでもサービスが良くなるよう努めた。例えば、チャットを表示する部分において、無限スクロールとローディングUIをいれる提案や個別質問という機能のホスト側の既読判定の別案などを提案した。

- 未経験のエンジニアの方がいたので、出社しているときは直接会話をしたり、リモートのときはハドルを利用してコミュニケーションを積極的にとった。slackなどのテキストコミュニケーションの際は言い方をやわらかくしたり、感嘆符や絵文字を使うことで、後輩エンジニアの方が質問しやすい空気作りを心がけた。また、誤りやすいコーディングのルールをまとめたり、コードレビューの際も答えをそのまま教えるのではなく、参考記事を載せたりして自分でどのように修正すればいいのかを考えてもらうようにした。

- JavaScriptを使っていることやVonageVIdeoAPIとの繋ぎ込みなどがたくさんあり、初見だとコードが読みづらくなっていたため、jsDocを使うことでコードにドキュメントの側面を持たせるよう工夫をした。

<!-- </details> -->

</details>

---

<details>
<summary>プロジェクト4(2022/1~2)</summary>

#### 概要
オンラインイベント配信サービスのAPI開発

#### メンバー
- PM: 1人
- サーバー：2人

#### 担当
API開実装、改修、GraphQLスキーマ定義

#### 技術
TypeScript, Express, GraphQL, Apollo Server, Prisma

#### 実装した機能
- チケット検索機能
- チケット返金機能
- 手動発券したチケット一覧取得
- 購入通知メール文を動的に変える機能
- 明細メール文作成のバリデーション
- 初期パスワード設定
- アカウントとステージ紐付け機能
など

<!-- <details>
<summary>取り組み・工夫した点</summary> -->
  
#### 取り組み・工夫した点

- GraphQLやPrismaなど初めての技術が多かったため、休日も使い公式のチュートリアルやハンズオン教材などで積極的にキャッチアップを行った。

- 複数のイベント主催者の物販が同時に購入された場合の金額分配処理が必要になり、その際お金の流れを意識した改修作業を行なったこと。
元々のお金の流れとして、購入者からstripeを通して運営者側にお金が送金され、その子アカウントであるイベント主催者に送金される流れ。
この修正において、既存のstripeの分配機能を使用すると、購入者からstripeを通してイベント主催者へ直接金額の送金が行われ、お金の流れが変わってしまうため、stripe（決済処理API）手数料、プラットフォーム（開発しているサービス）手数料、イベント主催者への売り上げ金額、トランザクションなどを考慮した分配処理を作ることで対応した。

- また社内でもあまり知見のない技術スタックであると同時に、先方の予算都合で開発がストップすることがあり、人員の入れ替わりがこれからも多くなると予想し、後任の方用に自分がキャッチアップする際に参考になった教材や記事、環境構築で詰まった点、Stripe決済をローカルでテストする手順などをまとめた。
自分が案件から抜けたあと、後任で入った方からキャッチアップの時間が短縮できて助かったと言ってもらえた。

<!-- </details> -->

</details>

---

<details>
<summary>プロジェクト5(2021/10~12)</summary>

#### 概要
医療支援連携サービスのフロントエンドの改修、バグ修正

#### メンバー
- PM: 1人
- フロント：2 ~ 3人
- サーバー：4 ~ 2人
- インフラ：1人
- アプリ：2人
- QA：2人

#### 担当
フロントの改修作業、APIとの繋ぎ込み、バグ修正

#### 技術
TypeScript, Vue3(Composition API), TailwindCSS

<!-- <details>
<summary>取り組み</summary> -->
  
#### 取り組み

エンジニアとして入社して初めての案件で、TypeScript, Composition API, TailwindCSSなど初めての技術ばかりだったので、休日も使い既存コードや公式ドキュメントを参考に積極的にキャッチアップを行った。

それでもわからない部分のコードに関してはわからないままにせず積極的に質問するようにしていた。

ただ先輩エンジニアの時間を奪う行為でもあるので、質問する際には自分はこういう認識なのですがあってますでしょうか？のように、自分の現在の認識や理解度を述べて、なるべく答えやすいような質問の仕方を心がけていた。

後半の方では、仕様漏れによるバグや実装後の要望が多かったため、QAエンジニアと積極的にコミュニケーションを取りながら、PMへの仕様の確認や機能改修の提案をし、品質向上に務めた。

例えば、カレンダーでの検索機能において、カレンダーの月を変更するとそのタイミングで毎回検索処理が走ってしまっていたので、検索処理を発火するイベントを`@input`イベントを`@change`イベントに置き換えることで、日時の変更が完了しフォーカスが外れた時のみ検索処理が走るようにし、UXを改善をした。

上記の姿勢やキャッチアップの早さを評価いただき、リリース前の2週間ほどの間、1人でフロント側の改修作業、バグ修正を任せて頂き、無事納期に間に合った。

<!-- </details> -->

</details>

## 自己PR
---
私は以下の3点を強みとしています。

■キャッチアップ力

未経験の技術でも、休日なども使いながらキャッチアップすることやその技術を使って簡単な機能を作り理解を深めることで、開発リーダーやPMの方から「キャッチアップが早い」「想定していたより早く戦力になってくれて助かる」と言っていただけます。

■読みやすいコード

エンジニアとして働く上で他人のコードを読み解く時間は必ず発生することやコードは書いた時点で負債になるという考えがあるため、関数やコンポーネントを細かく分けることやコメントアウト、適切な組み込み関数を使うなど、読みやすいコードを常に意識しています。

■主体性

自らプロジェクトの課題を見つけ改善できます。
以前担当した案件で、コンポーネントの肥大化による品質低下問題に着目し、スケジュールに少し余裕ができた段階で技術スタックやコンポーネント設計の見直しを提案し、品質向上に貢献した。


