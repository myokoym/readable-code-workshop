# 課題

リーダブルコードワークショップで開発するプログラムについて説明します。

## 概要

開発するプログラムは「レシピ管理プログラム」です。

このワークショップの目的は「日々リーダブルコードを書いているプログラマー」にステップアップすることです。ワークショップ当日だけのレベルアップは目的ではありません。

目的を達成するために「リーダブルコードを発見できるようになること」を目指しますが、「リーダブルコードのテクニックをたくさん覚えること」や「難しいプログラムでも実装できるようになること」、「速く実装できるようになること」は目指すことではありません。そのため、次の点に注意して開発するプログラムの仕様を用意しました。

  * 言語の基本的な機能のみで実現できる。
    * ライブラリーを知っていることや使えることは重要ではない。
  * 難しいロジックを必要としない。
    * 効率のよいアルゴリズムを考えることは重要ではない。
  * 段階的に改良していく。
    * 書き捨てのプログラムではなく継続的に開発するプログラムであることは重要である。
  * すべての仕様を実装しなくてもよい。
    * 今回の実装時間は170分で仕様は13個ある。平均して13分で1つ実装するとすべての仕様を実装できるが、「速く実装できるようになること」は目的ではないので、すべての仕様を実装することは重要ではない。

開発するコードは「今の自分で最高にリーダブルなコード」にしてください。そのとき、「どうしてこのコードはリーダブルと言えるのか」の理由も考えてください。例えば、「 `do_something` では何かをするのはわかるけど何をするのかわからないが、 `open_file` ならファイルを開くということがすぐわかるのでリーダブルだ」といった具合です。

理由を考えるのは、理由をつけられるくらい考えていれば応用が効くからです。前述の例の理由からは「何をするのかわかる名前がよい」という基準を見つけられます。この基準を使えば、違うコードでもリーダブルなコードを書けます。

### リーダブルコードを書くヒント

1つ、リーダブルコードを書くためのヒントを伝えます。それは、「書く時に読む人の視点を持つこと」です。

リーダブルコードとはどのようなコードだと思いますか？読む人がリーダブルだと思ったら、それはその人にとってリーダブルコードです。読む人にとって前提知識が違うので、より多くの人がリーダブルだと思うコードもありますし、同じ開発チームの人たちだけがリーダブルだと思うコードもあります。どちらを選ぶかは「読む人」をどのように設定したかに依存します。必ずしも「より多くの人」を選ぶことが妥当なわけではありません。例えば…、と書き始めるとヒントではなくなってしまいますね。ここで止めておくことにします。

書く時は「どんな人が読むコードか」を意識してみてください。それが、読む人の視点を持つことにつながります。

## 進め方

プログラムを1から開発します。後述する仕様を実現するようにプログラムを開発します。仕様は複数あり、仕様1を実装したら、仕様2を実装する、というように、同じプログラムを改良しながら仕様を実現していきます。

すべての仕様をいかに速く実装するか、ということは目的では **ありません** 。プログラムを開発しながら「日々リーダブルコードを書いているプログラマー」に近づくことが目的です。「1番速く実装したけどリーダブルコードについてはなにも得られることがなかった」というケースはこのワークショップでは失敗ケースです。目的を見失わないようにしましょう。

1つ仕様を実装する毎にGitHubにcommit + pushしてください。

例：

  * 仕様1を実装
  * commit + push
  * 仕様2を実装
  * commit + push
  * ...

仕様を実装した状態でcommit + pushしていれば、1つの仕様を実装する間に何回commit/pushしても構いません。

例:

  * 仕様1を実装開始
  * 仕様1を30%実装
  * commit
  * 仕様1を60%実装
  * commit + push
  * 仕様1を90%実装
  * commit
  * 仕様1を100%実装
  * commit + push
  * ...

コミットメッセージにはどの仕様を実装しているかがわかるマークを入れてください。具体的には、コミットメッセージの最初に `spec${仕様番号}: ` と入れてください。

仕様1を実装しているときのコミット例:

    % git commit -m "spec1: add a sample script"
    % git commit -m "spec1: 並び替え機能を追加"

仕様3を実装しているときのコミット例:

    % git commit -m "spec3: fix a typo"
    % git commit -m "spec3: 異常値のときのテストを追加"

これは、どの仕様を実装しているかをわかりやすくするためです。後からこのコードを「読む人」がいるということを思い出してください。

## 仕様

それぞれの仕様には次の2点を明記しています。仕様を実装した後は、各自、これらを使って仕様を満たしているかどうかを確認してください。不安な場合はメンターに質問したり、確認をお願いしてください。

  * 入力
  * 期待する結果

### 仕様1：レシピを出力

レシピのタイトルとして「オムライス」と出力するプログラムを新しく作ってください。

#### 入力

なし

#### 期待する結果

プログラムを実行したらなんらかの形で「オムライス」と出力してください。コンソールに出力しても構いませんし、ファイルに出力しても、ウィンドウを作ってそこに出力しても、Webブラウザーに表示させても構いません。なんらかの形で「オムライス」と出力してください。

#### 実現例

recipe.sh：

    #!/bin/sh

    echo "オムライス"

実行：

    % chmod +x recipe.sh
    % ./recipe.sh
    オムライス

#### 実現後

仕様1を実現したらメンターに声をかけて結果を確認してもらってください。仕様1は練習です。仕様1でうまくできていたら仕様2以降もうまくやれるはずです。

### 仕様2：同じグループの人がプログラムを実行できること

同じグループの人があなたが書いたプログラムを実行できるように、実行手順を書いたREADME.mdを用意してください。

#### 入力

なし

#### 期待する結果

README.mdに書かれた手順に従って作業すれば、このプログラムが仕様1を満たしていることを確認できるようにしてください。

### 仕様3：レシピデータを別ファイルに分離すること

今はプログラム中に「オムライス」のレシピが埋め込まれているはずです。そのレシピ情報をデータとして別のファイルに保存し、プログラムとは分離してください。

ファイルのフォーマットは問いません。

どのようにファイルを指定するかも問いません。

どのようなフォーマットにしたか、どのようにファイルに指定するかはREADME.mdに記述してください。

#### 入力

  * データファイル
    * ファイル名は任意。例: recipe-data.txt
    * 中身は「オムライス」というレシピ情報1つだけ。
    * データファイルはリポジトリーに入れること

データファイルは、例えば次のような内容：

    % cat recipe-data.txt
    オムライス
    %

#### 期待する結果

プログラムを実行したらなんらかの方法でデータファイルを読み込み、データファイル内にある「オムライス」というレシピ情報をロードしてください。そして、そのレシピ情報を出力してください。

実行例：

    % ./recipe.sh recipe-data.txt
    オムライス
    %

README.mdを読めば、グループの他の人でもファイルを作成してプログラムにレシピ情報をロードできるようにしてください。

### 仕様4：データファイルに3つのデータを保存できること

今のデータファイルは「オムライス」しかレシピ情報が入っていません。これを、次の3つのレシピ情報を登録できるようにします。

  * オムライス
  * 親子丼
  * 杏仁豆腐

また、登録されているすべてのレシピを出力してください。

レシピ情報のフォーマットは問いません。

どのようなフォーマットにしたかはREADME.mdに記述してください。

#### 入力

  * データファイル
    * ファイル名は任意。例: recipe-data.txt
    * 中身は次の3つのレシピ情報。
      * オムライス
      * 親子丼
      * 杏仁豆腐

データファイルは、例えばこういう内容です。

    % cat recipe-data.txt
    オムライス
    親子丼
    杏仁豆腐
    %

#### 期待する結果

プログラムを実行したらなんらかの方法でデータファイルを読み込み、データファイル内にある3つのレシピ情報をロードしてください。そして、そのレシピ情報をすべて出力してください。

実行例：

    % ./recipe.sh recipe-data.txt
    オムライス
    親子丼
    杏仁豆腐
    %

READMEを読めば、グループの他の人でもファイルを作成できるようにしてください。

### 仕様5：レシピにIDを振ること

今のプログラムは同じ料理のレシピを複数登録すると区別できません。登録されたレシピにプログラム内で自動でID（レシピを一意に識別できる識別子）を振ってレシピを区別できるようにしてください。IDは数値でも文字列でも一意であればなんでも構いません。

出力するときはIDも出力してください。

#### 入力

  * データファイル
    * 中身は前の仕様と同じ次の3つのレシピ情報。
      * オムライス
      * 親子丼
      * 杏仁豆腐

データファイルは、例えばこういう内容です。

    % cat recipe-data.txt
    オムライス
    親子丼
    杏仁豆腐
    %

#### 期待する結果

プログラムを実行したら読み込んだレシピ情報になんらかの方法でIDを振ってください。そして、そのレシピ情報をID付きですべて出力してください。

実行例：

    % ./recipe.sh recipe-data.txt
    1: オムライス
    2: 親子丼
    3: 杏仁豆腐
    %

### 仕様6：IDを指定したレシピだけ出力すること

今のプログラムは読み込んだレシピをすべて表示します。IDを指定した場合は指定したIDのレシピだけを表示してください。

IDの指定方法は問いません。

IDの指定方法はREADME.mdに記述してください。

指定されるIDは必ず存在するIDと仮定してください。

IDを指定されなかった場合の挙動は変えないでください。

#### 入力

  * データファイル
    * 中身は前の仕様と同じ次の3つのレシピ情報。
      * オムライス
      * 親子丼
      * 杏仁豆腐
  * ID

#### 期待する結果

プログラムを実行したらレシピ情報を読み込んでください。その後、指定されたIDのレシピのみ表示してください。

IDを指定されなかった場合はすべてのレシピを表示してください。

実行例：

    % ./recipe.sh recipe-data.txt 2
    2: 親子丼
    % ./recipe.sh recipe-data.txt
    1: オムライス
    2: 親子丼
    3: 杏仁豆腐
    %

README.mdを読めば、グループの他の人でもIDを指定できるようにしてください。

### 仕様7：レシピに説明文を関連付けること

今のプログラムはレシピの料理名しか情報を持っていません。それぞれのレシピに説明文を関連付けられるようにしてください。説明文には作り方を書きます。

出力時は料理名と説明文の両方を表示してください。

説明文は長くても4KiBとします。

データファイルのフォーマットは問いません。

どのようなフォーマットにしたかはREADME.mdに記述してください。

#### 入力

  * データファイル
    * ファイル名は任意。例: recipe-data.txt
    * 中身は次の3つのレシピ情報。
      * オムライス
      * 親子丼
      * 杏仁豆腐
    * それぞれに説明文を関連付けること

データファイルは、例えばこういう内容です。

    % cat recipe-data.txt
    オムライス 卵を焼いてごはんにのせる
    親子丼 鶏肉を焼いて卵でとじてごはんにのせる
    杏仁豆腐 牛乳と砂糖をまぜてゼラチンで固める
    %

#### 期待する結果

プログラムを実行したら説明文入りレシピ情報を読み込み、読み込んだレシピ情報を表示します。

実行例：

    % ./recipe.sh recipe-data.txt
    1: オムライス 卵を焼いてごはんにのせる
    2: 親子丼 鶏肉を焼いて卵でとじてごはんにのせる
    3: 杏仁豆腐 牛乳と砂糖をまぜてゼラチンで固める
    %

README.mdを読めば、グループの他の人でも説明文を関連付けられるようにしてください。

### 仕様8：レシピ情報を持っているユーザー名を指定できること

今のプログラムはレシピ情報の集まりをロードして出力するだけです。これに、だれが集めたレシピ情報かを指定できるようにしてください。「だれ」のことを「ユーザー名」と呼ぶことにします。出力するときはユーザー名も出力してください。

ユーザー名に使える文字は次の通りとします。

  * 小文字のアルファベット
  * 数字
  * ハイフン
  * アンダーバー

ユーザー名は長くても10文字とします。

この条件を満たさないユーザー名が指定されることはないと仮定して構いません。

ユーザー名の指定方法は問いません。

どのような指定方法にしたかはREADME.mdに記述してください。

ユーザー名の出力方法は問いません。

#### 入力

  * データファイル
    * ファイル名は任意。例: recipe-data.txt
    * 中身は次の3つのレシピ情報。
      * オムライス
      * 親子丼
      * 杏仁豆腐
    * それぞれに説明文を関連付けること
  * レシピを集めているユーザー名

データファイルは、例えばこういう内容です。

    % cat recipe-data.txt
    オムライス 卵を焼いてごはんにのせる
    親子丼 鶏肉を焼いて卵でとじてごはんにのせる
    杏仁豆腐 牛乳と砂糖をまぜてゼラチンで固める
    %

#### 期待する結果

プログラムを実行したら、レシピ情報とそのレシピ情報を集めているユーザー名を受け取り、ユーザー名と読み込んだレシピ情報を表示します。IDを指定したら指定したレシピだけ表示する機能は壊さないでください。

実行例：

    % ./recipe.sh kou recipe-data.txt
    ユーザー名: kou
    1: オムライス 卵を焼いてごはんにのせる
    2: 親子丼 鶏肉を焼いて卵でとじてごはんにのせる
    3: 杏仁豆腐 牛乳と砂糖をまぜてゼラチンで固める
    % ./recipe.sh kou recipe-data.txt 2
    ユーザー名: kou
    2: 親子丼 鶏肉を焼いて卵でとじてごはんにのせる
    %

README.mdを読めば、グループの他の人でもユーザー名を指定できるようにしてください。

### 仕様9：4人のユーザーのレシピ情報をサポートすること

今のプログラムは1人のユーザーのレシピ情報だけを扱えますが、これを4人のユーザーのレシピ情報も扱えるようにしてください。

出力するときはユーザー毎にレシピを出力してください。

ユーザー名とそのユーザーのレシピ情報の指定方法は問いません。

どのような指定方法にしたかはREADME.mdに記述してください。

ユーザー名は重複するかもしれません。

#### 入力

  * ユーザー名とデータファイルのペアを4つ
    * データファイル内のレシピ数は3つ
    * 1つはこれまで使ってきたデータファイルを使うこと
    * 残りの3つはこれまで使ってきたデータファイルを参考に新しく作ること
    * 異なるユーザーで同じレシピ情報を持っているかもしれない
      * 例：ユーザー1とユーザー2のどちらにも「オムライス」がある
    * すべてのレシピは異なるIDを持つこと
    * すべてのデータファイルはリポジトリーに入れること

データファイルは、例えば次のような内容です。

    % cat recipe-data1.txt
    オムライス 卵を焼いてごはんにのせる
    親子丼 鶏肉を焼いて卵でとじてごはんにのせる
    杏仁豆腐 牛乳と砂糖をまぜてゼラチンで固める
    % cat recipe-data2.txt
    オムライス 卵を焼いてごはんにのせる
    鶏の唐揚げ 鶏肉にから揚げ粉をまぶして揚げる
    カレー 野菜を切って煮込んでカレー粉を入れる
    % cat recipe-data3.txt
    トマトサラダ トマトと野菜を切ってまぜる
    生ハムサラダ 生ハムと野菜を切ってまぜる
    和風サラダ 豆腐と野菜を切ってまぜて醤油ベースのドレッシングをかける
    % cat recipe-data4.txt
    チョコケーキ 薄力粉とココアと卵とバターをまぜて焼く
    スイートポテト 蒸したさつまいもと砂糖とバターと生クリームをまぜて焼く
    杏仁豆腐 牛乳と砂糖をまぜてゼラチンで固める
    %

#### 期待する結果

プログラムを実行したら、レシピ情報とそのレシピ情報を集めているユーザー名を受け取り、ユーザー名と読み込んだレシピ情報を表示します。IDを指定したら指定したレシピだけ表示する機能を壊さないでください。

実行例：

    % ./recipe.sh kou recipe-data1.txt piro recipe-data2.txt okkez recipe-data3.txt kou recipe-data4.txt
    ユーザー名: kou
    1: オムライス 卵を焼いてごはんにのせる
    2: 親子丼 鶏肉を焼いて卵でとじてごはんにのせる
    3: 杏仁豆腐 牛乳と砂糖をまぜてゼラチンで固める

    ユーザー名: piro
    4: オムライス 卵を焼いてごはんにのせる
    5: 鶏の唐揚げ 鶏肉にから揚げ粉をまぶして揚げる
    6: カレー 野菜を切って煮込んでカレー粉を入れる

    ユーザー名: okkez
    7: トマトサラダ トマトと野菜を切ってまぜる
    8: 生ハムサラダ 生ハムと野菜を切ってまぜる
    9: 和風サラダ 豆腐と野菜を切ってまぜて醤油ベースのドレッシングをかける


    ユーザー名: kou
    10: チョコケーキ 薄力粉とココアと卵とバターをまぜて焼く
    11: スイートポテト 蒸したさつまいもと砂糖とバターと生クリームをまぜて焼く
    12: 杏仁豆腐 牛乳と砂糖をまぜてゼラチンで固める
    % ./recipe.sh kou recipe-data1.txt piro recipe-data2.txt okkez recipe-data3.txt sunaot recipe-data4.txt 5
    ユーザー名: kou

    ユーザー名: piro
    5: 鶏の唐揚げ 鶏肉にから揚げ粉をまぶして揚げる

    ユーザー名: okkez

    ユーザー名: kou
    %

README.mdを読めば、グループの他の人でもユーザー名と対応するデータファイルを指定できるようにしてください。

### 仕様10：ユーザーにIDを振ること

今のプログラムは同じユーザー名だと区別できません。指定されたユーザーにプログラム内で自動でID（ユーザーを一意に識別できる識別子）を振ってユーザーを区別できるようにしてください。IDは数値でも文字列でも一意であればなんでも構いません。

出力するときはIDも出力すること。

#### 入力

  * ユーザー名とデータファイルのペアを4つ
    * データファイル内のレシピ数は3つ
    * 1つはこれまで使ってきたデータファイルを使うこと
    * 残りの3つはこれまで使ってきたデータファイルを参考に新しく作ること
    * 異なるユーザーで同じレシピ情報を持っているかもしれない
      * 例：ユーザー1とユーザー2のどちらにも「オムライス」がある
    * すべてのレシピは異なるIDを持つこと

データファイルは、例えば次のような内容です。

    % cat recipe-data1.txt
    オムライス 卵を焼いてごはんにのせる
    親子丼 鶏肉を焼いて卵でとじてごはんにのせる
    杏仁豆腐 牛乳と砂糖をまぜてゼラチンで固める
    % cat recipe-data2.txt
    オムライス 卵を焼いてごはんにのせる
    鶏の唐揚げ 鶏肉にから揚げ粉をまぶして揚げる
    カレー 野菜を切って煮込んでカレー粉を入れる
    % cat recipe-data3.txt
    トマトサラダ トマトと野菜を切ってまぜる
    生ハムサラダ 生ハムと野菜を切ってまぜる
    和風サラダ 豆腐と野菜を切ってまぜて醤油ベースのドレッシングをかける
    % cat recipe-data4.txt
    チョコケーキ 薄力粉とココアと卵とバターをまぜて焼く
    スイートポテト 蒸したさつまいもと砂糖とバターと生クリームをまぜて焼く
    杏仁豆腐 牛乳と砂糖をまぜてゼラチンで固める
    %

#### 期待する結果

プログラムを実行したら読み込んだユーザーになんらかの方法でIDを振る。そして、そのユーザー名をID付きですべて出力する。

実行例:

    % ./recipe.sh kou recipe-data1.txt piro recipe-data2.txt okkez recipe-data3.txt kou recipe-data4.txt
    ユーザー: 1: kou
    1: オムライス 卵を焼いてごはんにのせる
    2: 親子丼 鶏肉を焼いて卵でとじてごはんにのせる
    3: 杏仁豆腐 牛乳と砂糖をまぜてゼラチンで固める

    ユーザー: 2: piro
    4: オムライス 卵を焼いてごはんにのせる
    5: 鶏の唐揚げ 鶏肉にから揚げ粉をまぶして揚げる
    6: カレー 野菜を切って煮込んでカレー粉を入れる

    ユーザー: 3: okkez
    7: トマトサラダ トマトと野菜を切ってまぜる
    8: 生ハムサラダ 生ハムと野菜を切ってまぜる
    9: 和風サラダ 豆腐と野菜を切ってまぜて醤油ベースのドレッシングをかける

    ユーザー: 4: kou
    10: チョコケーキ 薄力粉とココアと卵とバターをまぜて焼く
    11: スイートポテト 蒸したさつまいもと砂糖とバターと生クリームをまぜて焼く
    12: 杏仁豆腐 牛乳と砂糖をまぜてゼラチンで固める

### 仕様11: IDを指定したユーザーだけ表示すること

今のプログラムはすべてのユーザーを表示します。IDを指定した場合は指定したIDのユーザーだけを表示してください。

IDの指定方法は問いません。

IDの指定方法はREADME.mdに記述してください。

指定されるIDは必ず存在するIDと仮定して構いません。

IDを指定されなかった場合の挙動は変えないでください。

ユーザーIDとレシピIDを指定した場合は該当ユーザーの該当レシピ情報だけ表示してください。レシピIDは指定したユーザーが持っているレシピのIDであると仮定して構いません。

#### 入力

  * ユーザー名とデータファイルのペアを4つ
    * データファイル内のレシピ数は3つ
    * 1つはこれまで使ってきたデータファイルを使うこと
    * 残りの3つはこれまで使ってきたデータファイルを参考に新しく作ること
    * 異なるユーザーで同じレシピ情報を持っているかもしれない
      * 例：ユーザー1とユーザー2のどちらにも「オムライス」がある
    * すべてのレシピは異なるIDを持つこと
  * ユーザーID

データファイルは、例えば次のような内容です。

    % cat recipe-data1.txt
    オムライス 卵を焼いてごはんにのせる
    親子丼 鶏肉を焼いて卵でとじてごはんにのせる
    杏仁豆腐 牛乳と砂糖をまぜてゼラチンで固める
    % cat recipe-data2.txt
    オムライス 卵を焼いてごはんにのせる
    鶏の唐揚げ 鶏肉にから揚げ粉をまぶして揚げる
    カレー 野菜を切って煮込んでカレー粉を入れる
    % cat recipe-data3.txt
    トマトサラダ トマトと野菜を切ってまぜる
    生ハムサラダ 生ハムと野菜を切ってまぜる
    和風サラダ 豆腐と野菜を切ってまぜて醤油ベースのドレッシングをかける
    % cat recipe-data4.txt
    チョコケーキ 薄力粉とココアと卵とバターをまぜて焼く
    スイートポテト 蒸したさつまいもと砂糖とバターと生クリームをまぜて焼く
    杏仁豆腐 牛乳と砂糖をまぜてゼラチンで固める
    %

#### 期待する結果

プログラムを実行したらユーザー名と対応するレシピ情報を読み込んでください。その後、指定されたIDのユーザーのみ表示してください。

実行例：

    % ./recipe.sh kou recipe-data1.txt piro recipe-data2.txt okkez recipe-data3.txt kou recipe-data4.txt 4
    ユーザー: 4: kou
    10: チョコケーキ 薄力粉とココアと卵とバターをまぜて焼く
    11: スイートポテト 蒸したさつまいもと砂糖とバターと生クリームをまぜて焼く
    12: 杏仁豆腐 牛乳と砂糖をまぜてゼラチンで固める

レシピIDも指定されたら該当ユーザーの該当レシピ情報だけ表示してください。

実行例:

    % ./recipe.sh kou recipe-data1.txt piro recipe-data2.txt okkez recipe-data3.txt kou recipe-data4.txt 4 11
    ユーザー: 4: kou
    11: スイートポテト 蒸したさつまいもと砂糖とバターと生クリームをまぜて焼く

レシピIDだけ指定したときはこれまでと同じ挙動にしてください。次の例は、ユーザーIDに-1を指定したらユーザーIDは指定なしという仕様にしています。

実行例:

    % ./recipe.sh kou recipe-data1.txt piro recipe-data2.txt okkez recipe-data3.txt kou recipe-data4.txt -1 11
    ユーザー: 1: kou

    ユーザー: 2: piro

    ユーザー: 3: okkez

    ユーザー: 4: kou
    11: スイートポテト 蒸したさつまいもと砂糖とバターと生クリームをまぜて焼く

README.mdを読めば、グループの他の人でもIDを指定できるようにしてください。

### 仕様12: ライブラリーとして切り出すこと

ユーザー・レシピ管理部分をライブラリーとして切り出し、複数のプログラムから再利用できるようにしてください。これまでの挙動をするプログラムは、この切り出したライブラリーを使うようにしてください。挙動は変えないでください。

次の入出力部分はライブラリーではなく、プログラム側に入れてください。

  * このプログラムの利用者からユーザー名やレシピ情報などの入力を受け取る部分
  * データファイルを読み込む部分
  * 結果を出力する部分

プログラムをビルドする方法や実行方法が変わった場合はREADME.mdを更新してください。

#### 入力

仕様11と同じ。

#### 期待する結果

仕様11と同じ。

README.mdを読めば、グループの他の人もプログラムを実行できるようにしてください。

### 仕様13: 出力フォーマットがCSVの別のプログラムを作ること

ライブラリーを使用して結果をCSVで出力する別のプログラムを作ってください。

出力フィールドは左から順に次のとおりにしてください。

  * ユーザーID
  * ユーザー名
  * レシピID
  * レシピ名
  * レシピの説明

README.mdに実行方法を追記してください。

#### 入力

仕様11と同じ。

#### 期待する結果

プログラムを実行したらユーザー名と対応するレシピ情報を読み込んでください。その後、CSV形式でユーザー名と対応するレシピ情報を表示してください。

実行例:

    % ./recipe-csv.sh kou recipe-data1.txt piro recipe-data2.txt okkez recipe-data3.txt kou recipe-data4.txt
    1,kou,1,オムライス,卵を焼いてごはんにのせる
    1,kou,2,親子丼,鶏肉を焼いて卵でとじてごはんにのせる
    1,kou,3,杏仁豆腐,牛乳と砂糖をまぜてゼラチンで固める
    2,piro,4,オムライス,卵を焼いてごはんにのせる
    2,piro,5,鶏の唐揚げ,鶏肉にから揚げ粉をまぶして揚げる
    2,piro,6,カレー,野菜を切って煮込んでカレー粉を入れる
    3,okkez,7,トマトサラダ,トマトと野菜を切ってまぜる
    3,okkez,8,生ハムサラダ,生ハムと野菜を切ってまぜる
    3,okkez,9,和風サラダ,豆腐と野菜を切ってまぜて醤油ベースのドレッシングをかける
    4,kou,10,チョコケーキ,薄力粉とココアと卵とバターをまぜて焼く
    4,kou,11,スイートポテト,蒸したさつまいもと砂糖とバターと生クリームをまぜて焼く
    4,kou,12,杏仁豆腐,牛乳と砂糖をまぜてゼラチンで固める

README.mdを読めば、グループの他の人もプログラムを実行できるようにしてください。

### 仕様14: シークレット

メンターに仕様を聞いてください。