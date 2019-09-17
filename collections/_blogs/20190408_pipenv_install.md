---
layout: blog
title: pipenv導入
date_post: 20190408
tags: tech
hidden: true
---

# pipenv導入

## Install

公式の導入ページ
* https://github.com/pypa/pipenv
* https://pipenv-ja.readthedocs.io/ja/translate-ja/index.html

他参考になったページ

* 初心者向け・Pythonの仮想環境venvとPipenvによるパッケージ

https://paiza.hatenablog.com/entry/2018/07/05/初心者向け・Pythonの仮想環境venvとPipenvによるパッケージ

* pipenvでDjangoアプリをherokuにでデプロイしたので手順をメモ

https://qiita.com/miler0528/items/1926e93ed97979f8e9fa


```
$ brew install pipenv
```

## Setup
```
$ cd ./gmail_push
$ pipenv --python 3.6.1 
```
or 
```
$ pipenv install --python 3.6.1
```
しかしこれだとエラーを吐いた。
```console
$ pipenv --python 3.6.1
Warning: the environment variable LANG is not set!
We recommend setting this in ~/.profile (or equivalent) for proper expected behavior.
Traceback (most recent call last):
  File "/usr/local/Cellar/pipenv/2018.11.26_2/libexec/lib/python3.7/site-packages/pipenv/vendor/pythonfinder/models/python.py", line 112, in get_versions
    version = PythonVersion.parse(p.name)
  File "/usr/local/Cellar/pipenv/2018.11.26_2/libexec/lib/python3.7/site-packages/pipenv/vendor/pythonfinder/models/python.py", line 359, in parse
    version_dict = parse_python_version(str(version))
  File "/usr/local/Cellar/pipenv/2018.11.26_2/libexec/lib/python3.7/site-packages/pipenv/vendor/pythonfinder/utils.py", line 86, in parse_python_version
    raise InvalidPythonVersion("%s is not a python version" % version_str)
pipenv.vendor.pythonfinder.exceptions.InvalidPythonVersion: .DS_Store is not a python version
(以下略)
```
.DS_Storeが邪魔と書いてあるけど、どこの.DS_Storeなのか。。。。
公式のissueに次の様に上がっていた。

> I removed the `~/.pyenv/versions/.DS_Store` as indicated above as a possible solution.
I then re-executed pipenv install --dev lettuce and happily observed
* https://github.com/pypa/pipenv/issues/3208
* https://github.com/pypa/pipenv/issues/3208#issuecomment-449778005

と書いてあり、pyenvがバージョンを探しに行くフォルダにいつの間にか、.DS_Storeファイルができていてそれが原因だった。


## Installing Python Package
```
pipenv install gunicorn==19.9.0 flask==1.0.2
```
こんな感じでパッケージをインストールできる。

## Work
```
pipenv shell
```
で仮想環境の中に入る。

## pycharmへの追加
https://qiita.com/nomunomu0504/items/a674a3d8cafd617f5319

を参考にしながらproject〜interpreterをpyenvのpython実行命令にしたり、python consoleのインタープリタをそれに合わせたりした。


これだとpycharmでエラーが出たり。ipythonのバージョンの問題だった。
https://intellij-support.jetbrains.com/hc/en-us/community/posts/115000686170-Python-Console-crashes-on-startup-in-PyCharm



* Todo: これ見ながら描き方見直す
https://www.kabuku.co.jp/developers/python-pipenv-graph


## トラブルシューティング
### python3がつかえない
上記プロセスをubuntuで実施したところ、python3のinstallができないかった。
調べたら以下のissueで既出の問題であった

* [Broken with Python 3 and Ubuntu 18.04](https://github.com/pypa/pipenv/issues/2922)

これに書いてある通り、'python3-distutils'を導入した。
'''
$sudo apt-get install python3-distutils
'''
ただし、この時に
> [dpkg: error: dpkg frontend is locked by another process]
というエラーがでたので対応が必要だった。次のサイトを参考に対応した。

* [リンク](https://bistro.site/?p=1403)