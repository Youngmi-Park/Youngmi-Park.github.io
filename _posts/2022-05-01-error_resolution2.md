---
title:  "[Error] VScode SSH: Failed to save, EACCES permission denied 오류 해결"
excerpt: "VScode에서 SSH 접속 시 발생한 오류 해결"
strapline: "VScode에서 SSH 접속 시 발생한 오류 해결"
toc: true
comments: true
mathjax: true
toc_sticky: true
header:
  overlay_image: /assets/img/02.jpg
categories:
  - Error-Resolution
tags:
  - vscode
  - ubuntu
  - ssh
  - error
last_modified_at: 2021-05-01
---

## 오류 상황

VScode SSH를 통해 서버에 원격으로 접속하였는데, 파일을 생성하거나 수정하려고 하면 다음과 같은 오류 메시지가 나타났다.
또 로컬파일을 VScode로 직접 옮기는 것도 불가능한 상황이었다.

```shell
Failed to save : Unable to write file ‘vscode-remote://ssh-Nopermissions (FileSystemError): Error: EACCES: permission denied, open
```

## 해결 방법
terminal에서 sudo chown -R ubuntu *를 입력한다.

파일/폴더의 소유자가 ubuntu로 바뀌며 기본적인 작업들은 모두 할 수 있다.

이때, ubuntu가 아닌 특정 유저명을 입력하면 해당 유저에게 권한을 줄 수 있다.