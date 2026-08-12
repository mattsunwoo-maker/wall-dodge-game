# 벽 피하기 게임 PWA 패키지

이 폴더 안 파일 전체(`index.html`, `manifest.json`, `sw.js`, `icons/`, `.well-known/`)를 같은 폴더 구조 그대로 웹 호스팅에 올리면 PWA로 동작합니다.

## 1. 호스팅에 올리기 (무료 옵션)

- GitHub Pages, Netlify, Vercel, Firebase Hosting 중 아무거나 선택
- 폴더 전체를 그대로 업로드 (파일 경로/이름을 바꾸지 마세요 — index.html이 다른 파일들을 상대경로로 참조합니다)
- HTTPS가 자동 적용되는 서비스를 쓰면 별도 설정 불필요

## 2. 배포 확인

- 크롬에서 배포된 주소로 접속 → 주소창 오른쪽에 "설치" 아이콘이 뜨면 PWA 설정이 정상 인식된 것
- 크롬 개발자도구 → Lighthouse 탭 → PWA 점수 확인 (80점 이상이면 다음 단계 진행 가능)

## 3. 구글플레이용 앱으로 패키징

[club-scoreboard](https://github.com/mattsunwoo-maker/club-scoreboard) 저장소와 동일한 방식으로 진행하세요:

1. [Bubblewrap CLI](https://github.com/GoogleChromeLabs/bubblewrap) 또는 [PWABuilder](https://www.pwabuilder.com)에 배포된 주소를 입력
2. 생성된 키스토어로 서명 → AAB 파일 생성
3. Bubblewrap이 알려주는 패키지명과 SHA256 지문을 `.well-known/assetlinks.json`에 채워 넣고 다시 배포
4. Google Play Console에 AAB 업로드 후 심사 제출
