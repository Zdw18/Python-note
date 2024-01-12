# Python: file

## Pythonファイル読み込む

### ⚫︎read メソッド
>ファイルの内容を読み出すには、 f.read(size) を呼び出します。このメソッドはある量のデータを読み出して、文字列 (テキストモードの場合) か bytes オブジェクト (バイナリーモードの場合) として返します。size が省略されたり負の数であった場合、ファイルの内容全てを読み出して返します。ファイルの終端にすでに達していた場合、 f.read() は空の文字列 ('') を返します。

#### ◾️f はfile object です、file object はopen()で獲得できる。

```
open(filename, mode, encoding=None)
2つの位置引数と1つのキーワード引数を伴って呼び出されます。
```
* 最初の引数はファイル名の入った文字列です
`ファイル存在しない場合、「 No such file or directory」エラー発生`

* 二つめの引数も文字列で、ファイルをどのように使うかを示す数個の文字が入っています。

mode | 意味 
-------- | --------|
'r' | 読み込み用に開く (デフォルト) |
'w' | 書き込み用に開き、まずファイルを切り詰める |
'x' | 排他的な生成に開き、ファイルが存在する場合は失敗する |
'a' | 書き込み用に開き、ファイルが存在する場合には末尾に追記する |
'b' | バイナリモード |
't' | テキストモード (デフォルト) |
'+' | 更新用に開く (読み込み・書き込み用) |

==**デフォルトのモードは 'r' (テキストの読み込み用に開く、 'rt' と同義) です**==

* encoding 

	encodingはファイルのエンコードやデコードに使われる text encoding の名前です。このオプションはテキストモードでのみ使用してください。デフォルトエンコーディングはプラットフォーム依存 (locale.getencoding() が返すもの) ですが、Pythonでサポートされているエンコーディングはどれでも使えます。
	
### read メソッドのsample
##### open()、close()
```
f = open("test.txt", 'r')
data = f.read()
f.closed
# 注意：この方法は、ファイルを閉じ、利用されたシステムのリソースを直ちに解放するために f.close() を呼び出してください。
```

#### with キーワードを使う
==**ファイルオブジェクトを扱うときに with キーワードを使うのは良い習慣です。**==

```
# ファイルを開く
with open('test.txt', 'r') as f:
    # ファイルの内容をリストとして読み込む（1行が1要素）
    data = f.read()

# We can check that the file has been automatically closed.
>>> f.closed
True
```

### ⚫︎readline メソッド
#### f.readline() はファイルから 1 行だけを読み取ります。改行文字 (\n) は読み出された文字列の終端に残ります。
```
➜  ~ cat text.txt 
This is the first line of the file.
Second line of the fil.e
third line of the file.

>>> with open("text.txt") as f:
...     f.readline()
... 
'This is the first line of the file.\n'
```

### ⚫︎readlines メソッド
#### f.readlines() はファイルのすべての行をリスト形式で読み取ります。

```
➜  ~ cat text.txt 
This is the first line of the file.
Second line of the fil.e
third line of the file.

>>> with open("text.txt") as f:
...     f.readlines()
... 
['This is the first line of the file.\n', 'Second line of the fil.e\n', 'third line of the file.\n', '\n']
```

## Pythonファイルに書き込み
>f.write(string) は、string の内容をファイルに書き込み、書き込まれた文字数を返します。

```
>>> with open("sample.txt", "w") as f:
...     f.write("Hello!\n")
... 
7
➜  ~ cat sample.txt 
Hello!
```

>ファイルに追記する

```
◾️f.write()
with open("sample.txt", "a") as f:
...     f.write("Hello! Mr.Tom.\n")
... 
15
➜  ~ cat sample.txt
Hello!
Hello! Mr.Tom.

◾️f.writelines()
# writelines メソッドは自動的には最後に改行を書き込みませんので、必要であれば要素に格納する文字列に '\n' を加えてください。
>>> with open("sample.txt", "a") as f:
...     f.writelines(lines)
... 
➜  ~ cat sample.txt
Hello!
Hello! Mr.Tom.
hi
how are you
```

>ファイルある行に挿入

**f.seek(offset, whence)で位置を移動して書き込む**

>参照点は whence 引数で選びます。whence の値が 0 ならばファイルの 先頭から測り、1 ならば現在のファイル位置を使い、2 ならばファイルの終端を参照点として使います。whence は省略することができ、デフォルトの値は 0、すなわち参照点としてファイルの先頭を使います。

***テキストファイル (mode 文字列に b を付けなかった場合) では、ファイルの先頭からの相対位置に対するシークだけが許可されています (例外として、seek(0, 2) でファイルの末尾へのシークは可能です)。***

```
➜  ~ cat sample.txt 
abcdefg
1234567
あいうえお

>>> with open("sample.txt", "r+") as f:
...     f.seek(3)
...     f.write("X")
... 
3
1
➜  ~ cat sample.txt
abcXefg
1234567
あいうえお

>>> with open("sample.txt", "r+") as f:
...     f.seek(10)
...     f.write("X")
... 
10
1
➜  ~ cat sample.txt
abcXefg
12X4567
あいうえお


```


## Pythonファイル存在確認
Pythonでファイルの存在を確認するためには、os モジュールを使用します。

```
>>> import os
>>> file_path = "./sample.txt"
>>> if os.path.exists(file_path):
...     print(f'The file "{file_path}" exists.')
... else:
...     print(f'The file "{file_path}" does not exist.')
... 
The file "./sample.txt" exists.
```


