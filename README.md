# alcohol-json-library

먹었던 술의 이런저런것들을 json으로 정리하는 곳  
Made by 머성

## 술의 종류

술의 대분류를 파일명으로 정한다. (술종류.json)

### 대분류

* soju - 소주
* beer - 맥주
* makgeolli - 막걸리
* yakju - 약주, 법주
* cheongju - 청주, 사케
* whisky - 위스키
* non-whisky - 보드카, 진, 럼, 데낄라 등등
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
            "alcDegree": (float 술의 도수),
            "alcMade": (string 술을 만든 양조장 또는 사람),
            "alcWonPrice": (int 최근에 산 원화 가격 / 책정불가시 -1),
            "alcImage": (string 술의 이미지 주소인데 가능한지 모름),
            "private":{ (평가들의 평균값을 가져와서 저장해두는 곳)
                "score": (int 적당한 점수 / max min 없음),
                "taste": [(int 단, 짠, 신, 맵, 감칠)],
                "again": (bool 다시 마실지)
            }
        },
        ...
    ]
}
```

술의 소분류는  
(classification) + (category) 시 자연스럽게 만든다.

    예시) "생" + "막걸리" -> "생 막걸리"

자세한 정보는 schema.json 참조

## 양조장

brewery.json에는 양조장에 대한 정보를 담는다.