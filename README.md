# 교화 자료 앱 — GitHub Pages + APK 만들기

이 폴더 안의 파일들을 GitHub에 올리면, 나만의 링크가 생기고 그 링크로 안드로이드 설치 파일(APK)까지 만들 수 있습니다.

## 1단계. GitHub 저장소 만들기
1. https://github.com 접속 후 로그인 (계정이 없으면 무료로 만들기)
2. 오른쪽 위 `+` → `New repository` 클릭
3. Repository name에 `gyohwa-app` 같은 이름 입력, **Public**으로 설정 → `Create repository`

## 2단계. 파일 업로드
1. 방금 만든 저장소 페이지에서 `Add file` → `Upload files` 클릭
2. 이 폴더 안의 파일을 **전부** (index.html, manifest.json, sw.js, icons 폴더, images 폴더) 끌어다 놓기 — 이제 이미지가 9개 파일로 합쳐져 있어서 한 번에 올려도 됩니다
3. 아래 `Commit changes` 클릭

(만약 예전처럼 이미지가 낱장으로 100개 넘게 있던 버전이라 업로드가 안 됐다면, 이 새 버전으로 바꿔서 올려주세요 — GitHub 웹 업로더는 한 번에 100개 이상 파일을 받으면 실패합니다.)

## 3단계. GitHub Pages 켜기
1. 저장소 상단 `Settings` 탭 클릭
2. 왼쪽 메뉴에서 `Pages` 클릭
3. `Branch`를 `main`, 폴더는 `/ (root)`로 선택 → `Save`
4. 1~2분 기다리면 상단에 `https://내아이디.github.io/gyohwa-app/` 같은 주소가 생깁니다. 이 주소가 나만의 앱 링크입니다.

## 4단계. APK로 만들기 (PWABuilder)
1. https://www.pwabuilder.com 접속
2. 3단계에서 얻은 주소를 입력하고 `Start`
3. 분석이 끝나면 오른쪽 위 **"Package For Stores"** 버튼을 클릭 (이 버튼이 회색으로 눌리지 않으면 manifest.json이 아직 인식이 안 된 것이니 잠시 후 다시 시도해 보세요)
4. 뜨는 팝업에서 **Google Play(Android)** 칸의 `Generate Package` 클릭 → 완료되면 `.apk`(또는 `.aab`) 파일을 다운로드
5. 그 파일을 폰으로 옮겨서 설치 (안드로이드에서 "출처를 알 수 없는 앱" 설치를 허용해야 할 수 있습니다)

이 방식은 자체 도메인(github.io)에서 서비스되기 때문에, claude.ai 링크로 만들 때보다 더 앱에 가까운 느낌(주소창 없이 열릴 가능성)을 기대할 수 있습니다.

## 나중에 자료를 업데이트하려면
1. Claude에게 새 hwpx 파일을 보내 업데이트된 `index.html`을 다시 받습니다.
2. GitHub 저장소에서 기존 `index.html`을 새 파일로 다시 업로드(덮어쓰기)만 하면 됩니다.
3. GitHub Pages 링크와 이미 설치된 APK 앱 모두 자동으로 최신 내용을 불러옵니다 (서비스 워커가 새 버전을 감지해서 갱신합니다).
