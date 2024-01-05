# Python基本構文ーレベルアップ

## enumerate関数の利用
enumerate関数を使用すると簡単に要素のインデックスを取得できます。
>基本的な構文:
>enumerate(iterable, start=0)

```
例：
enumerate使用しない場合：
index = 0
for e in ["apple", "banana", "orange"]:
    print(index, e)
    index += 1
>>>
0 apple
1 banana
2 orange

enumerate使用する場合：
>>> for index, e in enumerate(["apple", "banana", "orange"]):
...     print(index, e)
... 
0 apple
1 banana
2 orange
```

## zip関数の利用
zip 関数は、複数の反復可能なオブジェクト（list或いはiterable）を受け取り、それらを組み合わせてタプルのシーケンスを作成する組み込み関数です。各list或いはiterableから同じインデックスの要素を取得して、新しいlist或いはiterable作成可能です。

>基本的な構文&例

```
zip(iterable1, iterable2, ...)

>>> fruits = ["apple", "banana", "orange"]
>>> prices = [20, 5, 10]
>>> for item in zip(fruits, prices):
...     print(item)
... 
('apple', 20)
('banana', 5)
('orange', 10)

```

## set（集合）
setは、Pythonの組み込みデータ型の一つで、重複のない要素を持つ無順序なコレクションです。

>setの特性

* 重複がない: 同じ要素を複数回追加しても、最終的な集合には1つの要素しか含まれません。
* 無順序: 要素の順序が保証されません。そのため、集合はインデックスやキーの概念がありません。
* 可変性: 集合は可変（mutable）なデータ型で、要素の追加や削除が可能です。
* イテラブル: for ループなどで集合の要素にアクセスできます。


```
# 空の集合を作成
my_set = set()
# 要素を追加
>>> my_set = set()
>>> my_set.add(1)
>>> my_set.add(2)
>>> my_set.add(3)
# 重複する要素は無視される
>>> my_set.add(2)
>>> my_set
{1, 2, 3}

# for ループ
>>> my_set = {1, 2, 3}
>>> for element in my_set:
...     print(element)
... 
1
2
3

#集合演算: 集合演算（和集合、積集合、差集合など）
set1 = {1, 2, 3}
set2 = {2, 3, 4}

union_set = set1 | set2  # 和集合
intersection_set = set1 & set2  # 積集合
difference_set = set1 - set2  # 差集合

print(union_set)        # {1, 2, 3, 4}
print(intersection_set) # {2, 3}
print(difference_set)   # {1}

```

## iterator
iter（イテレータ）は、Pythonの組み込み関数の一つで、イテレータオブジェクトを生成するために使用されます。
iter 関数は主に2つの方法で使用されます

>iterable オブジェクトの次の要素を順に取り出す

```
my_list = [1, 2, 3, 4, 5]
my_iterator = iter(my_list)

print(next(my_iterator))  # 1
print(next(my_iterator))  # 2

```

>呼び出し可能オブジェクトとセンチネル値からイテレータを生成:

```
def my_generator():
    yield 1
    yield 2
    yield 3

my_iterator = iter(my_generator, 2)

print(next(my_iterator))  # 1
print(next(my_iterator))  # StopIteration が発生する

```
