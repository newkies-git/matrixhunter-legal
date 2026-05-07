# MatrixHunter Legal

[MatrixHunter](https://github.com/) 모바일 앱(`com.matrixhunter.app`)의
개인정보처리방침과 같은 법적 고지 문서를 정적으로 호스팅하기 위한 저장소입니다.

## 구성

```
public/
├── index.html              # 언어 선택 랜딩
├── style.css
├── privacy/
│   ├── ko.html             # 개인정보처리방침 (한국어)
│   └── en.html             # Privacy Policy (English)
└── terms/                  # (예약) 향후 이용약관 추가용
vercel.json                 # cleanUrls + 보안 헤더
```

빌드 단계 없이 `public/`을 그대로 정적 호스팅합니다.

## 로컬 미리보기

```bash
npx serve public
# 또는
python3 -m http.server -d public 8080
```

## Vercel 배포

1. 이 저장소를 GitHub에 push
2. <https://vercel.com/new> 에서 Import
3. **Framework Preset**: `Other`
4. **Output Directory**: `public`
5. Build/Install 명령은 비워둠
6. Deploy

배포 후 URL 예시:

- 한국어: `https://<project>.vercel.app/privacy/ko`
- English: `https://<project>.vercel.app/privacy/en`

이 URL을 Google Play Console **앱 콘텐츠 → 개인정보처리방침** 필드에
등록합니다. (Apple App Store Connect의 동일 항목에도 사용 가능합니다.)

## 커스텀 도메인 (선택)

스토어 정책상 URL이 갑자기 사라지면 정책 위반으로 처리될 수 있으므로,
가능하면 커스텀 도메인을 연결해 두는 편이 안전합니다. 예: `legal.matrixhunter.app`.

## 갱신 절차

문구를 변경할 때마다 다음을 함께 갱신하세요.

1. `public/privacy/ko.html`, `public/privacy/en.html` 양쪽 본문 동기화
2. 두 파일 상단의 **최종 갱신일 / Last updated** 날짜 갱신
3. 커밋 후 push → Vercel 자동 재배포

## 연락처

문서 내 안내 이메일은 `newkies86@gmail.com`으로 설정되어 있습니다. 운영
주소를 바꾸려면 두 정책 페이지 하단의 `mailto:` 링크와 표시 텍스트를 함께
교체해 주세요.
