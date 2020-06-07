---
layout: post
title: Git 코드 명령어
tags:
  - Git
  - Programming
---

## Jekyll 코드 명령어 기록
현재 Jekyll 을 사용해서 개인 블로그를 운영 중
자주 블로그 내용을 작성하는게 아니다보니 내용을 업데이트 해야할 때 마다 Jekyll 코드를 봐야하는 경우가 존재해서 따로 기록. 

---- 
### 로컬 테스트 서버 실행하기 
`bundle exec jekyll serve `

브라우저에서 [http://127.0.0.1:4000/](http://127.0.0.1:4000) 로 접속해서 블로그 내용 확인
GitHub로 바로 블로그 내용을 업데이트 하기 이전, 웹사이트에서 반영되는 모습을 확인하기 필요함. 

---- 
### Github에 블로그 업로드 하기

#### 1. 블로그 글 작성하기 
블로그 글은 연결된 로컬 저장소의 posts폴더 아래에 작성하며 반드시  YYYY-MM-DD-제목.md 의 형식으로 파일이름을 지정. 

#### 2. 블로그 글 업데이트 하기 

```git init```
Jekyll 블로그 생성했던 폴더에서 로컬 GIT 저장소를 시작

```git remote add origin [리모트저장소주소]```
명령어로 로컬 저장소와 리모트 저장소를 연결 

```bash
git add [File_tobeuploaded.md]
//파일을 업로드 
git commit - m [Commit Message]
// 커밋 메시지 추가 
git push origin master
// github에 업로드  
```

git에서 파일명이 변경되거나 혹은 파일 삭제를 반영하는 방법 
```git add -u```
삭제된 파일만 Commit 
```git commit -a -m 메시지내용 ```

Will be updated accordingly. 
Thanks, 