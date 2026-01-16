# 단체선물 주문 현황 확인 시스템

Redash API를 활용한 실시간 주문 현황 조회 웹페이지입니다.

## 🚀 빠른 시작

### 1. Redash 정보 확인

먼저 다음 정보를 확인하세요:

1. **Redash 서버 URL**
   - 예: `https://redash.your-company.com`

2. **API Key 발급**
   - Redash 로그인 → 우측 상단 프로필 아이콘 클릭
   - Settings → API Key 탭
   - API Key 복사

3. **쿼리 ID 확인**
   - 해당 쿼리 페이지에서 URL 확인
   - 예: `https://redash.your-company.com/queries/123` → 쿼리 ID는 `123`

### 2. 설정 파일 수정

`app.js` 파일의 상단 설정 영역을 수정하세요:

```javascript
const CONFIG = {
    REDASH_URL: 'https://your-redash-server.com',  // ← 여기에 Redash 서버 URL
    API_KEY: 'YOUR_API_KEY_HERE',                   // ← 여기에 발급받은 API Key
    QUERY_ID: 'YOUR_QUERY_ID',                      // ← 여기에 쿼리 ID
};
```

### 3. GitHub에 업로드

#### 방법 1: GitHub Desktop 사용 (초보자 추천)

1. [GitHub Desktop](https://desktop.github.com/) 다운로드 및 설치
2. GitHub 계정 로그인
3. File → New Repository 클릭
   - Name: `group-gift-status` 입력
   - Local Path: 이 폴더 선택
   - ✅ Initialize this repository with a README 체크 해제
4. "Create Repository" 클릭
5. "Publish repository" 클릭
   - ✅ Keep this code private 체크 해제 (공개로 설정)
6. 파일들이 업로드됩니다

#### 방법 2: Git 명령어 사용

```bash
# 1. Git 저장소 초기화
git init

# 2. 파일 추가
git add .

# 3. 첫 커밋
git commit -m "Initial commit"

# 4. GitHub 저장소 생성 후 연결
git remote add origin https://github.com/YOUR_USERNAME/group-gift-status.git

# 5. 업로드
git branch -M main
git push -u origin main
```

### 4. GitHub Pages 활성화

1. GitHub 저장소 페이지로 이동
2. Settings → Pages 메뉴 클릭
3. Source에서 "Deploy from a branch" 선택
4. Branch에서 "main" 선택, 폴더는 "/ (root)" 선택
5. Save 클릭
6. 약 1-2분 후 페이지가 배포됩니다

배포된 URL: `https://YOUR_USERNAME.github.io/group-gift-status/`

### 5. 사용 방법

#### 기본 사용
```
https://YOUR_USERNAME.github.io/group-gift-status/
```
→ 기본값 템플릿 번호 2로 조회

#### 템플릿 번호 지정
```
https://YOUR_USERNAME.github.io/group-gift-status/?number=5
```
→ 템플릿 번호 5로 조회

```
https://YOUR_USERNAME.github.io/group-gift-status/?number=10
```
→ 템플릿 번호 10으로 조회

## 📋 주요 기능

### 실시간 현황 조회
- ✅ 전체/미선택/선택완료/주문확정/배송완료 건수 표시
- ✅ 실시간 데이터 새로고침
- ✅ 자동 업데이트 시간 표시

### 검색 및 필터
- 🔍 이름, 전화번호, 상품명으로 검색
- 🏷️ 상태별 필터링
- 📄 페이지네이션 (50개씩)

### 개인정보 보호
- 🔒 이름 마스킹 (홍길동 → 홍*동)
- 🔒 전화번호 마스킹 (010-1234-5678 → 010-****-5678)

### 반응형 디자인
- 📱 모바일, 태블릿, PC 모두 지원
- 🎨 직관적인 UI/UX

## 🔧 문제 해결

### CORS 오류가 발생하는 경우

Redash 서버에서 CORS를 허용해야 합니다. 관리자에게 요청하세요:

```
Access-Control-Allow-Origin: https://YOUR_USERNAME.github.io
```

또는 Redash API Key를 사용할 때 `embed` 옵션을 활성화하세요.

### 데이터가 로드되지 않는 경우

1. 브라우저 개발자 도구(F12) → Console 탭에서 오류 확인
2. Network 탭에서 API 호출 상태 확인
3. `app.js`의 CONFIG 설정이 올바른지 확인

### API Key 보안

⚠️ **주의**: API Key가 공개 저장소에 노출됩니다!

보안이 중요한 경우:
1. Private Repository로 설정하거나
2. 환경변수나 설정 파일로 분리하거나
3. Backend API를 통해 프록시하는 방식으로 구현하세요

## 📁 파일 구조

```
group-gift-status/
├── index.html       # 메인 HTML
├── styles.css       # 스타일시트
├── app.js          # JavaScript (Redash API 연동)
└── README.md       # 이 파일
```

## 🔄 업데이트 방법

### GitHub Desktop 사용
1. 파일 수정
2. GitHub Desktop에서 변경사항 확인
3. Summary에 변경 내용 입력
4. "Commit to main" 클릭
5. "Push origin" 클릭

### Git 명령어 사용
```bash
git add .
git commit -m "설명"
git push
```

## 📞 지원

문제가 발생하거나 궁금한 점이 있으면 이슈를 등록해주세요!

## 📝 라이선스

MIT License - 자유롭게 사용하세요!
