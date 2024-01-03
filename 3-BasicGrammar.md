# 基本文法
## コメント
Pythonでは、# 記号を使用してコメントを追加します。

```
# これは一行コメントです

"""
これは複数行コメントです
三重引用符で囲むことができます
"""
```

## 変数
Pythonでは、変数に直接値を代入できます。変数の型は指定する必要がない、自動的に決定されます。

```
x = 1          # 整数
y = 1.18        # 浮動小数点数
name = "Zdw"   # 文字列
```

## データ型
よく使われるデータ型には整数（int）、浮動小数点数（float）、文字列（str）、ブール値（bool）などがあります。

```
num = 13        # 整数
pi = 3.14       # 浮動小数点数
text = "Hello Python!"  # 文字列
is_true = True   # ブール値
```

### 整数： 整数を２進法、８進法、16進法で記述

進法 | 表記（プレフィックスをつける） | 例 10進法の整数10
----|----|----|
2進法 | 0b/0B | 0b1010
8進法 | 0o/0O | 0o12
16進法 | 0x/0X | 0xa

```
>>> a = 10
>>> print(bin(a))
0b1010
>>> print(oct(a))
0o12
>>> print(hex(a))
0xa
>>> 
```

> ２進法、８進法、16進法を使用する場面は主に以下のようなケースが考えられます。

```
①ビット演算: 2進法は、ビット演算やビットマスク操作に役立ちます
FLAG_A = 0b0001
FLAG_B = 0b0010
FLAGS = FLAG_A | FLAG_B  # フラグの組み合わせ

bitmask = 0b11001100
result = data & bitmask  # 2進法のビット演算

②ファイルのパーミッション： Unix系のオペレーティングシステムでは、8進法がファイルのパーミッション（権限）を表すのに使われます。例えば、0o755は所有者が読み書き実行可能、他のユーザーは読み実行可能というパーミッションです。
file_permissions = 0o755

③16進法： 16進法は、メモリアドレス、色の表現（RGB値など）などでよく使用されます。
memory_address = 0x7fff2a8b2a10
color = 0xFF3366  # 16進法のRGB表現
```

## 文字列操作
Pythonには文字列を操作するための多くのメソッドがあります。結合、スライスなどがあります。

```
greeting = "Hello"
name = "Zdw"
message = greeting + ", " + name + "!"  # 文字列の結合
substring = message[0:5]                # スライスの操作
```

## リスト
リストは順序付けられたコレクションで、異なる型の要素を含むことができます。

```
my_list = [1, 2, 3, "apple", True]

```

## 条件文、ループ文：
if、elif、else を使用して条件分岐を行います。

```
x = 10

if x > 0:
    print("xは正の数です")
elif x < 0:
    print("xは負の数です")
else:
    print("xはゼロです")
```
for および while を使用してループ操作を行います。

```
for i in range(5):
    print(i)

while x > 0:
    print(x)
    x -= 1

```

## 関数
関数を定義するには def を使用します。

```
def sum(a, b):
    return a + b

result = sum(3, 5)

```

## ラスとオブジェクト
Pythonはオブジェクト指向の言語であり、クラスを使用してオブジェクトを作成できます。

```
class Dog:
    def __init__(self, name):
        self.name = name

    def bark(self):
        print("ワンワン！")

my_dog = Dog("Buddy")
my_dog.bark()

```