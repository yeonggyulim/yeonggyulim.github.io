---
title: Github Pages 블로그 만들기 with Hexo
categories:
  - Github Pages 블로그 만들기
  - Hexo
tags:
  - Github Pages
  - Hexo
  - Blog
date: 2020-03-30 17:26:29
---
회사에서 1년 정도 일하면서 공부는 간간이 했지만 기록하거나 프로젝트로 관리하지 않으니 공부하고 있는 게 눈에 보이지 않아 기록하고 정리할 수 있는 블로그를 다시 시작해보기로 했습니다. 이전에는 Jekyll을 이용하여 Github Pages에 블로그를 올렸었는데, 이번에는 [Hexo의 next 테마](https://theme-next.org/)를 이용하여 블로그를 만들어 보기로 하였습니다. 먼저 사용하려고 하는 기술들을 간단히 정리하고 만드는 과정을 적어보도록 하겠습니다.

## 1. 기술 정리

### [Github Pages](https://pages.github.com/)
- 깃헙 저장소에서 바로 웹사이트를 만들 수 있는 무료 호스팅 서비스

### [Hexo](https://hexo.io/)
- 빠르고, 간단하고 파워풀한 블로그 프레임워크

## 2. 블로그 만들기

<!-- more -->

### Hexo Requirements
- [Node.js 10 버전 이상 설치](https://nodejs.org/en/)
- [Git 설치](https://git-scm.com/)

### Hexo Cli 설치
글로벌로 설치하고 싶지 않은 사용자들은 npm으로 hexo만 설치하고, npx hexo 명령어를 사용하지만 편의상 hexo cli 사용
```bash
$ npm install -g hexo-cli
```

### Hexo 프로젝트 Setup
```
$ hexo init <folder>
$ cd <folder>
$ npm install
```
설치하고 나면 다음과 같은 프로젝트 폴더 구조를 볼 수 있습니다.
```
<folder>
├── _config.yml
├── package.json
├── scaffolds
├── source
|   ├── _drafts
|   └── _posts
└── themes
    └── landscape
```

### Theme 설치 및 사용
먼저 마음에 드는 테마를 [Hexo 테마](https://hexo.io/themes/)에서 고른 뒤 themes 폴더 안에 설치해 줍니다. 저는 [Next Theme](https://theme-next.org/)를 사용하기로 하였습니다. Theme에 새로운 기능이 생길 때마다 기능을 바로바로 pull 받아 사용하려면 git clone으로 설치한 뒤 2개의 프로젝트(개인 Hexo 블로그 프로젝트, 테마 프로젝트)를 관리해 주어야 하지만 저는 편의상 released된 [v7.7.2 버전](https://github.com/theme-next/hexo-theme-next/releases/tag/v7.7.2)을 다운로드해 사용하기로 하였습니다.

zip 파일을 받아 themes 폴더 안에 넣어주고, <folder>의 _config.yml 파일에 theme을 `landscape`에서 `next`로 바꿔주었습니다.
![config_theme](/images/github-pages-blog/hexo/config_theme.png)

### Github 프로젝트 생성
메인 웹사이트로 사용하기 위해 [{username}.github.io](https://github.com/yeonggyulim/yeonggyulim.github.io) 명의 프로젝트 생성
![github_project_init](/images/github-pages-blog/hexo/github_project_init.png)

### Github Repository에 Hexo 프로젝트 올리기
프로젝트의 최상위 디렉토리에서 해당 명령어 입력
```
$ git init
$ git add .
$ git commit -m 'hexo blog first commit'
$ git remote add origin https://github.com/{username}/{username}.github.io.git
$ git push -u origin master
```

### 생성한 Hexo 프로젝트 테스트
프로젝트의 최상위 디렉토리에서 해당 명령어 입력
```
$ hexo server
```
[로컬호스트](http://localhost:4000/)로 접속하면 생성한 블로그를 로컬 환경에서 확인할 수 있습니다.

다음 포스트에서는 [Travis CI](https://travis-ci.com/)를 이용하여 자동 배포하는 과정을 다루어보도록 하겠습니다.