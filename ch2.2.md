
# Git 설정

> 사용자(Author)의 이름, 이메일 주소 속성
```sh
$ git config --global user.name "User Name"

$ git config --global user.email "name@email.com"
```

# 새 프로젝트 시작하기

```sh
$ mkdir our-website
```

```sh
$ cd our-website
```

> Git 저장소 초기화
```sh
$ git init
Initialized empty Git repository in /Users/username/our-website/.git/
(master) $
```

# 프로젝트 복제

> 복제 cloning
```sh
$ git clone https://github.com/gyp2018/study-git.git
Cloning into 'study-git'...
remote: Counting objects: 7, done.
remote: Compressing objects: 100% (5/5), done.
remote: Total 7 (delta 0), reused 7 (delta 0), pack-reused 0
Unpacking objects: 100% (7/7), done.

$ cd study-git
(master) $
```

> 다른 이름으로 복제
```sh
$ git clone https://github.com/gyp2018/study-git.git study-github
Cloning into 'study-github'...
remote: Counting objects: 7, done.
remote: Compressing objects: 100% (5/5), done.
remote: Total 7 (delta 0), reused 7 (delta 0), pack-reused 0
Unpacking objects: 100% (7/7), done.
```

```sh
$ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	index.html

nothing added to commit but untracked files present (use "git add" to track)
```

> 파일 추가
```sh
$ git add index.html
```

```sh
$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

	new file:   index.html

```

> 커밋 commit
```sh
$ git commit --message "Initial commit"
[master (root-commit) 15e96e8] Initial commit
 1 file changed, 1 insertion(+)
 create mode 100644 index.html
```

> --message 옵션은 -m으로 
```sh
$ git commit -m "Initial commit"
```

# 스테이징 영역 staging area
```sh
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   index.html

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	css/

no changes added to commit (use "git add" and/or "git commit -a")
```

```sh
$ git add index.html css/
```

```sh
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	new file:   css/style.css
	modified:   index.html

```

```sh
$ git commit -m "Add stylesheet"
[master c060094] Add stylesheet
 2 files changed, 14 insertions(+), 1 deletion(-)
 create mode 100644 css/style.css
 ```

```sh
$ git rm robots.txt
rm 'robots.txt'
```

```sh
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	deleted:    robots.txt

```

```sh
$ git commit -m "Remove robots.txt"
[master 6487c99] Remove robots.txt
 1 file changed, 1 deletion(-)
 delete mode 100644 robots.txt
 ```

 # 파일 이름 변경
```sh
$ git status
On branch master
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	deleted:    css/style.css

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	css/screen.css

no changes added to commit (use "git add" and/or "git commit -a")
```

```sh
$ git mv css/styles.css css/screen.css
fatal: bad source, source=css/styles.css, destination=css/screen.css
```

```sh
$ git rm css/style.css
rm 'css/style.css'
```

```sh
$ git add css/screen.css
```

```sh
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	renamed:    css/style.css -> css/screen.css
	modified:   index.html

```

# 핵폭탄: git add --all

> 로컬에서 변경된 모든 대상을 한 번에 스테이징 git add --all (git add -A)
```sh
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   index.html

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	js/

no changes added to commit (use "git add" and/or "git commit -a")
```

```sh
$ git add --all
``` 

```sh
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	modified:   index.html
	new file:   js/site.js

```

```sh
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	modified:   index.html
	new file:   js/site.js

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   index.html
	deleted:    js/site.js

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	scripts/

```

```sh
$ git add --all
```

```sh
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	modified:   index.html
	new file:   scripts/site.js

```

```sh
$ git commit -m "Add JavaScript"
[master 2dc7b08] Add JavaScript
 2 files changed, 2 insertions(+)
 create mode 100644 scripts/site.js
```
