# 명령행 기초

커서(_)
```sh
$ _
```

로그인한 사용자 이름
```sh
$ whoami

username
```

새 디렉토리 만들기
```sh
mkdir javascripts
```

# 명령행 내비게이션

작업 디렉토리(print working directory)
```sh
$ pwd

/Users/username
```

작업 디렉토리 변경(change directory)
```sh
$ cd Projects/our-website

$ pwd

/Users/username/Projects/our-website
```

디렉토리 안의 파일과 디렉토리 목록(list)
```sh
$ ls

css        index.html
```

디렉토리 구별 옵션
```sh
$ ls -F

css/        index.html
```

디렉토리 안의 목록
```sh
$ ls css

style.css
```

디렉토리 이동 후 목록보기
```sh
$ cd css

$ ls

style.css
```

현재 디렉토리의 상위(..)
```sh
$ ls ..

css        index.html

$ cd ..

$ pwd

/Users/username/Projects/our-website
```

# 프롬프트

현재의 Git 브랜치
```sh
(master) $
```

```sh
(master *) $
```
