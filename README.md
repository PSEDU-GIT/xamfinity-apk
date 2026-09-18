# 키오스크용 apk 설치 파일

키오스크용 태블릿에서 업데이트 관리할 때 사용.

firebase Remote Config의 **current_version**이 태블릿에 설치된 버전보다 높으면, **apk_url**의 주소에서 apk를 받아 자동으로 업데이트한다.

## apk_url

```
https://github.com/PSEDU-GIT/xamfinity-apk/releases/latest/download/xamfinity.apk
```

항상 최신(Latest) 릴리스의 `xamfinity.apk`를 가리키므로 한 번 설정하면 바꿀 필요가 없다.

## 릴리스 올리기

이 저장소에 직접 올리지 않는다. 앱 저장소의 `kiosk` 브랜치에서 fastlane으로 올린다.

```bash
bundle exec fastlane android kiosk_deploy
```

- 버전마다 `xamfinity-v.<버전>` 태그(예: `xamfinity-v.1.0.41+75`)로 새 릴리스를 만들고 Latest로 지정한다
- 파일명은 항상 `xamfinity.apk`로 고정한다
- `current_version`은 새 릴리스를 올린 **뒤에** 갱신한다. 먼저 올리면 태블릿이 이전 apk를 받아 업데이트 화면에 갇힌다

자세한 절차는 앱 저장소 README의 `배포 체크리스트 → 3. 키오스크 APK 배포`를 참고한다.
