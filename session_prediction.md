# 세션 예측

- 점검 내용: 단순한 방법으로 생성되는 세션 ID를 예측하여 세션 탈취 여부 점검
- 점검 목적: 사용자의 세션 ID를 추측 불가능하도록 난수로 생성하여 공격자의 불법적인 접근을 차단하기 위함
- 검증하는데 오랜 시간이 필요할 것 같음 추후 시행 예정
- 세션 ID
    
    ID1 : GwOAovFeAHE-mIODSqd95dDOm-v5BmpgB5Fv-ofx
    
    ![세션 ID_1.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/8e7f0aeb-630b-4d29-8f60-1646bd7e6e7a/%EC%84%B8%EC%85%98_ID_1.png)
    
    해당 ID의 네트워크 구성
    
    - Public IP: 1.235.206.237
    - Private IP: 172.20.40.225
    - Subnet Mask: 255.255.255
    - MAC:  8C-B0-E9-1C-D1-72
    - URL: [https://business.daangn.com/profile/login](https://business.daangn.com/profile/login)
    
    ![스크린샷(2).png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/5d33410c-97f3-459c-8f91-889a01c6eac5/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7(2).png)
    

- 참고 사이트
    - [https://coconuts.tistory.com/533](https://coconuts.tistory.com/533)
    - [https://velog.io/@chlwogur2/사용자-인증을-위한-세션-인증-방식](https://velog.io/@chlwogur2/%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%9D%B8%EC%A6%9D%EC%9D%84-%EC%9C%84%ED%95%9C-%EC%84%B8%EC%85%98-%EC%9D%B8%EC%A6%9D-%EB%B0%A9%EC%8B%9D)
