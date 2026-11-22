# 해가빛 캠핑장 실시간 자리 현황

충남 서천 **해가빛 캠핑장**(37개 사이트)의 네이버 예약 현황을 배치도 위에 겹쳐 보여 주는 웹페이지입니다.

- 배포 주소: <https://rjaksssdev.github.io/heigabich-map/>
- 네이버 예약: <https://booking.naver.com/booking/3/bizes/667875>
- 카페: <https://cafe.naver.com/heigabichcamping>

## 구성

| 경로 | 설명 |
| --- | --- |
| `index.html` | 페이지 전체 (CSS·JS 포함, 외부 라이브러리 없음) |
| `assets/map.png` | 캠핑장 배치도 원본 이미지 (1262 × 982) |
| `data/sites.json` | 37개 사이트의 배치도 위 좌표(%)·존 정보 |
| `data/status.json` | 날짜별 사이트 예약 상태 |

## 현황 갱신 방법

`data/status.json`만 바꾸면 배치도 색과 숫자가 자동으로 반영됩니다.

```json
{
  "updatedAt": "2026-11-22T16:40:00+09:00",
  "dates": [
    {
      "date": "2026-11-28",
      "label": "11/28",
      "weekday": "토",
      "status": { "sol8": "확정", "bit3": "확정", "hae1": "예약가능", "sol3": "예약불가(미판매)" }
    }
  ]
}
```

- 상태값: `예약가능` · `확정`(예약완료) · `예약불가(미판매)`
- 사이트 id: `sol1`~`sol12`, `deck1`~`deck7`(`deck1-1` 처럼 `-1` 포함), `gravel8`, `gravel8-1`, `bit1`~`bit4`, `hae1`~`hae5`
- `label`은 탭에 표시되는 글자(예: `11/28`), `weekday`는 `금`·`토`·`일`
- 상태가 빠진 사이트는 배치도에서 `예약가능`으로 보입니다.
