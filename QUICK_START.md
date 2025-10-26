# 🚀 빠른 시작 가이드

APK를 온라인으로 배포하는 가장 빠른 방법을 안내합니다.

## 방법 1: Netlify로 5분 만에 배포하기 (초보자 추천)

### 1단계: Netlify 가입
- https://www.netlify.com/ 접속
- "Sign up" 클릭 (GitHub, GitLab, 이메일 등으로 가입)

### 2단계: 사이트 생성
1. 로그인 후 "Add new site" 클릭
2. "Deploy manually" 선택

### 3단계: 폴더 업로드
1. `download_page` 폴더를 드래그 앤 드롭으로 업로드
   - 폴더 전체를 드래그해서 Netlify 페이지에 놓으면 됩니다
   - 또는 파일들(index.html, app-release.apk, README.md)을 선택해서 업로드

### 4단계: 완료!
- 배포가 완료되면 자동으로 URL이 생성됩니다
- 예: `https://your-app-name-123.netlify.app`
- 이 URL을 테스터들에게 공유하면 됩니다

### 5단계 (선택): URL 이름 변경
1. Site settings → Site details → Change site name
2. 원하는 이름으로 변경 (예: `my-drug-app-test`)
3. 최종 URL: `https://my-drug-app-test.netlify.app`

---

## 방법 2: GitHub Pages로 무료 호스팅 (무료, 안정적)

### 1단계: GitHub Repository 생성
1. https://github.com 접속 및 로그인
2. 우측 상단 "+" → "New repository" 클릭
3. Repository 이름 입력 (예: `app-download`)
4. Public으로 설정 (Private는 유료)
5. "Create repository" 클릭

### 2단계: 파일 업로드
1. 생성된 Repository 페이지에서 "uploading an existing file" 클릭
2. `download_page` 폴더의 모든 파일 드래그 앤 드롭
   - index.html
   - app-release.apk
   - README.md
3. "Commit changes" 클릭

### 3단계: GitHub Pages 활성화
1. Repository 상단의 "Settings" 탭 클릭
2. 왼쪽 메뉴에서 "Pages" 클릭
3. Source 섹션에서:
   - Branch: main (또는 master) 선택
   - Folder: / (root) 선택
   - "Save" 클릭

### 4단계: 배포 완료 대기
- 약 5분 정도 기다리면 배포 완료
- 페이지 상단에 배포 URL이 표시됩니다
- 예: `https://[your-username].github.io/app-download`

---

## 방법 3: Google Drive로 즉시 공유 (가장 간단)

### 장점
- 계정만 있으면 즉시 사용 가능
- 별도 설정 불필요

### 단점
- 다운로드 페이지(index.html) 사용 불가
- APK 파일만 직접 공유

### 방법
1. Google Drive 접속
2. `app-release.apk` 파일 업로드
3. 파일 우클릭 → "공유" 클릭
4. "링크가 있는 모든 사용자" 선택
5. "링크 복사" 클릭
6. 이 링크를 테스터들에게 공유

---

## 📱 테스터에게 전달할 메시지 예시

```
안녕하세요!

의약품 정보 앱 테스트 버전이 준비되었습니다.
아래 링크에서 다운로드 받으실 수 있습니다.

📥 다운로드 페이지: [여기에 호스팅 URL 입력]

⚠️ 설치 시 주의사항:
1. 안드로이드 기기에서만 설치 가능합니다
2. "출처를 알 수 없는 앱" 설치 허용이 필요합니다
   (설정 → 보안 → 출처를 알 수 없는 앱 설치 허용)
3. 개발자 테스트 버전이므로 불안정할 수 있습니다

버그나 문제점을 발견하시면 알려주세요!

감사합니다.
```

---

## 🎯 추천 순서

1. **가장 빠른 방법**: Google Drive (APK만 공유)
2. **가장 간단한 방법**: Netlify (드래그 앤 드롭)
3. **가장 안정적인 방법**: GitHub Pages (무료, 영구 호스팅)

---

## 💡 QR 코드 생성하기

배포 URL을 QR 코드로 만들면 모바일에서 쉽게 접속할 수 있습니다.

### 방법 1: 온라인 생성기 사용
1. https://www.qr-code-generator.com/ 접속
2. "URL" 선택
3. 배포 URL 입력
4. QR 코드 다운로드
5. 테스터들에게 QR 코드 이미지 전달

### 방법 2: Python 스크립트 사용
`download_page` 폴더에 `generate_qr.py` 파일이 있습니다.
```bash
python generate_qr.py [여기에 URL 입력]
```

---

## ❓ 자주 묻는 질문

### Q1: 배포 URL을 변경할 수 있나요?
- **Netlify**: Site settings에서 언제든 변경 가능
- **GitHub Pages**: Repository 이름을 변경하면 URL도 변경됨
- **커스텀 도메인**: 모든 서비스에서 지원 (별도 도메인 필요)

### Q2: 무료로 계속 사용할 수 있나요?
- 네! 소개된 모든 방법은 무료로 계속 사용 가능합니다.

### Q3: APK 파일이 너무 크면 어떡하나요?
- 현재 27.3MB는 모든 무료 호스팅에서 문제없이 지원됩니다.
- 100MB 이상일 경우 Firebase Hosting 사용을 권장합니다.

### Q4: 다운로드 횟수 제한이 있나요?
- **GitHub Pages**: 월 100GB 대역폭 (충분함)
- **Netlify**: 월 100GB 대역폭 (충분함)
- **Firebase**: 월 10GB 저장소, 하루 360MB 전송 (작은 팀은 충분)

### Q5: 보안은 괜찮나요?
- 모든 서비스가 HTTPS를 자동으로 지원합니다.
- 외부 공개를 원하지 않으면 Netlify의 Password Protection 기능을 사용하세요.

---

## 🆘 문제가 생겼다면?

1. **다운로드가 안 돼요**
   - 브라우저 캐시 삭제 후 재시도
   - 다른 브라우저로 시도
   - 모바일 데이터 대신 Wi-Fi 사용

2. **설치가 안 돼요**
   - "출처를 알 수 없는 앱" 설치 허용 확인
   - 안드로이드 5.0 (API 21) 이상인지 확인
   - 저장 공간 충분한지 확인 (최소 50MB 이상)

3. **앱이 실행 안 돼요**
   - 앱 삭제 후 재설치
   - 개발팀에 로그 전달

---

## 📞 지원

더 자세한 내용은 `README.md`를 참고하세요.


