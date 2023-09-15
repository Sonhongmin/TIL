# git

#### terminal
- 명령어

    1. mv *.py dist(폴더이름)

    2. cp ./dist/README.md(복사할 대상의 경로/파일이름) ./(복사파일 넣을 경로)

    3. mv random.py get_lotto.py
       복사할대상  복사파일 이름 바꾸기 가능
    4. rm ma*.py
    (ma*(에스트로퍼) => ma 문자를 포함한 모든 파일이름의 .py 파일을 삭제)

    5. rm [a-i]*.py 
    ( [a-i]* a부터i 까지의 문자가 들어가있는 .py 파일을 삭제

    6. cat sample.py
    (sample.py 의 내용을 출력)

#### git start
1. 기본세팅
    $ git config --global user.name "Sonhongmin"
    $ git config --global user.email "sonhongmin0907@gmail.com"
    $ git config --global core.editor "vim"
    $ git config --global core.paper "cat"

    (git bash -> 복사하는거 shift + insert) 

2. git clone(기본적인 예시)
    - 깃 레포지토리에서 code 영역의 git주소 복사
    - 깃 복사할 곳에 가서 $ git clone git주소
    - 지금 있는 경로에 레포지토리 이름으로 된 폴더생성
    - README.md 파일 수정함
    - $ git status 
    - 하면 빨간색으로 수정되었다고 뜸

3. $ git add README.md

    수정된거 올릴려는 준비(?)

4. $ git commit

    하면 vim창 열림

    그럼 위쪽에 설명적고(맨 윗줄은 제목느낌)

    엔터 두번에 상세설명 쓰고 

    저장 하고 나감(:wq)

    그럼 add 됐다고 나옴

5. $ git push origin main

    이 때 push할 때 비밀번호 넣으라고 나오는데 

    이건 깃 settings에서 token 발급 해서 그 비밀번호로 해야함

    이럼 완성!

    그리고 팁은 깃허브에서 바로 수정하지 말 것!!!

    기본적인 건 여기까지

#### pre-commit
- 자동검수(?)기능

    1. pip install pre-commit

    2. pip freeze > requirements.txt

    3. pre-commit sample-config > .pre-commit-config.yaml

    4. pre-commit run

    5. pre-commit run -a

    6. vi .pre-commit-config.yaml
```
# See https://pre-commit.com for more information
# See https://pre-commit.com/hooks.html for more hooks
repos:
-   repo: https://github.com/pre-commit/pre-commit-hooks
    rev: v3.2.0
    hooks:
    -   id: trailing-whitespace
    -   id: end-of-file-fixer
    -   id: check-yaml
    -   id: check-added-large-files
    -   id: check-ast
    -   id: double-quote-string-fixer
    -   id: check-merge-conflict
-   repo: https://github.com/asottile/add-trailing-comma
    rev: v3.1.0
    hooks:
    -   id: add-trailing-comma
```
    7. pip install add-trailing-comma

    8. pre-commit run

    9. pre-commit run -a (커밋(?)된거 말고 모든것)

    10. pre-commit install

#### etc.
1. vim

normal mode : press esc from any mode
insert mode :  press i from normal mode
visual mode : press v from normal mode
command mode : press : from normal mode

2. tip

https://rahuldkjain.github.io/gh-profile-readme-generator/  -> git README.md 파일 꾸미기
https://www.toptal.com/developers/gitignore -> git ignore 프리셋
https://segment-anything.com/ -> 페이스북 리서치

git blame 파일이름 -> 누군가 비난하고 싶을 때 로그 서치!
git commit --amend -> 직전!! commit만 글 수정 가능
git restore --staged fizzbuzz.py add된 파일을 다시 돌려놓는 명령어

pre-commit.com
pip install pre-commit

https://pre-commit.com/hooks.html
https://github.com/asottile/add-trailing-comma (맨뒤에 콤마 찍는거! 중요)
