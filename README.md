# 규칙

- 패키지 관리: `npm`이 아니라, `yarn`을 사용합니다.

# 서버 구동을 위해 준비해야 하는 것들

- node: 10.15 버전
- yarn
- mysql server(8.0 이상) 또는 그와 대응하는 서버(예를 들어, mariadb)
- 다음 명령어 실행

```bash
$ yarn install
```

## 환경 설정

데이터 베이스 설정에 맞게 환경변수를 설정해줘야 합니다.

다음 내용을 `~/.bashrc` 파일의 끝에 추가합니다.
`[]`로 써 있는 내용을 각 항목에 맞게 입력하시면 됩니다.

```bash
#########################################
## For Database Connection
#########################################
export NODE_DATABASE_USERNAME="[mysql 서버 사용자 이름]"
export NODE_DATABASE_PASSWORD="[mysql 서버 사용자 비밀번호]"
export NODE_DATABASE_NAME="[데이터베이스 이름]"
export NODE_DATABASE_HOST="[데이터베이스 호스트 주소]"
export NODE_DATABASE_PORT="[데이터베이스 호스트 포트 번호]"
export NODE_DATABASE_DIALECT="mysql"

#########################################
## For S3 connection through multer
#########################################
export NODE_S3_API_ACCESSKEY="[S3 Access Key]"
export NODE_S3_API_SECRETKEY="[S3 Secret Key]"

#########################################
## for crypto algorithms and tokens
#########################################
# 아래의 정보는 원하는 대로 정할 수 있음. config/index.js에서 기본 값 참고 가능.
export NODE_SECRET="[jwt와 암호화 시크릿 키]"
export NODE_EXPIRE_TIME="[토큰 만료 기간]"
export NODE_SALT="[암호화 솔트키]"
export NODE_CRYPTO_ALGORITHM="[암호화 알고리즘]"
```

다음 명령어로 현재 SHELL 세션에 불러옵니다.

```bash
$ source ~/.bashrc
```

# 서버 구동하기

다음 명령어를 실행하여 서버를 구동할 수 있습니다.

```bash
$ yarn start
```

## 데이터베이스 초기화

데이터베이스를 초기화할 일이 있다면 다음 명령어를 사용하면 됩니다.

```bash
$ export DATABASE_RESET=true
```

데이터 베이스 초기화가 완료되면 다음 명령어를 사용하여 매번 초기화되는 일이 없도록 합니다.

```bash
$ unset DATABASE_RESET
```

# API 정보

`api.rest` 파일에 API 정보가 나와 있습니다. API 정보를 원하는 경우 파일을 참조하세요. 이 파일은 "Visual Studio Code"의 "REST client"에서 사용 가능한 파일입니다.
