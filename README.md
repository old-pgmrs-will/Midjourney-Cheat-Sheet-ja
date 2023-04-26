

## 基本パラメータ

### [Aspect Ratios](https://translate.google.com/translate?hl=ja&sl=auto&u=https%3A%2F%2Fdocs.midjourney.com%2Faspect-ratios) / アスペクト比

#### `--aspect` または `--ar`
生成画像のアスペクト比を指定する。 例：`--ar 16:9`
- --ar 1:1
  デフォルトのアスペクト比だが、現代のデジタルカメラには正方形のセンサーを持つものは無く、ごく一部のカメラのオプションメニューとして存在する比率設定。
- --ar 16:9
	現在最も一般的なビデオフォーマットに使われる比率。
- --ar 5:4
  大判や中判のフィルムカメラや、8″x10″や16″x20″の画像をプリントする際に使われる比率。
- --ar 4:3
  ほとんどのスマートフォンやマイクロフォーサーズなどで搭載されているセンサーが4:3。
- --ar 3:2
  現在の写真では最も一般的な比率。デジタル一眼レフカメラ、ミラーレスカメラなどの多くは、センサーサイズを問わず3:2センサーを搭載。

※ アスペクト比設定は基本的に、`4:3` または `16:9` がおすすめです。


### [Chaos](https://translate.google.com/translate?hl=ja&sl=auto&u=https%3A%2F%2Fdocs.midjourney.com%2Fchaos) / カオス

#### `--chaos <number 0–100>`
生成結果の変化の度合い（カオス度）を設定。値が大きいほど予想外・想定外の生成結果をもたらす。デフォルト値は `0` 。カオス値を低く設定したり値を指定しなかったりすると、ジョブを実行するたびに微妙に変化する初期画像グリッドが生成されます。
同じプロンプトでもまったくテイストの異なる画像を生成することがあるので、カオス値を様々に変更しての生成も有意義。


### [No](https://translate.google.com/translate?hl=ja&sl=auto&u=https%3A%2F%2Fdocs.midjourney.com%2Fmulti-prompts) / ネガティブ・プロンプト指定

#### `--no`
いわゆる「ネガティブ・プロンプト」の指定。続くキーワードを生成画像を構成する要素から除外する。

### [Quality](https://translate.google.com/translate?hl=ja&sl=auto&u=https%3A%2F%2Fdocs.midjourney.com%2Fquality) / プロンプトの品質設定

#### `--quality <.25, .5, 1, or 2>`, or `--q <.25, .5, 1, or 2>`
レンダリング品質の時間設定でデフォルトは1。大きいほど高コスト、低いほど低コスト。
このパラメータは「ジョブに **どれだけのレンダリング品質時間を費やすべきかを定義するだけ** 」というのがポイント。値が小さいほどMidjourneyのGPU少時間が少なくて済む。**大きな値＝良い画像を生成という意味ではない** 点に注意。

- デフォルトは `1` 、通常はこの設定で十分。
- 初期のドラフト的な生成や実験には  `0.25` や `0.5` などが最適。 
- ドラフト生成や実験でプロンプトの有効性が確認できたら、デフォルトの `1` に戻せば良い。

### [Repeat](https://translate.google.com/translate?hl=ja&sl=auto&u=https%3A%2F%2Fdocs.midjourney.com%2Frepeat) / ジョブの繰り返し

####  `--repeat <1–40>` または `--r <1–40>`
1つのプロンプトから複数のジョブを作成する。`--repeat` で指定した回数だけ、同じプロンプトを繰り返し実行してくれる。例えば `--repeat 3` と指定すれば、同じプロンプトを3回繰り返し実行してくれる。

### [Seed](https://translate.google.com/translate?hl=ja&sl=auto&u=https%3A%2F%2Fdocs.midjourney.com%2Fseeds) / 画像生成の初期グリッドに適用するシード値

#### `--seed <integer between 0–4294967295>`
Midjourney Botは、初期画像グリッドを生成するための出発点としてテレビの静止画のような視覚ノイズのフィールドを作成するためにシード番号を使用します。
シード番号は画像ごとにランダムに生成されますが、`--seed` または `--sameseed` パラメータで指定することができます。
同じシード番号とプロンプトを使用すると似たテイストの画像が生成されるので、色々試して自分オリジナルのシード値を見つけておくのも良いでしょう。

### [Stop](https://translate.google.com/translate?hl=ja&sl=auto&u=https%3A%2F%2Fdocs.midjourney.com%2Fstop) / 画像生成ジョブの停止

#### `--stop <integer between 10–100>`
Jobを途中で終了させる場合は `--stop` パラメータを使用します。
より早いタイミングでジョブを停止すると、よりぼやけた、より詳細でない結果が得られます。

### [Style](https://translate.google.com/translate?hl=ja&sl=auto&u=https%3A%2F%2Fdocs.midjourney.com%2Fmodels)/ 画像スタイルの切り替え（主にv4系とNiji系）

#### `--style <4a, 4b, or 4c>`
Midjourney [Model Version](https://translate.google.com/translate?hl=ja&sl=auto&u=https%3A%2F%2Fdocs.midjourney.com%2Fdocs%2Fmodels) 4 に切り替えて使用。
#### `--style <expressive, or cute>`
Niji [Model Version](https://translate.google.com/translate?hl=ja&sl=auto&u=https%3A%2F%2Fdocs.midjourney.com%2Fdocs%2Fmodels) 5 に切り替えて使用。

※ `4a, 4b, or 4c` は、`/setting` で `MJ version 4` になっている必要があり、`MJ version 5` 環境ではエラーとなります。
※ `expressive, or cute` は主にアニメやコミック系の表現用で `/setting` で `Niji version` になっている必要があります。
- `expressive` = 表情豊か
- `cute` = かわいい

### [Stylize](https://translate.google.com/translate?hl=ja&sl=auto&u=https%3A%2F%2Fdocs.midjourney.com%2Fstylize) / 芸術性の加味・軽減

#### `--stylize <number>`, or `--s <number>`
このパラメータは、Midjourneyのデフォルトの美的スタイルが画像生成ジョブにどの程度強く適用されるかに影響します。
stylize の値が低い場合、プロンプトに近い画像が生成されますが芸術性は低くなります。
stylize の値が高い場合、とても芸術的な画像が作成されますがプロンプトとの関連性は低くなります。

### [Uplight](https://translate.google.com/translate?hl=ja&sl=auto&u=https%3A%2F%2Fdocs.midjourney.com%2Fupscalers) / 軽量（？）

#### `--uplight`
`U` ボタンを選択する際に、代替の「ライト（軽量？）」アップスケーラーを使用する。結果はオリジナルのグリッド画像に近くなります。アップスケーリングされた画像は、より詳細で滑らかなものになります。

### [Upbeta](https://translate.google.com/translate?hl=ja&sl=auto&u=https%3A%2F%2Fdocs.midjourney.com%2Fupscalers) / ベータ

#### `--upbeta`
`U` ボタンを選択する際に、代替のベータアップスケーラーを使用する。結果は元のグリッド画像に近くなります。アップスケーリングされた画像は、追加されたディテールが大幅に減少します。

※ アップスケーラーについて。Midjourneyはまず、各ジョブの低解像度イメージのグリッドを生成します。Midjourneyのアップスケーラーを使用することでグリッドイメージのサイズを拡大し、詳細度を上げることができます。画像のアップスケーリングには複数のアップスケーリングモデルが用意されています。

---

## モデルバージョン・パラメータ

Midjourneyは、効率性・一貫性・品質の向上のために定期的に新しいモデルのバージョンをリリースしています。モデルによって、得意とする映像（画質・テイスト）が異なります。

### [Niji](https://translate.google.com/translate?hl=ja&sl=auto&u=https%3A%2F%2Fdocs.midjourney.com%2Fmodels) / 二次・二次元（アニメ調）

#### `--niji`
アニメ調の映像に着目した代替モデル。

### [High Definition](https://translate.google.com/translate?hl=ja&sl=auto&u=https%3A%2F%2Fdocs.midjourney.com%2Fmodels) / 高精細度

#### `--hd`
より大きく、より一貫性のない画像を生成する初期の代替モデルを使用します。このアルゴリズムは抽象的な画像や風景画像に適していると思われます。

### [Test](https://translate.google.com/translate?hl=ja&sl=auto&u=https%3A%2F%2Fdocs.midjourney.com%2Fmodels)

#### `--test`
特別テストモデルを使用します。（詳しくはリンク先参照）

### [Testp](https://translate.google.com/translate?hl=ja&sl=auto&u=https%3A%2F%2Fdocs.midjourney.com%2Fmodels)

#### `--testp`
特殊撮影に特化したテストモデルを使用します。（詳しくはリンク先参照）

※ 時折、コミュニティのテストとフィードバックのために新しいモデルが一時的にリリースされることがあります。現在、テストモデルには `--test` と `--testp` の2種類があり、`--creative` パラメータと組み合わせることで、より多様なコンポジションが可能です。

### [Version](https://translate.google.com/translate?hl=ja&sl=auto&u=https%3A%2F%2Fdocs.midjourney.com%2Fmodels) / バージョン

#### `--version <1, 2, 3, 4, or 5>` または `--v <1, 2, 3, 4, or 5>`
Midjourneyのアルゴリズムの異なるバージョンを使用します。現在のアルゴリズム（V4）が初期設定です。

---

## アップスケーラー・パラメータ

Midjourneyはまず、各ジョブの低解像度イメージのグリッドを生成します。Midjourneyのアップスケーラーを使用することで、グリッドイメージのサイズを拡大し、詳細を追加することができます。画像のアップスケーリングには、複数のアップスケーリングモデルが用意されています。

### [Uplight](https://translate.google.com/translate?hl=ja&sl=auto&u=https%3A%2F%2Fdocs.midjourney.com%2Fupscalers) / 軽量（？）

#### `--uplight`
`U` ボタンを選択する際に、代替の「ライト（軽量？）」アップスケーラーを使用する。結果はオリジナルのグリッド画像に近くなります。アップスケーリングされた画像は、より詳細で滑らかなものになります。

### [Upbeta](https://translate.google.com/translate?hl=ja&sl=auto&u=https%3A%2F%2Fdocs.midjourney.com%2Fupscalers) / ベータ

#### `--upbeta`
`U` ボタンを選択する際に、代替のベータアップスケーラーを使用する。結果は元のグリッド画像に近くなります。アップスケーリングされた画像は、追加されたディテールが大幅に減少します。

### [Upanime](https://translate.google.com/translate?hl=ja&sl=auto&u=https%3A%2F%2Fdocs.midjourney.com%2Fupscalers) / アニメ調

`U` ボタンを選択したときに動作するように訓練された、別のアップスケーラーを使用してください。このアップスケーラーは、モデル `--niji` のために特別に作られました。

---

## 他のパラメータ

これらのパラメータは、特定のMidjourneyの初期モデルでのみ動作します。

### [Creative](https://translate.google.com/translate?hl=ja&sl=auto&u=https%3A%2F%2Fdocs.midjourney.com%2Fmodels)

#### `--creative`
`test` と `testp` のモデルを、より多様で創造的なものに変更する。

### [Image Weight](https://translate.google.com/translate?hl=ja&sl=auto&u=https%3A%2F%2Fdocs.midjourney.com%2Fimage-prompts)

#### `--iw`
テキストの重みに対する画像のプロンプトの重みを設定する。デフォルトは `--iw 0.25` です。

### [Sameseed](https://translate.google.com/translate?hl=ja&sl=auto&u=https%3A%2F%2Fdocs.midjourney.com%2Fseeds

#### `--sameseed`
シード値は初期グリッドのすべての画像に適用される単一の大きなランダムなノイズフィールドを作成します。Sameseedを指定すると、初期グリッド内のすべての画像で同じ開始ノイズが使用され、とてもよく似た生成画像が得られます。

### [Video](https://translate.google.com/translate?hl=ja&sl=auto&u=https%3A%2F%2Fdocs.midjourney.com%2Fvideo)

#### `--video`
最初のイメージグリッドが生成されるまでの経過動画を保存します。完成したイメージグリッドに絵文字を反応させ、 ✉️ でダイレクトメッセージに動画を送信するトリガーになります。`--video`  は、画像をアップスケーリングするときには機能しません。

---

## 画像生成時に使えるプロンプト・チートシート

ここでは、一般的な画像生成のスタイルとその特徴を紹介します：

| Style | Description |
| ----- | ----------- |
| 1990s point and click 16bit adventure game | 1990年代スタイルの16ビット・アドベンチャー系ゲーム風 |
| 32-bit isometric | 32ビット・ピクセルアート風 |
| 35mm film | より鮮やかな色彩だが、彩度は控えめで、前景や背景の要素を追加したディテール |
| 8k | 照明がより過激になる傾向があり、色は「ハイビジョン」よりもさらに彩度が高く、CGのように見える。|
| cinematic | 影はより極端になる傾向がある（暗くはないが）、オブジェクトは少し厚くなる、よりポスター的になる |
| color grading | 色相が極端に変化する、鮮やかだが過飽和ではない色 |
| colorful | 色彩が豊かで明るい表現。 |
| depth of field | 被写体にシャープなピントを合わせ、背景と前景をぼかす。 |
| diagramatic drawming | あるものがどのように機能するかを実証または説明するため、または全体の部分間の関係を明確にするために設計された計画、スケッチ、図面、または輪郭。 |
| duotone | 1枚の原画から、異なる画面の角度で2色のカラーを使ったイラストを作成 |
| film lighting | 光源が限られている、逆光が多い、光源が落とす影が深い |
| fine ultra-detailed realistic | 少し粒子が粗く、"ロープ状 "になることがありますが、ディテール生成は向上します。 |
| Hasselblad H6D | 被写体へのピントがよりシャープになり、陰影がより濃くなる。 |
| high definition | 影が薄くなり、より幻想的で彩度の高い色になる |
| intricate | 非現実的な「クラフト」「パターン」系のデザインに寄ります。|
| motion-blur | いわゆる「モーションブラー」表現。動いている対象をカメラで撮影した時に生じるブレや風が吹いているように見えることがある |
| op art | オプティカルアート：形や色、模様を特殊な方法で使い、あたかも動いたり、ぼやけたりしているように見える映像表現。 |
| patchwork collage | アートスタイル・キルトとしてデザインするための重ね布の風合いを表現。 |
| photography | 被写体の周囲にオブジェクトの小さな領域があり、背景には他のオブジェクトがほとんどない傾向がある。 |
| realism | 芸術的なリアリズム。背景がより均一である傾向があり、被写体がより絵画のように見える。被写体とともに多くのオブジェクトを描画します。 |
| rendered for IMAX | より複雑な被写体を、指向性の強い照明と控えめな彩度で表現。 |
| rim lighting | `film lighting` よりもやや強い照明効果ですが、非常によく似た仕上がりです。|
| stained glass window | ステンドグラス風。ガラスに色をつけ様々な形にカットして絵や模様を描いたもので、特に教会の窓に使われるもの。 |
| synthwave | 1980年代のアクション、SF、ホラー映画のサウンドトラックに関連した音楽を主なベースとする電子音楽のマイクロジャンルをイメージしたもの |
| tilt-shift | "depth of field" に類似。していますが、上空あるいは高角度からの表現。 |
| ultra photorealistic | `fine ultra-detailed realistic` に類似した表現になる |
| Ultra wide lens --v 4 | 魚眼レンズ風 |
| Ultra wide lens --v 5 --ar 16:9 | 広角レンズ風 |
| watercolor sketch | 水彩画の作品を短時間で完成させる、ゆるやかでカジュアルなスタイル。 |


## 参考文献

- [OFFICIAL - Midjourney Parameter List](https://docs.midjourney.com/docs/parameter-list)
- [PaulGG-Code / Midjourney-Cheat-Sheet](https://github.com/PaulGG-Code/Midjourney-Cheat-Sheet)

