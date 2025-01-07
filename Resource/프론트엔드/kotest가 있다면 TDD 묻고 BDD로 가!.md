```table-of-contents
title: 
style: nestedList # TOC style (nestedList|nestedOrderedList|inlineFirstLevel)
minLevel: 0 # Include headings from the specified level
maxLevel: 0 # Include headings up to the specified level
includeLinks: true # Make headings clickable
debugInConsole: false # Print debug info in Obsidian console
```

[if(kakao)의 영상](https://tv.kakao.com/channel/3693125/cliplink/414004682)을 보고 정리한 글 입니다.
## TDD/ BDD 란?

### test driven development
1. 테스트 작성
2. 테스트 
3. 코드 작성
3번에서 문제 발생 시 다시 2번으로, 2번에서 다시 3번으로 반복

테스트 케이스 우선 그 다음 코드 작성

### TDD의 장점
모듈의 크기가 작아질수록 역할도 작아진다. 책임도 작아진다. 테스트하기 쉽다.
모듈 크기를 작게 만드는 것을 유도하고 모듈간의 결합도를 낮춘다.



### behavior driven development
TDD의 장점을 모두 알고 있지만 리소스 관리, 일정, 테스트 코드 작성의 어려움에 의해 도입을 꺼려한다. 
이걸 보완하기 위해 BDD가 나오게 되었다. 
- TDD에서 파생된 개발 방법론
- 개발자와 비개발자간의 협업 과정을 녹여낸 방법
- 사용자의 행위를 작성하고 결과 검증을 진행
- BDD로 테스트 코드를 작성함에 따라 설계 역시 행위의 중심이 되는 도메인 기반 설계가 됨
Given : 주어진 환경
When : 실제 사용자의 행위
Then : 그 행위의 기대결과

## TDD와 BDD의 차이
TDD는 테스트 할 모듈의 기능을 확인
BDD는 시나리오 주체를 기준으로 한 행위를 확인

## kotest를 쓰자

## mockk를 쓰자
## Tests Succeed