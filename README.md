# AI VoC - 音声入力したお客様の声のAIによる自動分類
音声などで入力した雑多なお客様の声を生成AIを利用して自動的に分類するアプリです。

> [!Note]
> フィードバックは[ギークフジワラのX](https://x.com/geekfujiwara/status/1904664877660332036)までぜひ！

![image](https://github.com/user-attachments/assets/b6d60ff5-8e67-4f1e-af85-9b4db6a3bb91)

> [!Note]
> PCで音声入力する際には、Windows 11 標準の文字起こし機能をWindows キー + H で起動できます。
>
> スマートフォンでは、iPhoneなどのキーボードの文字起こし機能を利用します。

https://github.com/user-attachments/assets/370d215c-d770-4a3f-ad3b-d55876ad5448

## 業種と利用できる現場、利用場面

### 1. **マーケティングリサーチ**
- **現場**: マーケティング部門、リサーチ会社
- **利用場面**: 顧客フィードバックの分析、トレンドやニーズの把握

### 2. **人事・採用**
- **現場**: 人事部門、採用エージェンシー
- **利用場面**: 採用面接の分析、候補者の適性評価

### 3. **カスタマーサポート**
- **現場**: コールセンター、カスタマーサポート部門
- **利用場面**: 問い合わせやクレームの分析、問題の傾向把握

### 4. **メディア・ジャーナリズム**


## アーキテクチャ
### Power Apps
以下の2つのアプリが含まれています。

* Power Apps キャンバスアプリ: 現場での利用者向けの入力アプリである AI VoC Entryアプリ
* Power Apps モデル駆動型アプリ: 管理部門向けにデータを収集した後に分析に活用できるVoC Management App

![image](https://github.com/user-attachments/assets/e56c68f7-1d77-4986-8d7b-ce888bd83c7e)

### AI Builder
AI Builder によるインタビュー内容の整理機能が含まれています。

![image](https://github.com/user-attachments/assets/96435cfc-4649-46be-adef-e8c22c43a59e)


## セキュリティ
利用者向けのセキュリティロール `VoC Basic User` が提供されています。
自分のレコードは作成、編集、削除でき、自分の部署のレコードは参照できますが、読み取りできるだけで、削除、編集はできません。

![image](https://github.com/user-attachments/assets/be2dbd44-f321-4595-8e49-ea3424af7881)

特定の部署 (チーム) に割当するなどして利用してください。

![image](https://github.com/user-attachments/assets/38bc5e55-50c5-4b95-a7b8-6d99878e9466)

> [!Note]
> セキュリティロールの運用方法についてご不明な場合は、[こちらの私の記事](https://www.geekfujiwara.com/tech/powerplatform/6497/)を参考にしてください。



## 利用イメージ

### 1. 現場での VoC の登録
AI VoC Entryアプリより、生のインタビュー結果を新規から作成し、登録します。

![image](https://github.com/user-attachments/assets/9f0d1ad8-c5e2-4f6a-9844-bbf19bb3fe44)

インタビュー内容を入力します。

![image](https://github.com/user-attachments/assets/57a53860-9aca-4dc0-92b0-9f667b4efb70)

登録ボタンをクリックすると自動的にフォーマットに反映されます。よろしければ確定します。

![image](https://github.com/user-attachments/assets/084a3d09-c741-4d48-a454-8ae3af40fe5d)



### 2. 管理部門のアクション
管理部門では、直ちにその情報を確認することができます。

VoCを登録した、レコードの作成者の所属している部署の情報を元に各店舗からのVoCを確認できます。

確認は、 VoC Management App モデル駆動型アプリで一覧することができます。

* 一覧 (ビュー)

![image](https://github.com/user-attachments/assets/b791bf1f-8634-4751-ab36-4dd335b81a6d)

* 詳細 (フォーム)

![image](https://github.com/user-attachments/assets/f5d6f256-f2b2-444f-aa40-7cad50f8b135)

### 3. 担当者の割当と対策検討
VoCごとに担当者をアサインできます。

![image](https://github.com/user-attachments/assets/8fd05f0f-0d64-454b-892c-97cda25a26a9)


担当者をアサインしたら、その対策を記載します。

![image](https://github.com/user-attachments/assets/4a58fbc8-fa8f-4b90-abc7-06c8f78202d2)


### 4. 分析機能
VoCのステータス管理はビジネスプロセスフロー (BPF) で行っています。
![image](https://github.com/user-attachments/assets/f57bb0d1-874e-4a0c-a5a8-22531a425fb5)

その進捗はダッシュボードで確認できます。

![image](https://github.com/user-attachments/assets/f6935972-e871-48d4-833f-d60f5d68a19a)

ダッシュボードからレコードに遷移することができます。
クローズまで一元的に管理することができます。グラフごとに用意されているこのアイコンをクリックします。

![image](https://github.com/user-attachments/assets/ae725ef9-1a42-4b20-a22f-22763cf4e568)

グラフをクリックすることでレコードをフィルターすることができます。

![image](https://github.com/user-attachments/assets/9bf4367c-20ee-4ccc-b8f1-e86793dfeaac)

例えば受付ステージのレコードのみにフィルターした場合はこのようになります。

![image](https://github.com/user-attachments/assets/65171238-ef31-4286-909b-d578f26aef37)

他にも改善提案から抽出されたキーワードを元に、どのような要望が多いかを分類するグラフがあります。担当している特定の部署に担当者を一括でアサインするときなどに利用できます。

![image](https://github.com/user-attachments/assets/5f7bfa97-eee3-47fc-bb6f-325c67222804)

## 前提条件
AI Builder を利用していますので、Power Apps Premiumアプリが必要です。


## アプリの利用開始方法
### ソリューションのインポート
[最新のソリューションを入手](https://github.com/geekfujiwara/AIVoC/releases/tag/AIVoC)します。

インポートはPower Apps ポータルからソリューションのインポートより行います。

![image](https://github.com/user-attachments/assets/ec94688e-bb66-4c98-a28a-9e228f5a12e0)

アップデートに備えるためにマネージドソリューションのインポートが推奨です。

![image](https://github.com/user-attachments/assets/592ae300-3e8b-4029-abff-471bc6b9220b)

マネージドソリューションの場合、マネージドのタブにインポートされたソリューションが表示されます。

![image](https://github.com/user-attachments/assets/ec3942d0-5881-4108-8730-ca6a5ed1fa3b)

インポート後は、ソリューションを開き、すべてのカスタマイズを公開してから利用します。

![image](https://github.com/user-attachments/assets/f7f17225-4af1-479c-8baf-79b42cf65e39)

アプリはこちらにあります。

![image](https://github.com/user-attachments/assets/04164216-cf68-4488-80ca-52a0afd1d13c)

### 実行ユーザーへのセキュリティ設定
#### セキュリティロール
セキュリティロールを実行を行うユーザーに与えます。部署に割り当てるなどして利用できます。

部署(チーム)への割当についての具体的な利用方法は[私の記事](https://www.geekfujiwara.com/tech/powerplatform/6497/)を参考にしてください。

これにより、その部署(チーム)に所属しているユーザーはデータに対するアクセス権が与えられます。

#### リソースへのアクセス権
続けて、リソースへの共有を与えます。

関係するリソースは2個あります。
キャンバスアプリ、AIモデルです。

キャンバスアプリはこのようにして特定のユーザーやセキュリティグループに対して共有します。

![image](https://github.com/user-attachments/assets/1d828d0d-0077-435b-8cc6-e6919d32a0c7)

モデル駆動型アプリはセキュリティロールに対して共有されているので、ユーザーがセキュリティロールに関係する部署(チーム)に所属していれば、そのままアプリも利用できます。

AI モデルはこのようにして特定のユーザーやセキュリティグループに対して共有します。

![image](https://github.com/user-attachments/assets/c565d3d3-f69f-42d8-bb6b-0bf8d23953d1)

![image](https://github.com/user-attachments/assets/9b74b7d1-aca3-4d84-9c06-05cea2200810)

アプリのURLを共有して実行できるようにしてあげましょう。

## 参考: テストデータ

テストデータとして、以下の顧客の声で試すことができます。AI VoC Entry アプリに入力して試してみてください。

```
顧客属性: 30代女性
「スタッフの接客態度については、とても親切で、質問にも丁寧に答えてくれました。笑顔で対応してくれたのが印象的でした。レジでの対応が迅速で、待ち時間が少なかったことが良かったです。また、商品の場所を尋ねたときに、すぐに案内してくれたのも助かりました。」

「店舗全体の雰囲気については、とても明るくて清潔感がありました。入った瞬間に良い印象を受けました。デザインはモダンで、商品が見やすく配置されていました。動線もスムーズで買い物しやすかったです。」

「提供されている商品やサービスについては、種類が豊富で、欲しいものがすぐに見つかりました。質も非常に高いと思います。特に季節物が入口に配置されていて、すぐに見つけられるのが良かったです。」

「ただ、試着室の数が少なく、待ち時間が長かったのが不便でした。特に土曜日の午後2時から4時の間は混雑していて、試着室の待ち時間が長く感じました。もう少し試着室を増やしてほしいです。支払い方法としてPayPayが使えるのも便利でしたが、他の支払い方法も増やしてほしいです。また、商品の配置についても、もう少し工夫して、特に人気商品や新商品が目立つようにしてほしいです。」

「購入プロセス全体についてはスムーズで、特に問題はありませんでした。レジの待ち時間も短く、ストレスなく買い物ができました。セルフレジが使いやすかったことが良かった点です。支払い方法としてPayPayが使えるのも便利でした。」

「買いたかった商品が一部在庫切れで買えなかったのが残念でした。特に新作のジャケット『Urban Explorer Jacket』が欲しかったのですが、品番12345のブラックがサイズMで在庫切れでした。このジャケットはデザインがシンプルで、どんなコーディネートにも合うので気に入っています。もう少し在庫管理をしっかりしてもらえると助かります。」
```

```
顧客属性: 40代男性
「スタッフの接客態度については、とても親切で、質問にも丁寧に答えてくれました。笑顔で対応してくれたのが印象的でした。レジでの対応が迅速で、待ち時間が少なかったことが良かったです。また、商品の場所を尋ねたときに、すぐに案内してくれたのも助かりました。」

「店舗全体の雰囲気については、とても明るくて清潔感がありました。入った瞬間に良い印象を受けました。デザインはモダンで、商品が見やすく配置されていました。動線もスムーズで買い物しやすかったです。」

「提供されている商品やサービスについては、種類が豊富で、欲しいものがすぐに見つかりました。質も非常に高いと思います。特に季節物が入口に配置されていて、すぐに見つけられるのが良かったです。」

「ただ、試着室の数が少なく、待ち時間が長かったのが不便でした。特に日曜日の午後3時から5時の間は混雑していて、試着室の待ち時間が長く感じました。もう少し試着室を増やしてほしいです。支払い方法としてPayPayが使えるのも便利でしたが、他の支払い方法も増やしてほしいです。また、商品の配置についても、もう少し工夫して、特に人気商品や新商品が目立つようにしてほしいです。」

「購入プロセス全体についてはスムーズで、特に問題はありませんでした。レジの待ち時間も短く、ストレスなく買い物ができました。セルフレジが使いやすかったことが良かった点です。支払い方法としてPayPayが使えるのも便利でした。」

「買いたかった商品が一部在庫切れで買えなかったのが残念でした。特に新作のシャツ『Classic Fit Shirt』が欲しかったのですが、品番11223のブルーがサイズLで在庫切れでした。このシャツはデザインがシンプルで、どんなスタイルにも合うので気に入っています。もう少し在庫管理をしっかりしてもらえると助かります。」
```

```
顧客属性: 30代女性
「スタッフの接客態度については、とても親切で、質問にも丁寧に答えてくれました。笑顔で対応してくれたのが印象的でした。レジでの対応が迅速で、待ち時間が少なかったことが良かったです。また、商品の場所を尋ねたときに、すぐに案内してくれたのも助かりました。」

「店舗全体の雰囲気については、とても明るくて清潔感がありました。入った瞬間に良い印象を受けました。デザインはモダンで、商品が見やすく配置されていました。動線もスムーズで買い物しやすかったです。」

「提供されている商品やサービスについては、種類が豊富で、欲しいものがすぐに見つかりました。質も非常に高いと思います。特に季節物が入口に配置されていて、すぐに見つけられるのが良かったです。」

「ただ、試着室の数が少なく、待ち時間が長かったのが不便でした。特に土曜日の午後2時から4時の間は混雑していて、試着室の待ち時間が長く感じました。もう少し試着室を増やしてほしいです。支払い方法としてPayPayが使えるのも便利でしたが、他の支払い方法も増やしてほしいです。また、商品の配置についても、もう少し工夫して、特に人気商品や新商品が目立つようにしてほしいです。」

「購入プロセス全体についてはスムーズで、特に問題はありませんでした。レジの待ち時間も短く、ストレスなく買い物ができました。セルフレジが使いやすかったことが良かった点です。支払い方法としてPayPayが使えるのも便利でした。」

「買いたかった商品が一部在庫切れで買えなかったのが残念でした。特に新作のジャケット『Urban Explorer Jacket』が欲しかったのですが、品番12345のブラックがサイズMで在庫切れでした。このジャケットはデザインがシンプルで、どんなコーディネートにも合うので気に入っています。もう少し在庫管理をしっかりしてもらえると助かります。」
```


