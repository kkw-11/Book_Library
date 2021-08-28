# 도서관 대출 서비스

### 프로젝트 소개

---

도서관 대출 서비스는 레이서 도서관에 있는 책을 온라인으로 관리할 수 있는 웹 서비스입니다.

책의 상세 정보를 확인할 수 있는 페이지와 대여/반납 기능을 통해 도서 관리를 할 수 있는 웹 서비스를 제작하게 됩니다.

- [레이서 도서관 책 목록 보기](https://docs.google.com/spreadsheets/d/1Cd6psNhQUEc50-P7Z3HZoj4AEboTli3XhhniCa937Do/edit?usp=sharing)
- [레이서 도서관 책 이미지 목록](https://drive.google.com/drive/folders/1VgJD56KiIygWioZ0AaIX1c0pr8uDh7fV?usp=sharing)

### 프로젝트 개발기간

* 2021.08.16 ~ 2021.08.27

### 주요 사용 기술

* Flask, Jinja, My SQL, SQLAlchemy, Nginx, Azure, git

![image](https://user-images.githubusercontent.com/76929823/131218846-14f60fcd-4e7e-4f96-9642-e612be6711d8.png)


- 파이썬 패키지 버전

  ```bash
  python = "~3.7"
  Flask = "^1.1.2"
  SQLAlchemy = "^1.3.23"
  PyMySQL = "^1.0.2"
  python-dotenv = "^0.15.0"
  Flask-SQLAlchemy = "^2.4.4"
  bcrypt = "^3.2.0"
  Flask-Login = "^0.5.0"
  cryptography = "^3.4.5"
  email-validator = "^1.1.2"
  ```

### 와이어 프레임

---

https://whimsical.com/4uSB4tHy4ZjhBr8zuVVHoi




### 구현할 기능

---

`**필수**` 기능은 반드시 구현해야 하는 기능입니다.

**`선택`** 기능은 선택하여 구현하는 기능으로 필수가 아니며, 여기서 제시된 방식이 아닌 다른 방식으로 구현해도 괜찮습니다.

- **로그인**

  `**필수**`

  - 유저로부터 아이디(이메일)와 비밀번호 정보를 입력받아 로그인 합니다.
  - 아이디와 비밀번호는 필수 입력 사항 입니다.
  - 로그인한 유저에 대해 session으로 관리해야 합니다.

  **`선택`** 

  - 비밀번호는 다음의 [링크1](https://www.law.go.kr/%ED%96%89%EC%A0%95%EA%B7%9C%EC%B9%99/(%EA%B0%9C%EC%9D%B8%EC%A0%95%EB%B3%B4%EB%B3%B4%ED%98%B8%EC%9C%84%EC%9B%90%ED%9A%8C)%EA%B0%9C%EC%9D%B8%EC%A0%95%EB%B3%B4%EC%9D%98%EA%B8%B0%EC%88%A0%EC%A0%81%C2%B7%EA%B4%80%EB%A6%AC%EC%A0%81%EB%B3%B4%ED%98%B8%EC%A1%B0%EC%B9%98%EA%B8%B0%EC%A4%80/(2020-5,20200811)), [링크2](https://www.kisa.or.kr/public/laws/laws3_View.jsp?cPage=7&mode=view&p_No=259&b_No=259&d_No=102&ST=T&SV=)에 맞추어 최소 8자리 이상의 길이로 입력 받아야 합니다.
  - 아이디는 이메일 형식으로만 입력 받아야 합니다.

- **회원가입**

  `**필수**`

  - 유저로부터 아이디(이메일), 비밀번호, 이름 정보를 입력받아 회원가입합니다.
  - 비밀번호와 비밀번호 확인의 값이 일치해야 합니다.

  **`선택`** 

  - 아이디는 이메일 형식으로만 정보를 입력 받아야 합니다.
  - 이름은 한글, 영문으로만 입력 받아야 합니다.
  - 비밀번호는 다음의 [링크1](https://www.law.go.kr/%ED%96%89%EC%A0%95%EA%B7%9C%EC%B9%99/(%EA%B0%9C%EC%9D%B8%EC%A0%95%EB%B3%B4%EB%B3%B4%ED%98%B8%EC%9C%84%EC%9B%90%ED%9A%8C)%EA%B0%9C%EC%9D%B8%EC%A0%95%EB%B3%B4%EC%9D%98%EA%B8%B0%EC%88%A0%EC%A0%81%C2%B7%EA%B4%80%EB%A6%AC%EC%A0%81%EB%B3%B4%ED%98%B8%EC%A1%B0%EC%B9%98%EA%B8%B0%EC%A4%80/(2020-5,20200811)), [링크2](https://www.kisa.or.kr/public/laws/laws3_View.jsp?cPage=7&mode=view&p_No=259&b_No=259&d_No=102&ST=T&SV=)에 맞추어 영문, 숫자, 특수문자 중 2종류 이상을 조합하여 최소 10자리 이상 또는 3종류 이상을 조합하여 최소 8자리 이상의 길이로 구성합니다.

- **로그아웃**

  `**필수**`

  - 현재 로그인한 유저에 대해 로그아웃 합니다.
  - 로그아웃한 유저를 현재 session에서 제거해야 합니다.

- **메인 페이지**

  `**필수**`

  - 현재 DB 상에 존재하는 모든 책 정보를 가져옵니다.
  - 현재 DB 상에 존재하는 남은 책의 수를 표기합니다.
  - 책 이름을 클릭 시 책 소개 페이지로 이동합니다.
  - 책의 평점은 현재 DB 상에 담겨있는 모든 평점의 평균입니다. 숫자 한자리수로 반올림하여 표기합니다.

  **`선택`** 

  - 페이지네이션 기능을 추가합니다. 한 페이지 당 8권의 책만을 표기합니다.

- **대여하기**

  `**필수**`

  - 메인 페이지의 대여하기 버튼을 클릭하여 실행합니다.
  - 현재 DB 상에 책이 존재 하지 않는 경우, 대여되지 않습니다.
  - 현재 DB 상에 책에 존재하는 경우, 책을 대여하고 책의 권수를 -1 합니다.

  **`선택`** 

  - 현재 DB 상에 책이 존재하지 않는 경우, 유저에게 대여가 불가능하다는 메세지를 반환합니다.
  - 유저가 이미 이 책을 대여했을 경우, 이에 대한 안내 메세지를 반환합니다.

- **반납하기**

  `**필수**`

  - 로그인한 유저가 대여한 책을 모두 보여줍니다.
  - 반납하기 버튼을 통해 책을 반납합니다. 책을 반납한 후 DB 상에 책의 권수를 +1 합니다.

- **책소개**

  `**필수**`

  - 메인 페이지의 책 이름을 클릭하여 접근합니다.
  - 책에 대한 소개를 출력합니다.

  **`선택`** 

  - 가장 최신의 댓글이 보이도록 정렬하여 보여줍니다.
  - 댓글을 작성함으로써 책에 대한 평가 점수를 기입합니다.
  - 댓글 내용과 평가 점수는 모두 필수 입력 사항입니다.

- **대여기록**

  **`선택`** 

  - 로그인한 유저가 대여 후 반납했던 책에 대한 모든 사항을 출력합니다.

## 배운 점
* Flask 파이썬 웹 프레임워크를 통해 백엔드 API를 설계하는 방법 학습
* 파이썬 객체를 통해 DBMS를 다루는 SQLAlchemy를 다루는 방법을 학습
* 깃을 통한 프로젝트를 하며 branch를 통한 기능추가를 직접해보며 git의 중요성을 다시 한번 체감

## 아쉬웠던 점
* 짧은 시간 동안 많은 기능을 구현하면서 유지보수 및 확장성이 용이한 코드를 작성하지 못한 점이 아쉬움.

## 개선해야 할 사항
* api.py에 모든 API를 작성했는데, 기능별로 api 코드를 분리하여 객체지향적으로 코드 리팩토링
