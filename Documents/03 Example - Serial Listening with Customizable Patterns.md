# Example 3: Serial Data Listening with Customizable Patterns

This example showcases how to use the QistasLinks library to listen for serial data in C# with customizable data transfer patterns. It provides step-by-step instructions on setting up the Qlink object, configuring its properties, handling received and junk data using event handlers, and customizing the data transfer patterns to match specific project requirements.

## Prerequisites

Before running this example, ensure that you have the following:

- A device (microcontroller) connected to your computer.
- The QistasLinks library installed. You can find the library and installation instructions [here](https://github.com/khaledHamidi/QistasLinks).

## Getting Started

1. Add a reference to the QistasLinks library in your project.
2. Locate the code file where you want to implement the serial data listening functionality.
3. Import the necessary namespace:

```csharp
   using QistasLinks;
```

Create a new instance of the Qlink class and configure its properties:

```csharp
Qlink link = new Qlink
{
    port = "Auto",
    rate = 9600,
    receiveMode = Qlink.ReceiveMode.UseBufferLogOnlyAvailable,
    Buffer = 30,
    linksPatterns = QLinksPattern.Create(
        QLinksPattern.Between("<", ">", 2),
        QLinksPattern.EndsWith("\n", 1)
    )
};
```

- Set the `port` property to specify the communication port. Use `"Auto"` for automatic detection or provide the specific port name.
- Set the `rate` property to the desired baud rate for the serial communication.
- Adjust other properties as needed.

Initialize the connection:

```csharp
link.Init();
```

Open the connection:

```csharp
link.Open();
```

Register event handlers for received and junk data:
```csharp
link.Received += Link_Received;
link.JunkData += Link_JunkData;
```

Implement the event handler for received data:

```csharp
void Link_Received(string DataReceived, int patternId)
{
    if (patternId == 1)
    {
        Console.WriteLine($"Received ID 1: {DataReceived}");
    }
    else if (patternId == 2)
    {
        Console.WriteLine($"Received ID 2: {DataReceived}");
    }
}
```

Implement the event handler for junk data:
```csharp
void Link_JunkData(string JunkData)
{
    Console.WriteLine("Junk: " + JunkData);
}
```

Print the current status of the serial connection:
```csharp
Console.WriteLine(link.GetStatus());
```   
Run the program and observe the received and junk data in the console output.

## Customization

Customize the linksPatterns variable using the QLinksPattern.Create() method to define your own data transfer patterns. Add or remove pattern methods as needed.

Understanding the QLinksPattern.Between Method
The QLinksPattern.Between() method creates a pattern that matches data enclosed between specified delimiters. In this example, the pattern `QLinksPattern.Between("<", ">", id:2)` is used.

The `<` and `>` symbols define the delimiters for the pattern.

Here's how the pattern works:

When the QistasLinks library receives serial data, it checks if the received data matches the specified pattern.
If the received data falls between the `<` and `>` symbols, the library extracts the data between the delimiters.
The extracted data is then passed to the event handler with an associated **pattern ID** (in this case, **2**).
You can handle the received data in the event handler and perform any necessary actions or processing.
For example, if the library receives the string **<Hello, World!>**, the `QLinksPattern.Between("<", ">", 2)` pattern will extract **"Hello, World!"** and pass it to the event handler along with the pattern ID of **2**. You can then handle this data accordingly in the __Link_Received__ event handler.


By using different patterns and configuring them in the _linksPatterns_ property of the _Qlink object_, you can customize the behavior of the _QistasLinks_ library to extract specific data based on your project requirementsFeel free to modify the code and customize the patterns to suit your specific project requirements. Explore the QistasLinks library documentation for more information and advanced features.
