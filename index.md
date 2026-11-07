# 개인정보처리방침 게시 안내

- 운영자: **dWorks**
- 개인정보 문의 이메일: **dworks.st@gmail.com** (사용자가 공개용으로 지정)
- 앱: 옥탑 고양이 / RoofTop Cat / com.dworks.rooftopcat
- 시행일: 2026-11-07
- 현재 버전: v4.31 (code50), 실광고·GPGS·분석 SDK 미연결 상태 기준

## 파일

- 저장소 루트 `PRIVACY_POLICY.md`: GitHub에서 읽을 한국어 문서
- `docs/privacy/index.html`: Google Play 등록용으로 호스팅할 정적 웹페이지
- `docs/privacy/policy.json`: 본문의 단일 원본
- `tools/build_privacy_policy.py`: 원본에서 Markdown/HTML 생성. 운영자 확인/이메일이 빠지면 생성 차단

## GitHub Pages로 공개하기

1. GitHub 저장소 `good1100/RoofTopCat` → Settings → Pages.
2. Build and deployment의 Source를 **Deploy from a branch**로 선택.
3. Branch는 **main**, Folder는 **/docs**, Save.
4. 배포 완료 후 표시되는 실제 사이트 주소를 확인.
5. 이 구성의 예상 개인정보처리방침 URL:

   `https://good1100.github.io/RoofTopCat/privacy/`

이미 Pages를 다른 방식으로 운영 중이라면 기존 설정을 덮어쓰기 전에 확인한다. 저장소 root를 소스로 쓰는 경우 경로는 `/RoofTopCat/docs/privacy/`가 된다. 사용자 도메인이 설정돼 있으면 그 실제 주소를 사용한다. 위 예상 주소는 Pages 설정/배포 확인 없이 실제 공개 주소라고 단정하지 않는다.

Google Play에는 로그인 없이 열리는 HTML 페이지 주소를 넣는다. GitHub 편집 화면, 다운로드되는 raw/PDF 파일 경로, 로컬파일 경로를 정책URL로 쓰지 않는다. GitHub 저장소 문서는 `https://github.com/good1100/RoofTopCat/blob/main/PRIVACY_POLICY.md`에서 확인할 수 있다.

## 게시 후 할 일

- 실제 URL을 시크릿 창/모바일에서 열어 로그인·404·편집 없이 본문과 이메일이 보이는지 확인.
- Play Console 앱 콘텐츠의 개인정보처리방침 URL에 입력.
- 앱 내 설정/도움말에도 같은 링크를 추가하고 새 AAB로 제출해야 함. 현재 code50 AAB에는 이 링크가 아직 없으며 이번 문서 작업에서 앱을 재빌드하지 않음.
- 데이터 보안 답변과 실제 SDK/데이터 동작이 이 정책과 일치하는지 확인.
- 광고/GPGS/분석/서버저장을 실제로 추가하기 전에는 방침과 데이터 보안/동의/UI를 다시 갱신.
- 본문에는 실제 기기에만 저장하는 기록·재화·수집·닉네임·설정, 삭제방법, 문의 정보 처리, 아동 관련 처리, 제3자 플랫폼 구분을 포함함.

## 변경 방법

`docs/privacy/policy.json`을 고친 다음 실행:

```powershell
python tools/build_privacy_policy.py
```

생성된 두 문서를 함께 커밋한다. 공개용 문서에는 이메일 누락·가짜 연락처·미확정 플레이스홀더를 두지 않는다. 게시 전 최종 앱 동작과 운영자가 실제 지킬 처리 절차를 확인한다.

공식 기준: [Google Play 사용자 데이터 정책](https://support.google.com/googleplay/android-developer/answer/10144311?hl=en), [심사 준비/방침 URL 요구사항](https://support.google.com/googleplay/android-developer/answer/9859455?hl=en).
