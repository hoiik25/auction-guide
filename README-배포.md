# 배포 방법 (v2.0 — 이미지 외부 분리 이후)

## 폴더 구조 (저장소에 이렇게 둡니다)
```
auction-guide/
├── auction_guide_updated.html      (PC, 암호화 후 배포)
├── auction_guide_m_updated.html    (모바일, 암호화 후 배포)
├── img/                            ← 이미지 90개 (그대로 업로드)
│   ├── IMG_8365.jpg
│   ├── IMG_8633.jpg
│   ├── IMG_8633_thumb.jpg
│   └── ... (총 90개)
├── CHANGELOG.md
└── encrypt.html, admin.html 등 기존 파일
```

## 처음 한 번 (이미지 분리 최초 반영)
1. 이 압축 안의 `img/` 폴더를 저장소의 `auction-guide/` 아래에 통째로 넣습니다.
2. `auction_guide_updated.html` / `auction_guide_m_updated.html`을 새 버전으로 교체합니다.
3. HTML은 기존처럼 `encrypt.html`로 암호화합니다. **(이미지는 암호화하지 않습니다 — 방법 A)**
4. GitHub Desktop에서 HTML + img/ 폴더 + CHANGELOG를 함께 커밋 → Push.
   - 커밋 메시지 예: `v2.0 이미지 외부 파일 분리`
5. `?v=20260710` 캐시버스팅으로 링크 확인.

## 앞으로 (이미지 추가 시)
- 새 이미지는 `img/` 폴더에 파일로 추가하고, HTML에서 `img/파일명`으로 참조합니다.
- 안 바뀐 이미지는 다시 안 올라가므로 저장소가 가볍게 유지됩니다.
- 매번: HTML 수정 → CHANGELOG 한 줄 → HTML+CHANGELOG(+새 img) 함께 커밋·푸시.

## 주의
- 이미지는 이제 `hoiik25.github.io/auction-guide/img/파일명` 으로 **누구나 접근 가능**합니다(방법 A 선택). 글자 내용은 여전히 암호화됩니다.
- HTML의 이미지 경로는 상대경로(`img/...`)라, 암호화해도 브라우저가 같은 폴더의 img/에서 정상 로드합니다.
