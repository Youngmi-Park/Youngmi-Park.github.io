---
title:  "[Error] ModuleNotFoundError: No module named 'tensorflow.contrib' 오류 해결"
excerpt: "tensorflow 실행과정에서 발생한 오류 해결"
strapline: "tensorflow 실행과정에서 발생한 오류 해결"
toc: true
comments: true
mathjax: true
toc_sticky: true
header:
  overlay_image: /assets/img/02.jpg
categories:
  - Error-Resolution
tags:
  - python
  - tensorflow
  - version
  - error
last_modified_at: 2021-05-06
---

```shell
Traceback (most recent call last):
  File "train.py", line 2, in <module>
    ...
    from tensorflow.contrib import *
ModuleNotFoundError: No module named 'tensorflow.contrib'
```

GitHub에서 다운받은 소스를 테스트 해보다가 위와 같은 에러가 발생했다.
이 에러는 tensorflow 2.0 이후로는 `tensorflow.contrib` 이 삭제되어서 발생한다고 한다.

따라서 원래 tensorflow는 삭제해주고 **1.15 버전을 다시 설치**해주면 간단하게 해결된다.

## 1. 설치된 tensorflow 삭제

```shell
conda remove tensorflow
```

## 2. tensorflow 1.15 설치

```shell
conda install tensorflow==1.15
```

나중에 똑같은 오류가 발생했을 때 쉽게 해결하기 위해서 참고용으로 기록해두고자 한다.