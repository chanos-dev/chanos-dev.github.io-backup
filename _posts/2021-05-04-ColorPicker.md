---
layout: post
title:  "VisualStudio ColorPicker"
date:   2021-05-04
description: "VisualStudio ColorPicker"
tag: 
- Visual Studio
- Color Picker
comments: true
---

## <center> VisualStudio ColorPicker </center>    

---

Visual Studio의 Source Editor에서 Color를 사용할 때 작성한 Color가 어떤 색상인지 에디터에서 바로 육안으로 확인이 불가능하다.

e.g)
```c#
var color = Color.Red;
```

이를 위해 Visual Studio MarketPlace에서 Color Picker라는 확장 프로그램을 지원하는데 Visual Studio에 적용이 가능하다.

[MS Color Picker](https://marketplace.visualstudio.com/items?itemName=ShemeerNS.ColorPicker&ssr=false#overview){:target="_blank"}

해당 사이트에서 다운로드를하면 VSColorPicker.vsix를 다운받는다.

Visual Studio를 종료한 다음 인스톨을 진행하면 도구에서 Color Picker을 확인할 수 있다.

<a href="{{ site.url }}/images/posts/2021-05-04/option1.png"><img src="{{ site.url }}/images/posts/2021-05-04/option1.png" alt="option1"></a> 

Color Picker가 있으면 정상적으로 설치된 것이다. 설치를 하면 기본적으로 Color Highlight의 확장자는 다음과 같다

```
".css", ".scss", ".less", ".asp", ".aspx", ".htm", ".html", ".cshtml", ".vbhtml", ".xaml" 
```

우리는 .cs 파일에 적용을 해야하기 떄문에 Color Picker 옵션으로 가서 .cs 확장자를 추가 해야한다.

- 도구 -> 옵션 -> Color Picker -> cs 확장자 Add

<a href="{{ site.url }}/images/posts/2021-05-04/option2.png"><img src="{{ site.url }}/images/posts/2021-05-04/option2.png" alt="option2"></a> 

- 결과 Before

<a href="{{ site.url }}/images/posts/2021-05-04/before.png"><img src="{{ site.url }}/images/posts/2021-05-04/before.png" alt="before"></a> 

- 결과 After

<a href="{{ site.url }}/images/posts/2021-05-04/after.png"><img src="{{ site.url }}/images/posts/2021-05-04/after.png" alt="after"></a> 

### 단점

<a href="{{ site.url }}/images/posts/2021-05-04/badpoint.png"><img src="{{ site.url }}/images/posts/2021-05-04/badpoint.png" alt="badpoint"></a> 

- 일반 문자열에서도 적용이 된다.. 😂 .css파일이나 .html 때문인 것 같다. 😭 후에 해결 방안을 모색해봐야겠다.

---