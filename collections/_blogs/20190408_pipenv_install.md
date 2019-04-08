---
layout: default
title: Pipenv導入
date_post: 20190408
tags: tech
---

# Pipenv導入

## Install

公式の導入ページ
* https://github.com/pypa/pipenv
* https://pipenv-ja.readthedocs.io/ja/translate-ja/index.html

他参考になったページ

* https://paiza.hatenablog.com/entry/2018/07/05/%E5%88%9D%E5%BF%83%E8%80%85%E5%90%91%E3%81%91%E3%83%BBPython%E3%81%AE%E4%BB%AE%E6%83%B3%E7%92%B0%E5%A2%83venv%E3%81%A8Pipenv%E3%81%AB%E3%82%88%E3%82%8B%E3%83%91%E3%83%83%E3%82%B1%E3%83%BC%E3%82%B8
* https://qiita.com/miler0528/items/1926e93ed97979f8e9fa


```
$ brew install pipenv
```

## Setup
```
$ cd ./gmail_push
$ pipenv --python 3.6.1
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
