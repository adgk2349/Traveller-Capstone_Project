# Traveller (Capstone Project)

University Capstone Design Project (Team Project)  
Originally developed in the `HSMighty7/Main` organization repository.

## Repository Origin
- Fork source: `HSMighty7/Main`
- Current repository: `adgk2349/capstone-project`
- Commit history and fork relationship are preserved.

---

## KR | 한국어

### 1) 프로젝트 소개
`Traveller (Capstone Project)`는 위치 기반 여행 지원 웹 애플리케이션입니다.  
사용자가 여행지/식당/카페를 검색하고, 현재 위치 기준으로 목적지까지의 경로를 시각화할 수 있도록 설계된 대학 캡스톤 팀 프로젝트입니다.

### 2) 핵심 기능
1. 회원 기능
- 회원가입, 로그인, 로그아웃
- 마이페이지 조회
- 아이디/비밀번호 수정

2. 검색 기능
- 키워드 기반 검색 (이름, 주소)
- 카테고리별 결과 제공 (명소, 식당, 카페)
- 사용자별 이전 검색 이력 조회

3. 지도/경로 기능
- 현재 위치 조회 및 저장
- 출발지(현재 위치)에서 목적지까지 경로 시각화
- Folium 지도 기반 경로 표시

### 3) 기술 스택
- Backend: `Python`, `Django 5`
- Geospatial: `OSMnx`, `NetworkX`, `Folium`, `GeoPandas`
- Database: Django ORM 기반 DB 구성(`my_settings.py`에서 설정)
- Frontend: Django Template, Bootstrap, CSS, JavaScript

### 4) 프로젝트 구조
```text
capstone-project/
├── main/                    # 핵심 앱 (views, models, templates)
├── mighty7/                 # Django project settings/urls/wsgi
├── map/                     # 경로 그래프 생성 스크립트 및 그래프 파일
├── static/                  # 정적 리소스 (css/js/img)
├── manage.py
├── requirements.txt
└── README.md
```

### 5) 로컬 실행 방법
1. 저장소 클론
```bash
git clone https://github.com/adgk2349/capstone-project.git
cd capstone-project
```

2. 가상환경 생성 및 의존성 설치
```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

3. `mighty7/my_settings.py` 생성
```python
from pathlib import Path

BASE_DIR = Path(__file__).resolve().parent.parent

SECRET_KEY = {
    "secret": "replace-with-your-secret-key"
}

DATABASES = {
    "default": {
        "ENGINE": "django.db.backends.sqlite3",
        "NAME": BASE_DIR / "db.sqlite3",
    }
}
```

4. 마이그레이션 및 서버 실행
```bash
python3 manage.py migrate
python3 manage.py runserver
```

5. 브라우저 접속
```text
http://127.0.0.1:8000
```

### 6) 주요 페이지 경로
- `/` : 메인 페이지
- `/search` : 여행지 검색
- `/location` : 현재 위치 조회/저장
- `/map` : 경로 시각화 결과
- `/users/login/` : 로그인
- `/users/join/` : 회원가입
- `/users/mypage/` : 마이페이지
- `/users/update/` : 회원정보 수정

### 7) 참고
- `map/graph.osm`은 경로 시각화에 사용하는 그래프 데이터 파일입니다.
- 그래프를 새로 생성하려면 `python3 map/map.py`를 실행하세요.

---

## EN | English

### 1) Overview
`Traveller (Capstone Project)` is a location-based travel web application developed as a university capstone team project.  
It helps users search attractions/restaurants/cafes and visualize routes from their current location to selected destinations.

### 2) Core Features
1. User account features
- Sign up, log in, log out
- My page profile view
- Username/password update

2. Search features
- Keyword search by place name or address
- Category-based results (attractions, restaurants, cafes)
- Per-user search history view

3. Map and route features
- Current location lookup and save
- Route visualization from origin to destination
- Folium-based map rendering

### 3) Tech Stack
- Backend: `Python`, `Django 5`
- Geospatial: `OSMnx`, `NetworkX`, `Folium`, `GeoPandas`
- Database: Django ORM with project-specific DB settings in `my_settings.py`
- Frontend: Django Templates, Bootstrap, CSS, JavaScript

### 4) Project Structure
```text
capstone-project/
├── main/                    # Core app (views, models, templates)
├── mighty7/                 # Django project settings/urls/wsgi
├── map/                     # Route graph script and graph data
├── static/                  # Static resources (css/js/img)
├── manage.py
├── requirements.txt
└── README.md
```

### 5) Local Setup
1. Clone repository
```bash
git clone https://github.com/adgk2349/capstone-project.git
cd capstone-project
```

2. Create virtual environment and install dependencies
```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

3. Create `mighty7/my_settings.py`
```python
from pathlib import Path

BASE_DIR = Path(__file__).resolve().parent.parent

SECRET_KEY = {
    "secret": "replace-with-your-secret-key"
}

DATABASES = {
    "default": {
        "ENGINE": "django.db.backends.sqlite3",
        "NAME": BASE_DIR / "db.sqlite3",
    }
}
```

4. Run migrations and start the server
```bash
python3 manage.py migrate
python3 manage.py runserver
```

5. Open in browser
```text
http://127.0.0.1:8000
```

### 6) Main Routes
- `/` : Home
- `/search` : Place search
- `/location` : Current location lookup/save
- `/map` : Route visualization
- `/users/login/` : Login
- `/users/join/` : Registration
- `/users/mypage/` : My page
- `/users/update/` : Account update

### 7) Notes
- `map/graph.osm` is the graph data used for route visualization.
- To regenerate graph data, run `python3 map/map.py`.
