# LDAP 인젝션

- LDAP 인젝션이란: 사용자 입력을 기반으로 LDAP(Lightewegith Directory Access Protocol)구문을 구축하여 웹 기반 응용 프로그램을 악용하는데 사용되는 공
- 점검 내용: 웹페이지 내 LDAP 인젝션 취약점 점검
- 점검 목적: 취약한 시스템에 신뢰할 수 없는 LDAP 코드 삽입 공격을 통한 비 인가자의 악의적인 행위를 차단하기 위함

### 캐럿마켓:

- 유효한 사용자 이름과 Blind LDAP 인젝션 쿼리를 비밀번호에 입력했을 때 권한 요청이 나옴
- Blind LDAP injection: 알 수 없는 정보를 추출 하기 위해 다중 요청을 보내고 서버 응답을 확인하여 쿼리가 유효한지 여부를 결정하는 공격
- 유효했던 구문들
    
    해당 사이트의 Blind LDAP injection 구문은 전부 권한 요청을 반환했음
    
    실제 권한이 있었다면 값을 반환 받을 수 있었을듯하다.
    
    권한 부여가 어떤 형식으로 되는지 파악한다면 매우 유효할 것 같음
    
    objectClass  명령어에 공통적으로 반응한듯함
    
    [Complete Guide to LDAP Injection: Types, Examples, and Prevention](https://brightsec.com/blog/ldap-injection/)
    
- 해당 사용자 이름은 abcdefghijklmnop@google.com 이었고 현재는 동일한 방법으로 시도해도 권한 요청이 아닌 잘못된 입력값이라고만 나옴

수행 후에 밴먹음

![스크린샷(129).png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/c22ba44f-cf8d-4407-a36b-779d695c9d4c/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7(129).png)

- ldap 취약점 검사에 사용한 코드
dic에 있는 문자열들을 차례대로 로그인 입력란에 입력함
    
    [ldap_karrot.py](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/56cb2862-21e9-4482-b38c-5d8e39402dcb/ldap_karrot.py)
    

ldap취약점 검사에 사용한 입력 값

`%2A%28%7C%28mail%3D%2A%29%29` == ***(|(mail=*)) mail 속성이 있다면 속성의 모든 값 반환**

**%2A%28%7C%28objectclass%3D%2A%29%29 == *(|(objectclass=*)):  objectclass 속성이 있다면 어떤 값을 가지는지 반환하는 명령어**

전체 입력값들
