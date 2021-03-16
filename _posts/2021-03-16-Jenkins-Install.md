---
layout: post
title:  "[Jenkins] Ubuntu Jenkins 설치"
date:   2021-03-16
excerpt: "Ubuntu Jenkins"
tag: 
- Ubuntu
- Jenkins 
comments: true
---

## <center>[Jenkins] Ubuntu Jenkins 설치</center>   

📌Jenkins 설치 전에 Java가 설치 되어 있어야 한다.

#### 환경 ✔ 
`Windows Hyper-V`      
`Ubuntu 18.04.3 LTS`

```shell
wget -q -O - https://pkg.jenkins.io/debian/jenkins-ci.org.key | sudo apt-key add -
sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
apt-get update
apt-get install jenkins

service jenkins start

# default port:8080
# url : localhost:8080 or IP:8080
```

<a href="{{ site.url }}/images/posts/2021-03-16/install1.png"><img src="{{ site.url }}/images/posts/2021-03-16/install1.png" alt="install1"></a> 

- 사이트에 접속하면 Password를 입력하라고 합니다.
	- sudo cat /var/lib/jenkins/secrets/initialAdminPassword
- 터미널에서 Password 확인 후 넣어주고 Continue 클릭

<a href="{{ site.url }}/images/posts/2021-03-16/install2.png"><img src="{{ site.url }}/images/posts/2021-03-16/install2.png" alt="install2"></a> 

- Install suggested plugins 클릭하여 기본 플러그인 설치 (설치 후에 추가 플러그인 설치 가능합니다.)

<a href="{{ site.url }}/images/posts/2021-03-16/install3.png"><img src="{{ site.url }}/images/posts/2021-03-16/install3.png" alt="install3"></a> 

<a href="{{ site.url }}/images/posts/2021-03-16/install4.png"><img src="{{ site.url }}/images/posts/2021-03-16/install4.png" alt="install4"></a> 

- Plugin 설치가 끝나면 계정 생성 창으로 넘어옵니다. 

<a href="{{ site.url }}/images/posts/2021-03-16/install5.png"><img src="{{ site.url }}/images/posts/2021-03-16/install5.png" alt="install5"></a> 

- 계정 생성까지 완료하게 되면 Jenkins Dashboard로 넘어가게 됩니다.