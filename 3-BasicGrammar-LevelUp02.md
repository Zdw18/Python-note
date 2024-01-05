# Python基本ーレベルアップ: リスト(list)、辞書(dict)

## Pythonのlist実際にリンクリストlinked listではありません
Pythonのlistは、通常の言語での「リスト」のようなデータ構造を表現するために使用されるもので、リンクリスト（linked list）ではありません。実際、Pythonのlistは動的な配列（dynamic array）または可変長配列（dynamic array）として実装されています。

>特徴としては：

* appendやpopなどが高効率に動作します
* リンクリストのように挿入や削除が頻繁に行われる場面では逆にコストが高くなっています。コレクションモジュールのcollections.dequeなどがリンクリストに近い性質を持つデータ構造を使った方が良い

## list内包表記
>list内包表記、多くの場合通常のループを使用するよりクリーンで高速になります。

例：

```
# 通常の方法
even_squares = []
for i in range(5):
    if i % 2 == 0:
        even_squares.append(i**2)

print(even_squares)
[0, 4, 16]

# 条件付きリスト内包表記
even_squares = [i**2 for i in range(5) if i % 2 == 0]
print(even_squares)
[0, 4, 16]
```

## list、色々操作

>list、色々操作: 要素の追加と削除

例：

```
append(): リストの末尾に要素を追加します。
insert(): 指定された位置に要素を挿入します。
remove(): 指定された値と一致する最初の要素を削除します。
pop(): 指定された位置の要素を削除し、その値を返します。

my_list = [1, 2, 3, 4, 5]

my_list.append(6)
# 結果: [1, 2, 3, 4, 5, 6]

my_list.insert(2, 10)
# 結果: [1, 2, 10, 3, 4, 5, 6]

my_list.remove(3)
# 結果: [1, 2, 10, 4, 5, 6]

popped_value = my_list.pop(2)
# 結果: [1, 2, 4, 5, 6], popped_value = 10
```

>list、色々操作: スライシング

例：

```
my_list = [1, 2, 3, 4, 5]

subset = my_list[1:4]
# 結果: [2, 3, 4]

subset2 = my_list[:3]
# 結果: [1, 2, 3]

subset3 = my_list[2:]
# 結果: [3, 4, 5]
```

>list、色々操作: リストの結合

例：

```
他のリストとの結合は + 演算子を使用します。
list1 = [1, 2, 3]
list2 = [4, 5, 6]

combined_list = list1 + list2
# 結果: [1, 2, 3, 4, 5, 6]
```

>list、色々操作: リストの拡張

例：

```
extend() メソッドを使用して、別のリストの要素をリストに追加できます。
list1 = [1, 2, 3]
list2 = [4, 5, 6]

list1.extend(list2)
# 結果: [1, 2, 3, 4, 5, 6]
```

>list、色々操作: 要素の検索

例：

```
index() メソッドを使用して指定された値のインデックスを検索できます。
my_list = [10, 20, 30, 40, 50]

index = my_list.index(30)
# 結果: index = 2
```

>list、色々操作: リストのコピー

==注意:==<span style="color: red; ">copy()</span>と<span style="color: red; ">スライス[:]</span>は 新しいリストを生成します。

```
>>> original_list = [1, 2, 3, 4, 5]
>>> original_list
[1, 2, 3, 4, 5]
>>> id(original_list)
4542944192
>>> copied_list = original_list.copy()
>>> copied_list
[1, 2, 3, 4, 5]
>>> id(copied_list)
4542942592
>>> copied_list_2 = original_list[:]
>>> copied_list_2
[1, 2, 3, 4, 5]
>>> id(copied_list_2)
4542949440
>>> list2 = original_list
>>> list2
[1, 2, 3, 4, 5]
>>> id(list2)
4542944192
>>> original_list[0] = 10
>>> original_list
[10, 2, 3, 4, 5]
>>> list2
[10, 2, 3, 4, 5]
>>> copied_list
[1, 2, 3, 4, 5]
>>> copied_list_2
[1, 2, 3, 4, 5]
```

## 辞書内包表記

***Python 3.7以降、辞書（dict）は要素が挿入された順序を保持するようになりました。これはPython 3.6以前では標準では保証されていませんでした。***

>辞書を使う時の注意点

* モリ消費:辞書はハッシュテーブルを使用しているため、メモリ効率が悪いことがあります。キーと値の対応関係を保持するために追加のメモリが必要であり、特に==大規模なデータセット==の場合にメモリの使用量が問題になることがあります。
* イミュータブルなキーの制約:辞書のキーはイミュータブルでなければなりません。つまり、リストや辞書などの変更可能なデータ型はキーとして使えません。

>辞書内包表記にはリスト内包表記と同じメリットがあります。多くの場面で、よりクリーン・効率的。

例：

```
# 通常の方法
squares_dict = {}
for i in range(5):
    squares_dict[i] = i**2
>>>{0: 0, 1: 1, 2: 4, 3: 9, 4: 16}

# 辞書内包表記
squares_dict = {i: i**2 for i in range(5)}
>>>{0: 0, 1: 1, 2: 4, 3: 9, 4: 16}
```

## 辞書の操作

>要素の追加と更新

```
my_dict = {'name': 'John', 'age': 30}

my_dict['city'] = 'New York'
# 結果: {'name': 'John', 'age': 30, 'city': 'New York'}

my_dict['age'] = 31
# 結果: {'name': 'John', 'age': 31, 'city': 'New York'}

```

>要素の削除:

```
my_dict = {'name': 'John', 'age': 30, 'city': 'New York'}

del my_dict['age']
# 結果: {'name': 'John', 'city': 'New York'}

```

>キーの存在チェック
>in キーワードを使用して、指定したキーが辞書に存在するかどうかを確認できます。

```
my_dict = {'name': 'John', 'age': 30}

if 'city' in my_dict:
    print("City exists:", my_dict['city'])
else:
    print("City does not exist")

```

>辞書のキーと値の取得:
>keys(): すべてのキーを取得します
>values(): すべての値を取得します
>items(): すべてのキーと値のペアを取得します

```
my_dict = {'name': 'John', 'age': 30, 'city': 'New York'}

keys = my_dict.keys()
# 結果: dict_keys(['name', 'age', 'city'])

values = my_dict.values()
# 結果: dict_values(['John', 30, 'New York'])

items = my_dict.items()
# 結果: dict_items([('name', 'John'), ('age', 30), ('city', 'New York')])

```

>辞書のコピー:

==注意:==<span style="color: red; ">copy()</span>と<span style="color: red; ">dict() コンストラクタ</span>は 新しいリストを生成します。

```
>>> original_dict = {'name': 'John', 'age': 30, 'city': 'New York'}
>>> original_dict
{'name': 'John', 'age': 30, 'city': 'New York'}
>>> id(original_dict)
4330327744
>>> copied_dict = original_dict.copy()
>>> copied_dict
{'name': 'John', 'age': 30, 'city': 'New York'}
>>> id(copied_dict)
4330427840
>>> copied_dict_2 = dict(original_dict)
>>> copied_dict_2
{'name': 'John', 'age': 30, 'city': 'New York'}
>>> id(copied_dict_2)
4332749184
>>> original_dict['age'] = 31
>>> original_dict
{'name': 'John', 'age': 31, 'city': 'New York'}
>>> copied_dict
{'name': 'John', 'age': 30, 'city': 'New York'}
>>> copied_dict_2
{'name': 'John', 'age': 30, 'city': 'New York'}
>>> 
```