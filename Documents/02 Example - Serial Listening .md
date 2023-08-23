# Serial Data Listening Example

This example demonstrates how to use the QistasLinks library to listen for serial data in C#. It showcases the process of creating a Qlink object, configuring its properties, initializing the connection, and handling received and junk data using event handlers.

## Prerequisites

To run this example, ensure that you have the following:
- MAKE sure the device (microcontroller) connected with your computer.
- QistasLinks library installed. You can find the library and installation instructions [here](https://github.com/khaledHamidi/QistasLinks).

## Getting Started

1. Add a reference to the QistasLinks library.

2. Locate the code file where you want to implement the serial data listening functionality.

3. Import the necessary namespace:
   ```csharp
 using Qistas;
 using QistasLinks;

````

4. Create a new instance of the `Qlink` class and configure its properties:

   ````csharp
   Qlink link = new Qlink
   {
       port = "Auto",
       rate = 9600,
       receiveMode = Qlink.ReceiveMode.UseBufferLogOnlyAvailable,
       Buffer = 30,
       linksPatterns = QLinksPattern.Create(
           QLinksPattern.EndsWith("\n", 1)
       )
   };
   ```

   - Set the `port` property to specify the communication port. Use `"Auto"` for automatic detection or provide the specific port name.
   - Set the `rate` property to the desired baud rate for the serial communication.
   - Adjust other properties as needed.

   ````

4. Initialize the connection:

   ````csharp
   link.Init();
   ```

   ````

5. Open the connection:

   ````csharp
   link.open();
   ```

   ````

6. Register event handlers for received and junk data:

   ````csharp
   link.Received += Link_Received;
   link.JunkData += Link_JunkData;
   ```

   ````

7. Implement the event handler for received data:

   ```csharp
   void Link_Received(string DataReceived, int patternId)
   {
       Console.WriteLine($"by applying ({patternId}) >> received: {DataReceived}");
   }
   ```

8. Implement the event handler for junk data:

   ```csharp
   void Link_JunkData(string JunkData)
   {
       Console.WriteLine("Junk: " + JunkData);
   }
   ```

9. Print the current status of the serial connection:

   ```csharp
   Console.WriteLine(link.GetStatus());
   ```

10. Run the program and observe the received and junk data in the console output.

## Customization

- Modify the Qlink properties to match your specific serial communication settings.
- Expand the event handlers (`Link_Received` and `Link_JunkData`) to perform additional actions with the received and junk data.

```
