# 形式ばらない色々

## Version 

* Python2.X

> 2020.01.01  サポート終了

* Python3.X

>2008.12.03 Python3.0リリース。現在主要となるバージョンはPython3です

## インタプリタ

* **CPython**  
CPythonは、Pythonの公式実装であり、最も広く使用されているインタープリタの一つです。Python のコードを直接実行するのではなく、C言語で書かれたインタープリタを使用して実行します。この特性により、CPythonは高速な実行速度を持っています。

* **Jython**  
Jythonは、JavaによるPython 実装です。PythonコードをJavaのバイトコードにコンバイルしたり、Python モジュールの中からJavaのクラスをシームレスに使用できます

* **IronPython**  
IronPython は、.NET Framework/Mono/.NET Core 上で動作するPython の実装である。

* **PyPy**  
PyPyはPython をPython で書き直すということを目標にしている実装である。JITコンパイラを内蔵しています。CPythonよりも高速にPythonのコードを実行できる場合が多いです。

*なぜCPython以外の実装は色々存在していますか。理由としてはCPython では解決ができなかったり、解決できたとしても相当なコストをつぎ込まなければならないものです。*

## 環境変数

環境変数はPython の挙動に影響します。以下の環境変数をしておいた方が良いではないかと思います：

* **PYTHONHOME**

標準Pythonライブラリの場所を変更します。Python をインストールしたディレクトリと標準ライブラリの場所として理解してもいいかなと思います。

* **PYTHONPATH**

モジュールの検索パス。

* **PYTHONSTARTUP**

PYTHONSTARTUPでpythonインタプリタ起動時の決まった処理の追加ができます。

## IDE

* **PyCharm**  
JetBrainsによって開発された、Python 専用の統合IDEです。

 	* 有償
 	* コードの補完
 	* 検査
 	* リアルタイムでエラー指摘と修正
 	* 自動コードリファクタリング
 	* デバッグ、テスト、バージョン管理など網羅している　　

* **Visual Studio Code**  
 マイクロソフトによって開発されたオープンソースのコードエディタです。
 
	 * 無料
	 * Python を含む多くのプログラム言語に対応しており、拡張機能のライブラリも非常に豊富です。
	 
* **Vim**   
viから派生し、発展した高機能なテキストエディタです。
~/.vimrcファイルで詳細設定を設定する上でカスタマイズ化できます。

*自分は昔Vim派ですが最近Visual Studio Code使っています。*
 
 

## 役にたつリソース

* [Pythonドキュメント ](https://docs.python.org/3/)
* [PyPI Python パッケージインデックス](https://pypi.org)
* [Pythonのコーディング規約](https://peps.python.org/pep-0008/)





