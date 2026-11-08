# G.H.D 본부 — 대원 명부

Grand Harmony Directorate 캐릭터 소개 사이트.

```
index.html                  ← 본부 메인 (대원 명부)
assets/ghd_logo.jpg         ← 본부 로고
assets/factions/            ← 진영 문장 (sapientia, virtus, libertas)
characters/
  kross/                    ← 대원 한 명 = 폴더 하나
    index.html              ← 크로스 엘 신청서 페이지
    assets/                 ← 크로스 전용 그림
```

## 새 캐릭터 추가하기

1. `characters/` 안에 영문 소문자 폴더를 만든다. 예: `characters/dmitri/`
2. 그 폴더에 캐릭터 페이지 `index.html`과 그림 폴더 `assets/`를 넣는다.
   - 크로스 페이지(`characters/kross/`)를 통째로 복사해서 글과 그림만 바꿔도 된다.
   - 본부로 돌아가는 링크는 `../../index.html`.
3. 카드용 그림을 `characters/폴더이름/assets/card.jpg`로 넣는다. 세로 4:5 비율(상반신)이 가장 잘 맞는다.
4. 맨 위 `index.html`을 열어 `id="roster"` 아래 `"characters": [ ... ]` 목록 끝에 한 덩어리를 추가한다.
   앞 캐릭터 `}` 뒤에 쉼표(,)를 꼭 붙인다.

```json
{
  "id": "dmitri",
  "no": "002",
  "name": "Dmitri",
  "nameKo": "드미트리",
  "faction": "sapientia",
  "sex": "남",
  "age": 0,
  "height": "000cm",
  "attribute": "속성",
  "talent": "발현 능력 이름",
  "quote": "대표 대사",
  "image": "characters/dmitri/assets/card.jpg",
  "imagePosition": "50% 0%",
  "page": "characters/dmitri/index.html",
  "joined": "2026-11-09"
}
```

- `faction`은 `sapientia`, `virtus`, `libertas` 중 하나 (`factions` 목록의 `id`).
- `joined`(입단일)이 가장 최근인 대원이 메인의 '최근 입단'에 뜬다.
- 메인의 '등록 대원' 수는 일부러 `?`로 가려 두었다.
- `imagePosition`으로 카드에 보이는 그림 위치를 조정한다. (`"50% 0%"` = 가운데 위)

## 새 진영 추가하기

1. 문장 그림을 `assets/factions/진영이름.png`로 넣는다.
2. `index.html`의 `"factions": [ ... ]` 목록에 추가한다. `color`는 카드의 표시등 색이다.

```json
{ "id": "newfaction", "name": "진영 한글 이름", "en": "Faction", "color": "#888888", "emblem": "assets/factions/newfaction.png" }
```

## GitHub Pages로 공개하기

Settings → Pages → Source: Deploy from a branch → Branch: `main` / `(root)` → Save.
몇 분 뒤 `https://계정이름.github.io/저장소이름/` 에서 열린다. 파일 이름은 대소문자를 구분한다.
