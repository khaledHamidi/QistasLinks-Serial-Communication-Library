# Basic Example

In this example, we demonstrate how to use the Serial Communication Library to establish a serial connection and retrieve the status of the connection.

First, we need to import the `QistasLinks` namespace:

```csharp
using QistasLinks;
Next, we create an instance of the Qlink class and configure its properties. In this case, we set the port name to "COM5" and the baud rate to 115200. We also specify the receive mode as UseBufferLogOnlyAvailable and set the buffer size to 30. Furthermore, we define two QLinksPattern objects to specify the patterns for data parsing.

csharp
Copy
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
After configuring the Qlink object, we initialize the serial connection using the Init() method and open the connection using the open() method.

 
link.Init();
link.open();
Finally, we retrieve the status of the connection using the GetStatus() method and print it to the console.

 
Console.WriteLine(link.GetStatus());
This example demonstrates a basic usage of the Serial Communication Library to establish a serial connection and retrieve the connection status. You can further extend and customize the functionality based on your specific requirements.

Please note that the code snippet provided assumes that you have already referenced the necessary libraries and have the required hardware setup.

Feel free to modify the text or code snippet as needed to provide more context or details about the example.```