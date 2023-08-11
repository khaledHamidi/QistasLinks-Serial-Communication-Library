# Basic Example Serial read

In this example, we demonstrate how to use the Serial Communication Library to establish a serial connection and retrieve the status of the connection.

```csharp
using QistasLinks;

Qlink link = new Qlink
{
    port = "COM5",
    rate = 115200,
    receiveMode = Qlink.ReceiveMode.UseBufferLogOnlyAvailable,
    Buffer = 30,
    linksPatterns = QLinksPattern.Create(
        QLinksPattern.Between("<", ">", (int)Msg.router),
        QLinksPattern.EndsWith("\n", (int)Msg.internte)
    ),
};

link.Init();
link.open();

Console.WriteLine(link.GetStatus());
```

This example demonstrates a basic usage of the Serial Communication Library to establish a serial connection and retrieve the connection status. You can further extend and customize the functionality based on your specific requirements.

Please note that the code snippet provided assumes that you have already referenced the necessary libraries and have the required hardware setup.

Feel free to
