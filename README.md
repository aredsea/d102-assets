# D102 Fashion — 정적 자산

카페24 쇼핑몰(d102fashion.com)의 상세페이지·기획전에서 쓰는 정적 자산 저장소입니다.

## 왜 여기에 두나

카페24 웹서버는 **동영상 확장자를 전역 차단**합니다. 실측(2026-08-11):

| 경로 | `.mp4` | `.jpg` |
|---|---|---|
| `/web/upload/…` | 403 | 404 |
| `/mov/` · `/` · `/web/` · `/assets/` | 403 | 404 |

존재하지 않는 파일도 `.mp4`면 403이고 같은 경로의 `.jpg`는 404이므로, 경로 문제가 아니라 **확장자 단위 차단**입니다.
그래서 카페24 디자인 마켓의 영상 배경 템플릿들도 영상만 외부(GitHub Pages 등)에 두고 `<video>`로 불러옵니다.

이미지는 카페24에 그대로 올립니다. **여기에는 영상만** 둡니다.

## 사용법

```html
<video autoplay muted loop playsinline preload="metadata"
       poster="https://aredsea.github.io/d102-assets/video/sm-wave-poster.jpg">
  <source src="https://aredsea.github.io/d102-assets/video/sm-wave.webm" type="video/webm">
  <source src="https://aredsea.github.io/d102-assets/video/sm-wave.mp4"  type="video/mp4">
</video>
```

## 자산

| 파일 | 내용 | 사양 |
|---|---|---|
| `video/sm-wave.*` | 2026 Summer Memories 기획전 — 파도 배경 | 1280×900 · 30fps · 6.5초 무이음 루프 |

원본: Pexels 5668619 (ROMAN ODINTSOV). Pexels 라이선스 — 상업적 사용·수정 허용, 출처 표기 불요.
끝 0.9초를 앞머리에 겹쳐(crossfade) 루프 이음매를 없앴습니다.
