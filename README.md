# alcohol-json-library

먹었던 술의 이런저런것들을 json으로 정리하는 곳  
Made by 머성

## 술의 종류

술의 대분류를 파일명으로 정한다. (술종류.json)

### 대분류

* soju - 소주
* beer - 맥주
* makgeolli - 막걸리
* cheongju - 청주
* sake - 사케
* whiskey - 위스키
* non-whiskey - 보드카, 진, 럼, 데낄라 등등
* liqueur - 위 둘에 해당하지 않는 리큐르
* wine - 와인

## json 작성 구조

```json
{
    "category": (string 술의 종류),
    "alcList":
    [
        {
            "classification": (string 술의 소분류),
            "alcName": (string 술 이름),
            "alcPrice": (int 최근에 산 가격 / 책정불가시 -1),
            "alcImage": (술의 이미지 주소인데 가능한지 모름),
            "alcMade": (string 술을 만든 양조장 또는 사람),
            "alcSite": (string 술의 공식 홈페이지 또는 구매처),
            "private":
            [
                {
                    "score": (int 적당한 점수 / max min 없음),
                    "taste": [(int 단, 짠, 신, 맵, 감칠)],
                    "again": (bool 다시 마실지)
                }
            ]
        },
        ...
    ]
}
```