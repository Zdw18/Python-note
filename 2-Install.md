# Install

## 個人PCに簡単インストール場合

[公式サイト](https://www.python.org)からWindowsとmacOS用のPython installerをdownloadできます。downloadしたファイルを開き、画面の指示に従ってinstallしてください。

## Pythonランタイム環境を分離したい場合

そもそもなぜPythonランタイム環境分離必要でしょうか。以下の問題を解決したい場合Pythonランタイム環境分離することで簡単に解決できます。

* Project AはライブラリーXのバージョン1.xに依存するが、Project BはライブラリーXのバージョン2.xを必要とする、というジレンマを解消したい、依存ライブラリーが衝突してお互いに影響を与えるようなリスクを避けたい場合
* 開発者が複数のProjectを同時に対応する場合、Project使うpythonバージョンはそれぞれの場合
* 新しいパッケージを開発環境にのみ導入して検証を行う場合

仮想環境を作成及びパッケージの依存関係を管理するツールは主にvirtualenv、venv、buildoutが使われます。
また、異なるPython バージョンを管理し、切り替えるためのツールなら代表的なものはpyenvです。

個人PCで複数のProjectを開発する場合 [pyenv + venv]という案を紹介させて頂きたいです。
イメージとしては


