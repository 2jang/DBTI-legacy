# DBTI 🐾 MBTI와 맞는 강아지 찾기 & 반려견 성향 분석 서비스
[![status](https://img.shields.io/endpoint?url=https%3A%2F%2Fstatus.2jang.dev%2Fapi%2Fbadges%3Fid%3Ddbti%26label%3Dstatus%26up%3DOnline%26down%3DOffline%26colorUp%3D10b981%26colorDown%3Ddf484a&style=for-the-badge&logo=cloudflare&logoColor=white&labelColor=065f46)](https://status.2jang.dev)
[![Python](https://img.shields.io/badge/Python-3.7%2B-blue?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Flask](https://img.shields.io/badge/Flask-3.1.1-black?style=for-the-badge&logo=flask&logoColor=white)](https://flask.palletsprojects.com/)

DBTI 프로젝트는 사용자의 MBTI 성향에 맞는 반려견을 추천하고, 성격검사를 통해 반려견의 성격 유형(DBTI)을 분석하여  
반려자에게 양육에 대한 이해를 돕고 맞춤형 정보를 제공하는 서비스입니다.  

<p align="center">
  <br>
  <img src="static/images/readme/dbti_main.png">
  <br>
</p>

## ✨ 주요 기능

- 👤 **MBTI 기반 견종 추천**:  
    - 사용자의 MBTI를 입력하면, 성향에 맞는 견종과 해당 견종의 특징을 알려줍니다.

- 🐕 **DBTI 반려견 성향 검사**:
    - 웹페이지에서 12가지 설문을 통해 반려견의 DBTI 유형을 분석합니다.
    - 분석된 DBTI 결과는 해당 DBTI에 대한 상세 설명과 함께 양육 솔루션이 제공됩니다.

## 🏗️ 프로젝트 구조

```text
DBTI/
│
├── app.py                      # 메인 Flask 애플리케이션
├── test_app.py                 # 테스트 코드
│
├── static/
│   ├── dbti/
│   │   └── csv/dbti_types.csv  # DBTI 설명
│   │
│   └── mbti/
│       ├── csv/
│       │   ├── dog_match.csv   # 추천 견종 정보
│       │   └── mbti_types.csv  # MBTI 설명
│       │
│       └── mbti_crawling.py    # 크롤링 스크립트
│
└── templates/
    └── index.html              # DBTI 검사 웹 페이지
```

## 🚀 설치 및 실행 방법

- Python 3.8 이상 권장

### pip 패키지

프로젝트 실행에 필요한 패키지는 `requirements.txt` 파일에 있습니다.

```text
Flask~=3.1.1
flask-cors~=6.0.0
SpeechRecognition~=3.14.2
pandas~=2.2.3
requests~=2.32.3
bs4~=0.0.2
beautifulsoup4~=4.13.4
pytest~=8.3.5
```

### 서버 실행

1.  **저장소 클론 또는 다운로드**:
    ```bash
    git clone https://github.com/2jang/DBTI.git
    cd DBTI
    ```

2. **필요한 패키지 설치**:
    ```bash
    pip install -r requirements.txt
    ```

5.  **Flask 애플리케이션 실행**:
    ```bash
    python app.py
    ```
    `http://localhost:5000`에서 실행됩니다.

## 🔄 API 엔드포인트

-   **`GET /`**:
    -   DBTI 검사를 위한 메인 웹페이지 (`index.html`)를 제공합니다.
    

-   **`POST /submit_dbti`**:
    -   설명: `index.html`에서 사용자가 완료한 DBTI 결과를 받아 서버에 저장합니다.
    -   요청 (JSON):
        ```json
        {"dbti": "결과DBTI유형"}
    -   응답 (JSON):
        ```json
        {"message": "DBTI 저장 완료"}
    

## 🧩 사용된 기술

-   **언어**: Python
-   **웹 프레임워크**: Flask
-   **웹 크롤링**: `BeautifulSoup4` 
-   **데이터 처리**: Pandas
-   **테스팅**: `pytest`

## 🌟 특징

-   **웹-서버 간 비동기 통신**: fetch를 사용하여 웹 프론트엔드와 Flask 서버 간에 비동기적으로 통신
-   **웹 크롤링을 통한 데이터 구축**: 크롤링 스크립트로 외부 웹사이트에서 MBTI 관련 데이터를 수집하고 CSV 파일로 저장

## 🤝 기여하기

버그 리포트, 기능 제안, 코드 개선 등 모든 종류의 기여를 환영합니다!
1.  이 저장소를 Fork합니다.
2.  새로운 기능 브랜치를 생성합니다. (`git checkout -b feature/AmazingFeature`)
3.  변경 사항을 커밋합니다. (`git commit -m 'Add some AmazingFeature'`)
4.  브랜치에 푸시합니다. (`git push origin feature/AmazingFeature`)
5.  Pull Request를 생성합니다.

## 📝 라이센스

이 프로젝트는 [MIT 라이센스](LICENSE) 하에 배포됩니다.

## 🙏 감사의 말

-   MBTI 성격 유형 정보 제공: [16Personalities](https://www.16personalities.com)
-   DBTI 관련 아이디어 및 데이터 참고: [포동](https://www.fordong.co.kr/)

⭐ 이 프로젝트가 마음에 드셨다면 Star를 눌러주세요! ⭐
