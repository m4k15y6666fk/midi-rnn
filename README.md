
# MIDI RNN

## 概要

RNN を利用した MIDI 生成プログラム。IJulia Notebook (.qmd : Quarto 形式) によりコードを実行する。

MIDI generator with RNN. Execute with IJulia Notebook (.qmd : Quarto Format)

## インストール

### macOS

#### 1. 事前準備

* Python 3.12.x
* Julia 1.6.x

##### Homebrew

事前に Homebrew (`brew` コマンド) をインストールする。

##### Miniconda / venv

ローカル環境に Python をインストールし、conda または venv を使用できるようにする。

conda または venv で Python の仮想環境を構築する：

```bash
conda create --name [jupyter 環境の名前] python=3.12
```

#### 2. Jupyter Lab 

```bash
conda activate [jupyter 環境の名前]
```

```bash
pip install jupyter jupyterlab
```

#### 3. Julia 1.6 の実行環境

##### juliaup コマンドのインストール

```bash
brew install juliaup
```

または、その他の方法で juliaup コマンドを使用可能する。

##### Julia 1.6 のインストール

```bash
juliaup add 1.6
```

#### 4. IJulia パッケージの導入

```bash
# version が 1.6.x であることを確認
julia
```

```bash
julia> ]
(@v1.6) pkg> add IJulia
```

##### 【おまけ】 Julia 1.6 のノートブックが作成できないとき

過去に同じ Python 環境で別バージョンの IJulia をインストールしたことがある場合、以降の手順で Jupyter Lab を起動しても、Julia 1.6 のノートブックが作成できないことがある。

その場合、

```bash
# version が 1.6.x であることを確認
julia
```

```bash
julia> using IJulia
julia> installkernel("Julia")
```

を実行することで、Jupyter Lab でのファイル作成時に Julia 1.6 のノートブックが選択できるようになる。

### 5. その他必要なパッケージの導入

MIDI RNN の Notebook を実行するために必要なパッケージは以下：

* Flux
* MIDI
* MusicManipulations
* JLD2
* Distributions
* Plots (optional)

```bash
julia> ]
(@v1.6) pkg> add Flux MIDI MusicManipulations JLD2 Distributions Plots
```

### 6. GitHub リポジトリのクローン

```bash
cd [作業ディレクトリ]
git clone "https://github.com/m4k15y6666fk/midi-rnn.git"

cd midi-rnn
```

以上で環境構築は完了。

### 7. Jupyter Lab の起動

```bash
jupyter lab --notebook-dir=.
```
