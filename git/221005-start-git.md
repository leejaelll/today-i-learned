# How to create new repo

## Before start, set configuration

$ git config --global user.name "유저네임"
$ git config --global user.email "이메일 주소"
$ git config --global core.editor "vim" - editor를 vim으로 설정
$ git config --global core.pager "cat"

## Create new repo

$ mkdir first-repo && cd first-repo
$ git init
$ git remote add origin https://github.com/{username}/{reponame}.git
$ touch README.md
$ git add README.md
$ git commit -m "docs: Create README.md"
$ git push -u origin master

local main과 origin main은 이름만 같은 상태, 서로 연결을 시켜주어야 한다. -u를 사용(upstream set)

