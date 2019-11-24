#참고 사이트 http://datamining.dongguk.ac.kr/lectures/bigdata/_book/section-33.html
library(rvest)

##네이버뉴스에서 리버풀+영입 검색함으로써 클럽 리버풀과 관련된 이적시장 정보 크롤링
n_news <- lapply(1:30, function(page){
  url <- paste0("https://search.naver.com/search.naver?&where=news&query=%EB%A6%AC%EB%B2%84%ED%92%80%2B%EC%98%81%EC%9E%85&sm=tab_pge&sort=0&photo=0&field=0&reporter_article=&pd=3&ds=2019.09.01&de=2019.11.24&docid=&nso=so:r,p:from20190901to20191124,a:all&mynews=0&cluster_rank=436&start=1&refresh_start=", page,"&refresh_start=0")
  nr_table  <- read_html(url)
  title <- html_nodes(nr_table, xpath='//*[@class="type01"]/li/dl/dt/a')
  title <- html_text(title)
  sources <- html_nodes(nr_table, xpath='//*[@class="type01"]/li/dl/dd[1]/span[1]')
  sources <- html_text(sources)
  contents <- html_nodes(nr_table, xpath='//*[@class="type01"]/li/dl/dd[2]')
  contents <- html_text(contents)
  data.frame(title, sources, contents)
})
n_news <- do.call(rbind, n_news)
n_news

#문장부호는 빼준다.
contents <- gsub("[[:punct:]]", " ", n_news$contents)

#단어별로 정리하기 위한 패키지 KoNLP 사용
library(KoNLP)
#library(NIADic) # not used
useNIADic()

out1 <- lapply(contents, extractNoun)
out1[1:2]

new_term <- c("손흥민", "백업", "산초", "베르너", "하베르츠",
              "프리미어리그", "이적시장")
new_dic <- data.frame(new_term , "ncn")
buildDictionary(ext_dic = c('sejong', 'woorimalsam', 'insighter'),user_dic = new_dic)
#                , category_dic_nms=c('political'))


#out2 : list type ==> vector
out_v <- do.call(c, out2)
wt <- table(out_v)
wt <- wt[nchar(names(wt)) > 1]
sort(wt, decreasing = T)[1:30]

##wordcloud패키지를 이용해서 빈도수 그림으로 나타내기
install.packages('wordcloud')
library(wordcloud)
pdf.options(family = "Korea1deb")
pal <- brewer.pal(8,"Dark2")
wordcloud(words=names(wt), freq=wt, min.freq=5,
          random.ord
