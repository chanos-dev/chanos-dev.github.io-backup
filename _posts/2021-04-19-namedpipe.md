---
layout: post
title:  "[C#] named pipe"
date:   2021-04-19
description: "C# named pipe"
tag: 
- C#
- named pipe
comments: true
---

## <center>[C#] named pipe</center>   

>[Git Source](https://github.com/chanos-dev/blogcode/tree/master/21-0419)

---

> <b> named pipe </b> 🧷

서로 다른 두 프로세스 간 메시지나 데이터를 주고 받아야할 때 프로세스 통신을 해야한다.  
그 중 C#에서 제공하는 Namedpipe를 이용하여 통신하는 방법이다.

- `Namedpipe`
    - 이름을 가진 PIPE를 통해 프로세스 간 단방향 통신을 지원한다.
    - PIPE 이름만 알면 서로 다른 프로세스끼리 통신이 가능하다.
    - FIFO (First In First Out)구조이다.
    - read 또는 write 만 가능하다.
    - 양방향 통신을 위해서는 reae pipe, write pipe 하나 씩 만들어야 한다.

---

- NamedPipeControl
```c#
public class NamedPipeControl
{
    private const int TIMEOUT = 10000;

    private string PipeName { get; set; }

    public NamedPipeServerStream PipeServerStream { get; set; }
    public NamedPipeClientStream PipeClientStream { get; set; }

    public NamedPipeControl(string name)
    {
        PipeName = name;
    }

    public async void ServerOpen()
    {
        PipeServerStream = new NamedPipeServerStream(PipeName);

        Console.WriteLine("Wait a client");
        PipeServerStream.WaitForConnection();
        Console.WriteLine("Connected.");

        while(PipeServerStream.IsConnected)
        {
            var read = new byte[4096]; 

            await PipeServerStream.ReadAsync(read, 0, read.Length);

            var msg = Encoding.UTF8.GetString(read).TrimEnd('\0');

            Console.WriteLine(msg);
        }
    }

    public void ClientOpen()
    {
        PipeClientStream = new NamedPipeClientStream(PipeName);

        PipeClientStream.Connect(TIMEOUT);
    }

    public async void Write(string msg)
    {
        var write = Encoding.UTF8.GetBytes(msg);

        await PipeClientStream.WriteAsync(write, 0, write.Length);
        PipeClientStream.Flush();
    }
}
```

- Server
```c#
static void Main(string[] args)
{
    NamedPipeControl Server = new NamedPipeControl("chanos");

    Server.ServerOpen();

    Console.ReadLine();
}
```

- Client
```c#
static void Main(string[] args)
{
    NamedPipeControl Client = new NamedPipeControl("chanos");

    Client.ClientOpen();

    while(true)
    {
        Client.Write(Console.ReadLine());
    }
}
```

- 결과
<a href="{{ site.url }}/images/posts/2021-04-19/result.png"><img src="{{ site.url }}/images/posts/2021-04-19/result.png" alt="result"></a> 

## Reference

[NamedPipeServerStream](https://docs.microsoft.com/ko-kr/dotnet/api/system.io.pipes.namedpipeserverstream?view=net-5.0){:target="_blank"}

[NamedPipeClientStream](https://docs.microsoft.com/ko-kr/dotnet/api/system.io.pipes.namedpipeclientstream?view=net-5.0){:target="_blank"}