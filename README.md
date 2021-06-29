# Kakenhi report LaTeX template (C-19, F-19-1, Z-19)

科研費の成果報告書(C-19, F-19-1, Z-19)のLaTeXテンプレートを作ってみました。[科研費LaTeX](http://osksn2.hep.sci.osaka-u.ac.jp/~taku/kakenhiLaTeX/)が使えるので、申請時にはLaTeXで申請書を書き、成果報告書のベースになる原稿もLaTeXで書くので、成果報告書もLaTeXで書けたら便利かと思いました。しかし、探してみても見つからないので、作ってみました。

## 簡単な説明
### フォント
Word版と同じ見た目にするために、フォントはMS明朝を使用します。
msmincho.ttc というファイルをLaTeXから見える位置(例えば、ソースのディレクトリ)に置いてください。
MSゴシックのフォントファイル(msgothic.ttc)が無いとコンパイル時に怒られるようなのですが、使っていなかったら実害は無いみたいです。

### 参考文献
なんとなく、参考文献にはBibLaTeXを使っています。
そのため、コンパイル時は
```
# pdfuplatex report.tex
# biber report
# pdfuplatex report.tex
# pdfuplatex report.tex
```
の要領でコンパイルしてください。
その影響(？)で、bibファイル中の日本語の参考文献には
```
  langid = {Japanese},
```
を入れないと、最終著者の前にandが入ります。

まあ、BibTeXに変更してもらっても良いと思います。

### 縦横の文字数を数えるためのテストパターン
多分使わなくても良いと思いますが、Word版と文字数、行数を比較するときには、dummy.texを読み込んでください。
```
\input{dummy.tex}
```
の要領です。
