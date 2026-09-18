# Piye Liu - Master Thesis
* **Thesis:** [hal-lab-u-tokyo/liu_master_thesis](https://github.com/hal-lab-u-tokyo/liu_master_thesis)
    * Thesis is in master/
    * Defense slides are in master/defense
* **Contribution 1 Code and Data** can be found at [hal-lab-u-tokyo/SWoPP2026_ARC](https://github.com/hal-lab-u-tokyo/SWoPP2026_ARC)
* **Contribution 2 Code and Data** (including models) can be found at [hal-lab-u-tokyo/readings](https://github.com/hal-lab-u-tokyo/readings)

## To-do list

From [here](https://github.com/hal-lab-u-tokyo/Portal/wiki/%E4%BF%AE%E4%BA%86%E3%83%BB%E5%8D%92%E6%A5%AD%E6%99%82%E3%81%AE%E3%81%84%E3%82%8D%E3%81%84%E3%82%8D):
* [x] 部屋と机周りの後片付け
* [x] 学位論文をはじめとした研究データの共有・整理（進学者も要対応）
    * [x] Upload data to GDrive (see [here](https://drive.google.com/drive/folders/1R3vO8agHL1Wg3NEr7W6a9Xg-Q-dDjWls))
    * [x] Clear `.huggingface` `.cache` etc
* [x] ECCSアカウント失効に向けた準備（特に修了者）
    * [x] Google Takeout
    * [x] Archive files owned by me from shared drive
* [x] 研究室Google Drive, Slack, GitHubの整理
    * [x] Google Drive
    * [x] Slack
    * [x] GitHub (also fork/backup repos)
* [x] 今後のメールアドレス連絡先の共有

# TeX執筆tips

## 執筆(論文，予稿)
### 1．全般的な注意点
- [ ] 用語・語句が論文全体を通して統一されていることを確認．
- [ ] 変数の重複がないかを確認する．
- [ ] 長い文を避ける.
- [ ] 冗長な文章でないか確認する.
- [ ] 「もの」などのような抽象的な表現は使用しない.
- [ ] ニュアンスの違う似たような表現は誤解を招くので、どちらかを消すか表現を変える. 
- [ ] 文献や図表の引用ミス `?` は早めに潰すこと．いまその状態なら，提出版でもやらかします．
- [ ] 梗概は背景と課題を書きすぎないように注意．多くても2.5割くらい．
    - [ ] 背景と課題で2割
    - [ ] 提案手法の概要で4-4.5割
    - [ ] 評価と結果で2-2.5割
    - [ ] 本研究の成果と貢献・今後の展望で1-1.5割． 

### 論文を通して統一すべきもの
- [ ] 用語・語句
- [ ] 文章とTeXの細かい体裁
    - [ ] 括弧，句読点のコンマピリオドは基本は全角
    - [ ] 複数のモノを並べる場合，「AとB」「A，BとC」じゃなく「AおよびB」「A，BおよびC」と書く．
    - [ ] 二重引用符の始めは `` （バッククオート２つ）終わりは '' （シングルクオート２つ）
    - [ ] 文末で文献引用の番号を入れる場合は \cite{} の位置に注意．ピリオドの前に入れる．（「〜〜であることが知られている\cite{uso}．」）
    - [ ] `\caption` は１行に収まるように．端的であるべきで，長くなる説明は文中ですればよい．２行にまたがるとTeX的にいろいろ崩れるはず．
    - [ ] `\begin{figure}` `\begin{table}` 等の前後には空行を入れる
    - [ ] 本文中でコードや変数を書くときは `\texttt{}` にするとよい．ファイル名もこれを使うほうがよい．
- [ ] 図の形式
    - [ ] フォント
        - [ ] テキストの時はArial
        - [ ] 単位とかはTimesNewroman
    - [ ] フォントサイズ
    - [ ] 枠線の太さと色（黒推奨）
    - [ ] グラフの線の太さと色（黒推奨）
    - [ ] 図の倍率
    - [ ] 図はベクター化する（pdfやepsでPowerPoint図を保存してTeXで取り込む）
    - [ ] 図や表は本文で必ず参照して説明をする．
    - [ ] 理想は本文中の参照\refとその説明文と，その図が同じページに掲載するようにすべき．TeXの限界もあるので無理なら図が前後ページ（後のほうが良い）に来ても良い．2ページ離れるとか章を跨るとかは避ける．
- [ ] 参考文献の形式
    - [ ] bibtex
- [ ] 図・表・定理などの引用
    - [ ] \cref
		
### 発表 
- 事前にフォント種、強調色、フォントサイズ、強調時フォントサイズ、引用時フォントサイズなどルールを細かく決めておく. 
- 引用文献を明記すること.
    - ​et al.​， と表記する (+とする表記もある).
    - [文献番号]として最後に参考文献リストをまとめるでも良い
- 発表対象が誰かを明確にしておく.例えば，レビュータイプのプレゼン資料は，「わからせる」ことよりも「わかった気にさせる」ことの方が重要. 

					
---	
## TeXのテクニック
### 全般的な注意点
- 数字と単位の間、括弧の前、「:」の後、には半角スペース、改行防止の~を入力 (例:10 回，図 (a)など)	
- 「、」「。」ではなく「，」「.」(全角)		
- サブキャプションに文章は書かずにメインのキャプションにまとめて書く
    - キャプションにもピリオドをつけること
- ローマ字の斜体，立体を使い分ける.斜体は一文字ずつ変数を示し，変数ではない場合は 立体を使用.	
    - 変数の下つき上つき文字などで，意味的にTextのものを入れるときは`\text{}`をつけ立体に
        - 例：　$w_{\text{global}}$
    - 逆にただのインデックスであれば斜体
        - 例：　$w_i$

### 1. ファイル構成について
分割コンパイル構成を推奨します．
```
style/
  | - style.sty
text/
  | - abstract.tex
  | - chapterHoge.tex
figure/
  | - figure1...
main.tex
huga.cls（テンプレートファイル）
reference.bib
```


### 2. 引用について
基本的にはbibtex機能を使って，.bibファイルに書誌情報を記載する．（以下を参照）．  
https://qiita.com/SUZUKI_Masaya/items/14f9727845e020f8e7e9  
なんやかんやbibtexバグって使いにくいこともあるので，.bib で文献情報をまとめて，bibtex で .bbl に変換してやって，関連研究とか参考文献の必要な文章を書ききったら，その .bbl をまるごと .tex の本体に貼り付けちゃってから編集するとよい． .bbl を直接編集するとなんかのきっかけで変換上書きされちゃうのでご注意を．

### 3. 図，表，定理などの引用

cleverefを使うのがクレバーです．  
https://qiita.com/wktkshn/items/110cd6007837938e6c88


---

### Figure環境

- `\begin{figure}[t!]` が基本
- `\caption` は図の下部に入れる

#### subfigureを利用する場合
- `\caption`内でsubfigureのラベルを引用する場合は`\protect{}`を使う

```latex
\ifCLASSOPTIONcompsoc
\usepackage[caption=false, font=normalsize, labelfont=sf, textfont=sf]{subfig}
\else
\usepackage[caption=false, font=footnotesize]{subfig}

\begin{figure}[t!]
    \centering
        \subfloat[]{
            \centering
            \includegraphics[width=0.94\columnwidth]{hoge.pdf}
            \label{fig:subfig1}
        }\\
        \subfloat[]{
            \centering
            \includegraphics[width=0.94\columnwidth]{fuga.pdf}
            \label{fig:subfig2} % subfigureのラベル
        }
    \caption
    {
        図全体の説明 
        \protect\subref{fig:subfig1}~subfigure1のタイトルとその説明.
        \protect\subref{fig:subfig2}~subfigure1のタイトルとその説明.
    }
    \label{fig:mainfig}
\end{figure}
```
#### minipage環境

### Table環境

- `\begin{table}[b!]` が基本
- `\caption` は表の上部に入れる
- \begin{tabular}{ここは`c`，`l`，`r`，`p`などで　幅や位置揃えなどを指定できる}
```latex
\begin{table}[b!]
    \centering
    \caption{表の名前．}
    \label{table:t1}
    \begin{tabular}{cccc}% \begin{tabular}{ここは`c`，`l`，`r`，`p`などで　幅や位置揃えなどを指定できる}
    \hline \\
    &&& \\
    \hline
    \end{tabular}
\end{table}
```

## 修論・卒論の「指導教員」について

- 修論は（名簿上の）指導教員のみ
  - 和文： `\supervisor{中村 宏　 教授}` または `\supervisor{高瀬 英希 准教授}`
  - 英文： `\supervisor{Prof. Hiroshi Nakamura}` または `\supervisor{Assoc. Prof. Hideki Takase}`
- 卒論は `\supervisor{中村 宏　 教授 \and 高瀬 英希 准教授}` または `\supervisor{Prof. Hiroshi Nakamura \and Assoc. Prof. Hideki Takase}`
