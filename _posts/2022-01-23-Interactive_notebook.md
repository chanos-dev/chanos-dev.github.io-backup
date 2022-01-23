---
layout: post
title:  ".NET Interactive Notebooks (.NET 5 SDK)"
date:   2022-01-23
excerpt: ".NET Interactive Notebooks (.NET 5 SDK)"
tag: 
- .NET
- .NET 5
- Interactive Notebooks
comments: true
---

## <center>.NET Interactive Notebooks</center> 

>[Interactive Notebook Source](https://github.com/chanos-dev/blogcode/tree/master/22-0123){:target="_blank"}

---

안녕하세요. <b>chanos</b>입니다. 😉

오늘은 .NET Interactive NoteBooks에 대해 소개해 드리려 합니다.

.NET Interactive NoteBooks는 Visual Studio Code에서 주피터 노트북 처럼 소스를 코드 블럭 형태로 실행을 할 수 있는 Microsoft의 프로젝트 Tool 입니다.

보통 C#에서 간단한 코드를 작성하여도 테스트를 하기 위해 컴파일을 거쳐 결과를 확인하였는데 .NET Interactive NoteBooks를 사용하면 작성한 코드를 바로 실행하여 결과를 확인할 수 있습니다.

마치 인터프리터 언어의 python 처럼요.

.NET Interactive NoteBooks를 사용하기 위해서는 다음과 같은 파일이 설치되어 있어야 합니다.
> 설치 URL

- [Visual Studio Code](https://code.visualstudio.com/){:target="_blank"}
- [.NET SDK](https://dotnet.microsoft.com/en-us/download/visual-studio-sdks){:target="_blank"}

현재 .NET Interactive NoteBooks의 버전(1.0.260601)은 .NET 6 SDK 설치를 해야하지만 이 문서에서는 .NET 5 기준으로 설치를 진행하겠습니다. 

Visual Studio Code(이하 vsc)의 확장 프로그램에서 .NET Interactive Notebooks을 검색하면 바로 최상단에 확장 프로그램이 검색됩니다.

<a href="{{site.url}}/images/posts/2022-01-23/vsc_plugin.png"><img src= "{{site.url}}/images/posts/2022-01-23/vsc_plugin.png" alt="vsc_plugin"></a>

처음 설치를 진행하면 가장 최신 버전으로 설치가 되는데 최신 버전은 .NET 6가 필수로 설치되어 있어야합니다.

그렇기 때문에 .NET 5를 지원하는 버전을 설치를 진행해야하는데 다음과 같이 제거 버튼에서 다른 버전 설치를 통해 <b>`1.0.255902`</b> 버전을 설치하면 됩니다.

.NET Interactive Gibhub repo의 release 버전 히스토리를 확인하면 <b>`v.1.0.255904>=`</b>부터 .NET 6 SDK를 사용하기 때문입니다.

<a href="{{site.url}}/images/posts/2022-01-23/other_version.png"><img src= "{{site.url}}/images/posts/2022-01-23/other_version.png" alt="other_version"></a>

설치가 완료되면 이제 .NET Interactive Notebooks을 사용할 수 있게됩니다.

기본적으로 주피터 노트북을 기반을하고 있기 때문에 `.ipynb` 확장자와 .NET Interactive에서만 사용되는 `.dib` 확장자, 총 2가지를 제공합니다.

.NET Interactive Notebooks을 만드는 방법은 `Ctrl` + `Shift` + `P`를 이용하여 생성할 수 있습니다.

<a href="{{site.url}}/images/posts/2022-01-23/new_notebook.png"><img src= "{{site.url}}/images/posts/2022-01-23/new_notebook.png" alt="new_notebook"></a>

<details>
<summary>👉 (클릭!) 명령 '.NET Interactive: Create new blank notebook'에서 오류(command 'dotnet-interactive.newNotebook' not found)가 발생했습니다.</summary> 
<div markdown="1">
---
dotnet-interactive가 설치되어있지 않아 발생하는 에러입니다.

[dotnet-interactive](https://www.nuget.org/packages/Microsoft.dotnet-interactive/1.0.255902){:target="_blank"} 사이트로 이동하여 `.NET CLI(Glocal)` 탭에 있는 명령어를 로컬 CLI 창에서 실행하여 설치하면 에러가 나지 않을겁니다.!

---
</div>
</details>
<br>

확장자 및 언어에 맞게 선택 후 생성을 하면 주피터 노트북에서 봤었던 UI창이 생성되게 됩니다.
- 이 문서는 .dib / C# 기준으로 작성했습니다.

<a href="{{site.url}}/images/posts/2022-01-23/notebook.png"><img src= "{{site.url}}/images/posts/2022-01-23/notebook.png" alt="notebook"></a>

위와 같이 마크다운 또는 코드를 작성하여 바로 실행을 해볼 수 있고 `Ctrl` + `Alt` + `Enter` 입력 시 해당 블럭이 실행되게 됩니다.

---
이렇게 vsc에서 .NET Interactive Notebook을 사용하는 법을 알아보았습니다.

사용결과 간단한 코드 테스트 및 교육, 발표 등에 사용하면 효율적일 것 같습니다.

Notebook 공유 또한 생성한 파일(.dib)만 공유하면 vsc에서 load하여 바로 실행할 수 있기 때문에 앞으로 블로그 소스 작성 시 애용할 것 같습니다. 😎


글에 이상한 부분이나 문제가 있는 경우 [이슈](https://github.com/chanos-dev/chanos-dev.github.io/issues){:target="_blank"} 또는 <a href="mailto:{{site.email}}">메일</a>을 남겨주시면 감사하겠습니다.

---

## Reference

[.NET Interative](https://github.com/dotnet/interactive#notebooks-with-net){:target="_blank"}

[.NET Interactive 소개](https://forum.dotnetdev.kr/t/net-interactive/928){:target="_blank"}