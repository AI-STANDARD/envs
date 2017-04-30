# 環境設定① Anacondaのインストールと､仮想環境の設定

環境設定のはじめの一歩は､Anacondaの導入です｡


## Anacondaとは？
![](http://cdn-ak.f.st-hatena.com/images/fotolife/t/tasukujp/20151114/20151114235558.png)

<font color="MediumSeaGreen">
**Anaconda**は､Continuum Analytics社 が提供している**Pythonディストリビューション（配布パッケージ）**です｡Pythonの環境設定をとっても簡単にしてくれます｡それによって､開発環境の整備ができたり､豊富にあるPythonライブラリのインストールやバージョン管理を一括でできたりします｡
</font>

## Pythonの仮想環境とその利点

![](https://www.fastpic.jp/images.php?file=5033142421.png)

Anacondaの一番の利点は､<font color='red'>**Pythonの仮想環境が作成できる**</font>ということです｡仮想環境というのは､**ひとつのPC（ハードウェア）の中に､何台ものPC（ソフトウェア）を複製できる**というものです｡通常､PythonはひとつのPCをにひとつしか入れることができませんが､これによって**ひとつのPCをの中に複数のPythonが共存できるようになります**｡

仮想環境の利点は以下のとおりです｡この先使い込んでいく中で重要になる機能もありますが､早めに導入しておくのが後々を考えても楽でしょう｡

### 1. ライブラリのバージョンを一括管理できる
![](https://www.fastpic.jp/images.php?file=6747309283.png)


**Pythonはライブラリが豊富にある言語です**｡しかし､<font color='red'>**ライブラリは開発元がそれぞれ異なるので､バージョンのアップデートなどは個別に行わなければならず､非常に手間がかかります**</font>｡  

そんなとき､Anacondaを利用すれば､<font color='red'>**Anacondaが統括するライブラリのアップデートを一括で行うことができます**</font>｡手間もかからないし､特別な知識も必要なくなるので非常に助かります｡

### 2. Pythonの複数バージョンを共存させられる
![](https://www.fastpic.jp/images.php?file=4620392459.png)

**Pythonには2系（Python2）と3系（Python3）の2つのバージョンがあります**｡現状では､おそらく殆どの場合で3系が利用されていますが､<font color='red'>**参考にしたい過去のコードが2系であるということはまだあります**</font｡  

しかし､<font color='red'>**2系と3系には互換性がなく､3系のコードを2系の環境で実行しようとするとエラーが起きてしまいます**</font>｡Python2の環境を作りたいところですが､基本的にPC一台にはPythonがひとつだけなので､こういった場合にはPythonを入れ直すか他のPCで2系のPythonを利用するかしかありません｡  

そんなとき､Anadondaをり利用すれば､<font color='red'>**2系のPythonと3系のPythonをひとつのPCをに共存させることができます**</font>｡さらにいえば､3系を入れるにしても､3.1や3.5などと細かいバージョンを指定することもできます｡

### 3. チーム開発の際に､複数人と環境を揃えることが出来る
![](https://www.fastpic.jp/images.php?file=1682847693.png)

**複数人で開発を行う際に､開発メンバーのPC内のPythonやライブラリのバージョン含む環境の違いが問題になります**｡たとえば､バージョンが違うと､古いメソッドが廃止されてしまって使えなかったり､新しいメソッドが最新版でないと導入されていなかったりします｡すると､ひとつのプロジェクトの開発メンバーたちの間で､<font color='red'>**｢同じ操作をしたのに､違うことが起こってしまう｣**</font>という状況になります｡これは非常に面倒です｡  

そんなときも､Anacondaを使えばこうした状況を防ぎ､<font color='red'>**チーム開発を円滑にすすめることが出来るようになります**</font>｡また､<font color='red'>**過去に開発されたPythonのプログラムを実行したり､再利用したいときにも､開発当時の環境を再現することができるので､非常に役に立ちます**</font>｡



## 仮想環境構築の手順



### 1.インストーラのダウンロード

![](https://www.fastpic.jp/images.php?file=1266852847.png)

[Anacondaの公式サイト](https://www.continuum.io/downloads)から､**インストーラ**をダウンロードします｡各自､<font color='red'>**自分の利用するPCに合ったインストーラを選択しましょう**</font>｡詳しくは以下を参照｡

#### **Windows**の場合
![](https://www.fastpic.jp/images.php?file=3170473244.png)

#### **MacOS**の場合
![](https://www.fastpic.jp/images.php?file=8863052412.png)

メールアドレスの入力を求められますが､**飛ばしてしまっても問題ないようになっています**｡ポップアップを閉じてしまって構いません｡

![](https://www.fastpic.jp/images.php?file=9434976065.png)




### 2. Anacondaのインストール
**ダウンロードした.exeファイルまたは､.pkgファイルを起動します**｡ここから先は､<font color='red'>**デフォルト設定のまま最後まで進んでしまって大丈夫です**</font>｡  

![](https://www.fastpic.jp/images.php?file=8515780869.png)



### 3.仮想環境の構築
インストールが完了したら､<font ccolor='red'>**仮想環境の構築**</font>に入ります｡**Windowsの場合はコマンドプロンプト､MacOSの場合はターミナルを起動してください（以下では､これらを**コマンドライン**といいます）**｡  

コマンドラインに､以下のコマンドをコピペしてください｡<font color='red'>**Pythonの仮想環境が構築されます**</font>｡

`conda create --name py35 python=3.5 anaconda`

コマンドの意味
- conda: anaconda(conda)の機能を利用します
- create: 新しくPythonの仮想環境を作成(create)します
- --name py35: 仮想環境の名前(name)はpy35です
- anaconda: anacondaに含まれる全てのライブラリを仮想環境にインストールします. 

ここから先は以下の実行画面のように処理が進みます｡

実行画面
![](https://www.fastpic.jp/images.php?file=7656663406.png)
![](https://www.fastpic.jp/images.php?file=3167911905.png)
![](https://www.fastpic.jp/images.php?file=2410187068.png)
![](https://www.fastpic.jp/images.php?file=1406070310.png)



### 4. 仮想環境の有効化/無効化

**作成した仮想環境を利用できるように有効化（activate）します**｡コマンドラインに以下のコマンドを打ち込みます｡<font color='red'>**WinとMacで若干コマンドが異なるので注意してください**</font>｡  

**Windowsの場合**
```activate py35```

**Macの場合**
```source activate py35```


また､<font color='red'>**仮想環境はターミナルを起動するたびにリセットされる**</font>ので､仮想環境を有効化させたい場合は､起動のたびにactivateが必要になります｡

また､仮想環境を切り替えたいときは**無効化**することもできます｡これをするときは､**activate**のところを**deactivate**にするだけです｡  

**Windowsの場合**
```deactivate py35```

**MacOSの場合**
```source deactivate py35```

![](https://www.fastpic.jp/images.php?file=1202924528.png)

### 5.Anacondaに含まれていないライブラリのインストール
Anacondaには非常に多くのライブラリが収録されていますが､<font color='red'>**収録されていないライブラリも一定数あります**</font>｡そこで､各ライブラリをインストールするためのコマンドを打ち込んでいきます｡これらをコマンドラインにコピペしていきましょう｡**pip(Python Installation Package)**を利用してインストールを行います｡  

<font color='red'>**※注意
必ず､Anacondaの仮想環境をactivateしてから行うように注意してください｡仮想環境ごとに違うPCのPythonのように扱われるので､ライブラリの導入は仮想環境ごとに設定する必要があります｡**</font>

chainer
`pip install chainer`

tensorflow
`pip install tensorflow`

OpenCV
`conda install -c menpo opencv3=3.2.0`

tqdm
`pip install tqdm`


![](https://www.fastpic.jp/images.php?file=0752043346.png)


## その他のAnacondaのコマンド
### conda info -e: 仮想環境について情報を確認
<font color='red'>**現在自分のPCをにある仮想環境を確認</font>したいときは､以下のコマンドを実行すればできます｡

```conda info -e```
あるいは
```conda info --envs```

実行画面
![](https://www.fastpic.jp/images.php?file=0631220293.png)

#### conda remove -n 仮想環境名 --all: 仮想環境の削除

**仮想環境の構築で設定ミスをしてしまったとき**､あるいは**構築した仮想環境が使われなくなったとき**は､以下のコマンドで<font color='red'>**仮想環境を削除**</font>できます｡

```
conda remove -n 仮想環境名 --all
```

実行画面
![](https://www.fastpic.jp/images.php?file=8611992752.png)

![](https://www.fastpic.jp/images.php?file=9883234919.png)