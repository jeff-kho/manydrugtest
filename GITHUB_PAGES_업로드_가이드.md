# 📤 GitHub Pages 업로드 가이드

## 방법 1: 웹 브라우저로 업로드 (가장 쉬움) ⭐ 추천

### 1단계: GitHub Repository 생성

1. **https://github.com** 접속 및 로그인
2. 우측 상단 **"+"** 버튼 클릭 → **"New repository"** 선택
3. Repository 설정:
   - **Repository name**: `drug-app-download` (원하는 이름 입력)
   - **Description** (선택): "의약품 정보 앱 다운로드 페이지"
   - **Public** 선택 (⚠️ 중요: Private는 유료)
   - **Add a README file** 체크 해제
   - **Add .gitignore** 선택 안 함
   - **Choose a license** 선택 안 함
4. **"Create repository"** 클릭

### 2단계: 파일 업로드

Repository가 생성되면 빈 페이지가 나타납니다.

#### 옵션 A: 드래그 앤 드롭 (가장 간단)

1. 페이지 중앙에 **"uploading an existing file"** 링크 클릭
   - 또는 페이지 상단의 **"Add file"** → **"Upload files"** 클릭

2. **파일 선택**:
   - Finder(맥) 또는 탐색기(윈도우)에서 `download_page` 폴더 열기
   - 다음 파일들을 **모두 선택**:
     - `index.html`
     - `app-release.apk`
     - `README.md`
     - `QUICK_START.md`
     - `generate_qr.py`
     - `배포_완료_체크리스트.md`
   
3. **선택한 파일들을 드래그**하여 GitHub 페이지의 점선 박스에 **드롭**

4. 파일이 업로드되는 동안 기다리기 (APK가 27MB라서 1-2분 소요)

5. 페이지 하단에서:
   - **Commit message**: "Initial commit - APK 다운로드 페이지 추가"
   - **"Commit changes"** 버튼 클릭

#### 옵션 B: "Add file" 버튼 사용

1. Repository 메인 페이지에서 **"Add file"** 버튼 클릭
2. **"Upload files"** 선택
3. **"choose your files"** 클릭하여 파일 선택
4. 위의 파일들을 모두 선택
5. **"Commit changes"** 클릭

### 3단계: GitHub Pages 활성화

파일 업로드가 완료되면:

1. Repository 상단 메뉴에서 **"Settings"** (⚙️) 탭 클릭

2. 왼쪽 사이드바에서 **"Pages"** 메뉴 클릭

3. **"Build and deployment"** 섹션에서:
   - **Source**: "Deploy from a branch" 선택
   - **Branch**: 
     - 드롭다운에서 `main` (또는 `master`) 선택
     - 폴더는 `/ (root)` 선택
   - **"Save"** 버튼 클릭

4. ✅ 완료! 페이지 상단에 다음과 같은 메시지가 표시됩니다:
   ```
   Your site is live at https://[username].github.io/drug-app-download/
   ```

### 4단계: 배포 확인 (약 2-5분 소요)

1. **"Actions"** 탭 클릭하여 배포 진행 상황 확인
2. 녹색 체크 표시(✓)가 나타나면 배포 완료
3. 생성된 URL 접속:
   ```
   https://[your-username].github.io/[repository-name]/
   ```

---

## 방법 2: Git 명령어로 업로드 (개발자용)

터미널이나 Git에 익숙하다면 이 방법이 더 빠릅니다.

### 사전 준비

Git이 설치되어 있어야 합니다. 확인:
```bash
git --version
```

### 1단계: GitHub에서 Repository 생성

위의 "방법 1"의 1단계와 동일합니다.

### 2단계: Repository 초기화 및 파일 추가

터미널을 열고 다음 명령어를 실행:

```bash
# download_page 폴더로 이동
cd "/Users/mm/StudioProjects/Manydrug-feature-project-update 2/download_page"

# Git 초기화
git init

# 모든 파일 추가
git add .

# 커밋
git commit -m "Initial commit - APK 다운로드 페이지"

# 기본 브랜치 이름을 main으로 설정
git branch -M main

# GitHub Repository 연결 (⚠️ 아래 URL을 본인의 것으로 변경!)
git remote add origin https://github.com/[your-username]/[repository-name].git

# 푸시
git push -u origin main
```

**⚠️ 중요**: `[your-username]`과 `[repository-name]`을 실제 값으로 변경하세요!

예시:
```bash
git remote add origin https://github.com/johndoe/drug-app-download.git
```

### 3단계: GitHub Pages 활성화

위의 "방법 1"의 3단계와 동일합니다.

---

## ⚠️ 자주 발생하는 문제 해결

### 문제 1: "Large file" 경고 발생

APK 파일(27.3MB)은 GitHub의 50MB 제한보다 작아서 문제없지만, 경고가 나올 수 있습니다.

**해결**: 그냥 무시하고 계속 진행하세요. 업로드는 정상적으로 됩니다.

### 문제 2: "404 Not Found" 오류

배포 URL에 접속했는데 404 오류가 나타나는 경우:

**원인**: 
- 배포가 아직 완료되지 않음 (5분 정도 소요)
- 잘못된 URL 접속

**해결**:
1. 5분 정도 기다린 후 다시 시도
2. URL 확인: `https://[username].github.io/[repository-name]/`
3. "Actions" 탭에서 배포 상태 확인

### 문제 3: "Public repository required"

Private repository에서 GitHub Pages를 사용하려고 하면 이 오류가 발생합니다.

**해결**:
1. Repository Settings → Danger Zone
2. "Change repository visibility" → "Change to public"
3. 다시 GitHub Pages 활성화

### 문제 4: APK 다운로드가 안 됨

페이지는 정상이지만 APK 다운로드가 안 되는 경우:

**원인**: GitHub Pages가 APK 파일을 차단하는 경우 (드물음)

**해결**:
1. APK 파일이 제대로 업로드되었는지 확인
2. `index.html`의 다운로드 경로 확인:
   ```javascript
   const apkUrl = './app-release.apk';  // 이 경로가 맞는지 확인
   ```
3. 브라우저 콘솔(F12)에서 에러 확인

---

## 📱 배포 완료 후 테스트

1. **데스크탑 브라우저에서 테스트**:
   - URL 접속
   - 페이지가 정상적으로 표시되는지 확인
   - APK 다운로드 버튼 클릭

2. **모바일에서 테스트** (중요!):
   - 안드로이드 기기에서 URL 접속
   - 모바일 화면에서 레이아웃 확인
   - APK 다운로드 및 설치 테스트

3. **다양한 브라우저에서 테스트**:
   - Chrome
   - Safari
   - Samsung Internet
   - Firefox

---

## 🔄 나중에 APK 업데이트하는 방법

### 웹 브라우저 사용:

1. GitHub Repository 접속
2. `app-release.apk` 파일 클릭
3. 휴지통 아이콘(🗑️) 클릭하여 삭제
4. "Add file" → "Upload files"
5. 새로운 APK 업로드
6. `index.html`에서 버전 정보도 업데이트
   - 파일 클릭 → 연필(✏️) 아이콘으로 편집

### Git 명령어 사용:

```bash
cd "/Users/mm/StudioProjects/Manydrug-feature-project-update 2"

# 새 APK 빌드
flutter build apk --release

# 새 APK 복사
cp build/app/outputs/flutter-apk/app-release.apk download_page/

# Git 커밋 및 푸시
cd download_page
git add app-release.apk
git commit -m "Update APK to version 1.0.1"
git push
```

---

## 🎯 최종 체크리스트

- [ ] GitHub Repository 생성 완료
- [ ] 모든 파일 업로드 완료 (6개 파일)
- [ ] GitHub Pages 활성화 완료
- [ ] 배포 완료 (Actions에서 ✓ 확인)
- [ ] 데스크탑에서 접속 테스트
- [ ] 모바일에서 접속 테스트
- [ ] APK 다운로드 테스트
- [ ] 실제 기기에 설치 테스트
- [ ] URL을 테스터들에게 공유

---

## 📞 추가 도움말

- **GitHub Pages 공식 문서**: https://docs.github.com/ko/pages
- **Git 기초**: https://git-scm.com/book/ko/v2
- **Markdown 가이드**: https://docs.github.com/ko/get-started/writing-on-github

---

## 💡 프로 팁

1. **README.md 활용**: Repository에 README.md가 있으면 방문자에게 설명 표시
2. **커스텀 도메인**: Settings → Pages에서 본인의 도메인 연결 가능
3. **HTTPS 자동 적용**: GitHub Pages는 무료로 HTTPS 제공
4. **무제한 트래픽**: 소규모 팀 테스트에는 충분한 트래픽 제공

---

배포 성공을 기원합니다! 🚀

