> #Rvest를 이용한 네이버뉴스 크롤링 : 
###### 스포츠뉴스 중 '리버풀'의 영입찌라시를 크롤링 해보았다.
---------------------------------------------------------------------------------
# 사용한 패키지
- rvest, wordcloud, KoNLP
# 소개
-  https://search.naver.com/search.naver?&where=news&query=%EB%A6%AC%EB%B2%84%ED%92%80%2B%EC%98%81%EC%9E%85&sm=tab_pge&sort=0&photo=0&field=0&reporter_article=&pd=0&ds=&de=&docid=&nso=so:r,p:all,a:all&mynews=0&cluster_rank=44&start=1&refresh_start=0 에서 크롤링 했다.
- 데이터는 약 10000개 정도 사용
- 기간은 프리미어리그가 개막한 19.09.01부터 현시점 19.11.24까지 크롤링했다.
# 분석 결과
- 최근 가장 큰 이슈인 토트넘 감독의 경질과 함께 손흥민 선수가 강하게 영입설이 돌았다.
- 아무래도 한국의 포털사이트이다보니까 다른 외국선수들의 영입설을 유의미하게 발견하지 못한점이 아쉽다.
-----------------------------
# 데이터분석(뉴스 10000개)
![Rplot](https://user-images.githubusercontent.com/57973170/69500938-2b2fcd80-0f43-11ea-9702-2ac6690782a8.png)
