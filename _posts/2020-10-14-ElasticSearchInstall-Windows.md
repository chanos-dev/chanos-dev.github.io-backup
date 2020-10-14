---
layout: post
title:  "[ES] 윈도우 ElasticSearch 설치"
date:   2020-10-14
excerpt: "윈도우 ES 설치"
tag: 
- ElasticSearch
- ES
comments: true
---

## <center>[ES] 윈도우 ElasticSearch 설치</center> 

--- 
오늘은 검색엔진 서비스 중 하나인 ElasticSearch를 윈도우에서 설치 해보도록 하겠다. 👍

#### 앞으로 실습 환경은 다음과 같다. ✔ 
`OS : Windows 10 Pro`      
`ES : 7.9.2`


>ElasticSearch [다운로드](https://www.elastic.co/kr/downloads/elasticsearch)

<a href="{{ site.url }}/images/posts/2020-10-14/download.png"><img src="{{ site.url }}/images/posts/2020-10-14/download.png" alt="ElasticSearch_DownloadPage"></a> 

#### - 설치 순서 -

1. `elasticsearch-7.9.2-windows-x86_64.zip` 파일 압축 풀기
<a href="{{ site.url }}/images/posts/2020-10-14/install_1.png"><img src="{{ site.url }}/images/posts/2020-10-14/install_1.png" alt="ElasticSearch_install_1"></a> 

2. `cmd -> cd 'elasticsearch folder'/bin` cmd 실행 후 directory 이동

3. `elasticsearch.bat` bin폴더 안에 있는 elasticsearch.bat파일 실행 
<a href="{{ site.url }}/images/posts/2020-10-14/install_2.png"><img src="{{ site.url }}/images/posts/2020-10-14/install_2.png" alt="ElasticSearch_install_2"></a> 

4. 다음과 같이 `started` 문구가 뜨면 ElasticSearch 서비스가 정상적으로 구동이 된것이다.
<a href="{{ site.url }}/images/posts/2020-10-14/install_3.png"><img src="{{ site.url }}/images/posts/2020-10-14/install_3.png" alt="ElasticSearch_install_3"></a> 

5. 웹 브라우저 실행 후 `localhost:9200` 접속 시 다음과 같이 뜨면 성공! 😆
<a href="{{ site.url }}/images/posts/2020-10-14/install_4.png"><img src="{{ site.url }}/images/posts/2020-10-14/install_4.png" alt="ElasticSearch_install_4"></a> 

> ##### 다음은 ElasticSearch에 대하여 알아보도록 하자.