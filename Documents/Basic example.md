### Baisc Example

The following example demonstrates the basic usage of the QistasLinks library in C#. It showcases the creation and configuration of a Qlink, which represents a communication link, along with initializing the connection and retrieving its status.

```csharp
using QistasLinks;

// Create a new Qlink object and configure its properties
Qlink link = new Qlink
{
    port = "Auto", // use you connection port or use Auto.
    rate = 9600, // rate speed defualt 9600   
};

// Initialize the connection
link.Init();
// open connect.
link.open();

Console.WriteLine(link.GetStatus())
```
// Print the current status of serial connection.
Console.WriteLine(link.GetStatus());
The code begins by importing the necessary QistasLinks namespace to access the library's classes and functionalities.

A Qlink object is created using the Qlink class constructor. The object is then configured by setting its properties:

*    `port`: Specifies the communication port to be used, and in this example, it is set to `"Auto"`.
*    `rate`: Sets the baud rate for the communication, which is set to `9600` bits per second.

Next, the `open()` method is invoked to establish the connection on the specified port.

Finally, the `Console.WriteLine()` statement is used to print the current status of the connection state using the `GetStatus()` method. The implementation of the GetStatus() method is not shown in the provided code.

Please note that a comprehensive understanding of the code's purpose and functionality may require additional context and complete knowledge of the  library.

Next example will show to to lessiting to data recived.
