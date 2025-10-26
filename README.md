# APK 온라인 배포 가이드

## 📱 빌드된 파일

- **APK 파일**: `app-release.apk` (27.3 MB)
- **다운로드 페이지**: `index.html`

## 🚀 호스팅 방법

### 옵션 1: GitHub Pages (무료, 추천)

가장 간단하고 무료인 방법입니다.

#### 설정 방법:
1. GitHub에 새 Repository 생성
2. `download_page` 폴더의 파일들을 업로드
3. Repository 설정에서 GitHub Pages 활성화
   - Settings → Pages
   - Source: Deploy from a branch
   - Branch: main (또는 master) → /root 선택
   - Save
4. 5분 정도 후 `https://[username].github.io/[repository-name]`에서 접속 가능

#### 장점:
- ✅ 완전 무료
- ✅ HTTPS 지원
- ✅ 별도 서버 필요 없음
- ✅ 안정적인 다운로드

#### 주의사항:
- ⚠️ Public repository만 무료로 GitHub Pages 사용 가능
- ⚠️ 파일 크기 제한: 100MB (현재 APK는 27.3MB로 문제없음)

---

### 옵션 2: Firebase Hosting (무료)

Google의 Firebase를 사용한 호스팅입니다.

#### 설정 방법:
1. [Firebase Console](https://console.firebase.google.com/) 접속
2. 새 프로젝트 생성
3. Firebase CLI 설치:
   ```bash
   npm install -g firebase-tools
   ```
4. 로그인 및 초기화:
   ```bash
   firebase login
   cd download_page
   firebase init hosting
   ```
5. 배포:
   ```bash
   firebase deploy
   ```

#### 장점:
- ✅ 무료 (10GB 저장소, 360MB/일 전송량)
- ✅ HTTPS 자동 설정
- ✅ 빠른 글로벌 CDN
- ✅ 커스텀 도메인 지원

---

### 옵션 3: Netlify (무료)

드래그 앤 드롭으로 간단하게 배포할 수 있습니다.

#### 설정 방법:
1. [Netlify](https://www.netlify.com/) 가입
2. "Add new site" → "Deploy manually" 선택
3. `download_page` 폴더를 드래그 앤 드롭
4. 자동으로 URL 생성 (예: `https://random-name-123.netlify.app`)
5. 원하면 커스텀 도메인 설정 가능

#### 장점:
- ✅ 완전 무료
- ✅ 드래그 앤 드롭으로 즉시 배포
- ✅ HTTPS 자동 설정
- ✅ 배포 후 즉시 사용 가능

---

### 옵션 4: Google Drive (가장 간단)

별도 호스팅 없이 Google Drive를 사용하는 방법입니다.

#### 설정 방법:
1. Google Drive에 `download_page` 폴더 업로드
2. APK 파일 우클릭 → 공유 → "링크가 있는 모든 사용자"로 설정
3. 링크 복사 후 테스터들에게 공유

#### 장점:
- ✅ 가장 간단함
- ✅ 별도 설정 불필요
- ✅ 무료

#### 단점:
- ❌ 다운로드 페이지 사용 불가 (직접 APK 링크만 공유)
- ❌ 다운로드 제한 가능성 (일일 트래픽 제한)

---

### 옵션 5: Vercel (무료)

#### 설정 방법:
1. [Vercel](https://vercel.com/) 가입
2. Vercel CLI 설치:
   ```bash
   npm install -g vercel
   ```
3. 배포:
   ```bash
   cd download_page
   vercel
   ```

#### 장점:
- ✅ 무료
- ✅ 즉시 배포
- ✅ HTTPS 자동
- ✅ 빠른 글로벌 CDN

---

## 🎯 추천 방법

**초보자/빠른 테스트**: Google Drive 또는 Netlify (드래그 앤 드롭)

**정식 배포**: GitHub Pages 또는 Firebase Hosting

## 📝 배포 후 체크리스트

- [ ] 다운로드 페이지가 정상적으로 표시되는지 확인
- [ ] APK 다운로드 버튼 클릭 시 파일이 다운로드되는지 확인
- [ ] 모바일에서도 페이지가 잘 보이는지 확인
- [ ] 다운로드 링크를 테스터들에게 공유

## 🔧 문제 해결

### APK 다운로드가 안 되는 경우

1. **MIME 타입 설정**
   - 일부 호스팅 서비스에서는 APK 파일을 차단할 수 있습니다
   - `.htaccess` 파일 추가:
     ```
     AddType application/vnd.android.package-archive .apk
     ```

2. **파일 크기 제한**
   - GitHub Pages: 100MB 이하 (현재 27.3MB - OK)
   - Firebase: 2GB 이하 (OK)
   - Netlify: 무료 플랜은 100MB 이하 (OK)

### 다운로드 속도가 느린 경우

- CDN을 지원하는 호스팅(Firebase, Netlify, Vercel) 사용 권장

## 💡 추가 팁

1. **커스텀 도메인 사용**
   - 더 전문적인 URL 제공
   - 예: `test.yourcompany.com`

2. **QR 코드 생성**
   - 배포 URL을 QR 코드로 변환
   - 테스터들이 모바일로 쉽게 접속 가능
   - 무료 QR 생성 사이트: https://www.qr-code-generator.com/

3. **비밀번호 보호**
   - 테스트 버전을 외부에 노출하고 싶지 않다면
   - Netlify Password Protection 기능 사용

4. **다운로드 추적**
   - Google Analytics 추가하여 다운로드 수 추적 가능

## 🔗 유용한 링크

- [GitHub Pages 문서](https://docs.github.com/ko/pages)
- [Firebase Hosting 문서](https://firebase.google.com/docs/hosting)
- [Netlify 문서](https://docs.netlify.com/)
- [Vercel 문서](https://vercel.com/docs)

---

## 📧 지원

문제가 발생하면 이슈를 등록하거나 개발팀에 문의하세요.


