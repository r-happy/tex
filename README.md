# rhappy code space for school

# pdfの出力
```
texfot latexmk -lualatex document.tex
```
makefileが使えたら`make build`でもいいです

# 書き方
## 画像

word のようにコピペができないので画像を毎回保存する必要があります  
画像は`public/img`の中に入れて`\Figure`で指定します  
参照するときは`\ref{fig:<ラベル名>}`を使います

```
\Figure{ページに対してどれぐらいの大きさで表示したいか}{読み込みたい画像ファイル名}{キャプション名}{ラベル名}
```

例
```
\Figure{0.5}{rhappy_icon.jpg}{ラッピーのアイコン}{rhappy_icon}
```

## ソースコード

ソースコードの扱い

### ファイルの一部（関数とか）

キャプションは`_`が使えないので`\_`でエスケープします  

```
\begin{lstlisting}[caption={キャプション名}, label={ラベル名}]
<コード>
\end{lstlisting}
```

例

```
\begin{lstlisting}[caption={print\_\_hello\_world関数のソースコード}, label={lst:print__hello_world_func}]
void print__hello_world(void) {
    // hello worldを出力
    printf("hello world\n");
}
\end{lstlisting}
```

### ファイルを読み込む
ソースファイルは`public/code`の中に入れて`\lstinputlisting`で指定します

```
\lstinputlisting[caption={キャプション名}, label={ラベル名}]{public/code/<ファイル名>}
```

例

```
\lstinputlisting[caption={main.cのソースコード}, label={lst:source_main}]{public/code/main.c}
```

### 文章内でmonoフォントを使う
`\Inline{}`で囲みます

例

```
sample text sample text \Inline{sample text} sample text
```

### monoフォントの設定
すきなmonoフォントを使いたい人は39,40行目を変更してください