# Python: 条件分岐(if)、ループ(while, for)

## 条件分岐 if else

>Pythonの条件分岐もif,elseを使う

**基本的な構文:**

```
if 条件:
    # 条件が真の場合に実行されるコード
    # インデントでブロックを表現
    処理1
    処理2
    # ...
elif 別の条件:
    # 別の条件が真の場合に実行されるコード
    処理A
    処理B
    # ...
else:
    # どの条件も真ではない場合に実行されるコード
    処理X
    処理Y
    # ...
```

## ループ for while

>for ループはリスト、タプル、文字列などから要素を順番に取り出し、指定したブロック内の処理を繰り返し実行します。

```
>>> fruits = ['apple', 'banana', 'cherry']
>>> for e in fruits:
...     print(e)
... 
apple
banana
cherry

# break: ループを中断し、ループから抜け出します。
for i in range(10):
    if i == 5:
        break  # iが5のときループを抜ける
    print(i)

```

>while ループは、指定した条件が真の間、指定したブロック内の処理を繰り返し実行します。

```
count = 0
while count < 5:
    print(count)
    count += 1

# continue: ループの残りのコードをスキップし、次の反復に進みます。
for i in range(10):
    if i == 5:
        continue  # iが5のとき残りのコードをスキップして次の反復へ
    print(i)

```