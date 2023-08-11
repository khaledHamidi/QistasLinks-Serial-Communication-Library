# QistasLinks

The Serial Communication Library is a versatile library that provides a range of functions, properties, and events for establishing and managing serial communication connections. This library aims to simplify the process of working with serial interfaces in various applications.

## Overview

The library includes only one class caled **`Qlink`** a set of functions that allow you to control the serial connection, such as setting the baud rate, opening and closing the connection, and sending data. It also provides properties that enable you to access and modify important settings, such as the port name and buffer size.

Additionally, the library features events that can be used to handle incoming data or react to specific situations, such as the reception of valid data or junk data. These events provide flexibility in designing applications that rely on serial communication.

## Table of *Qlink class* Contents

- [QistasLinks](#qistaslinks)
  - [Overview](#overview)
  - [Table of *Qlink class* Contents](#table-of-qlink-class-contents)
    - [Methods](#methods)
    - [Properties](#properties)
    - [Events](#events)

Now, let's dive into the details of each component in the Serial Communication Library.


### Methods

|  Method                                                                                                                    |Description                                                                                                                                                           |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `class Qlink() `                                                                                                                                   | Constructor for creating an instance of the `Qlink` class. Initializes the `rate`,`port` and `linksPatterns` properties.                    |
| static `GetPorts`                                                                                                                                                                           | Gets an array of available port names on the system .                                                                                                                  |
| `GetRate()`                                                                                                                                                                          | Gets the current baud rate for the serial connection.                                                                                                                 |
| `SetRate(int value)`                                                                                                                                                                 | Sets the baud rate for the serial connection.                                                                                                                         |
| `GetPort()`                                                                                                                                                                          | Gets the current port name for the serial connection.                                                                                                                 |
| `SetPort(string value)`                                                                                                                                                              | Sets the port name for the serial connection.                                                                                                                         |
| `GetStatus()`                                                                                                                                                                        | Gets the current status of the serial connection. Returns a string indicating the connection state (open or closed), the port name, and the baud rate.                |
| `Init(Parity parity = Parity.None, int DataBit = 8, StopBits stopBits = StopBits.One, Handshake handshake = Handshake.XOnXOff, int ReadTimeout = 100000, int WriteTimeout = 100000)` | Initializes the serial connection with the specified parameters. Returns a boolean value indicating whether the initialization was successful.                        |
| `open()`                                                                                                                                                                             | Opens the serial connection. Returns a boolean value indicating whether the connection was successfully opened.                                                       |
| `isOpen()`                                                                                                                                                                           | Checks if the serial connection is open. Returns a boolean value indicating the connection status.                                                                    |
| `Close()`                                                                                                                                                                            | Closes the serial connection.                                                                                                                                         |
| `Send(string text)`                                                                                                                                                                  | Sends the specified text data over the serial connection. Returns a boolean value indicating whether the data was successfully sent.                                  |
| `SendLine(string text)`                                                                                                                                                              | Sends the specified text data followed by a new line character over the serial connection. Returns a boolean value indicating whether the data was successfully sent. |

### Properties

| Property        | Description                                                                                     |
| --------------- | ----------------------------------------------------------------------------------------------- |
| `linkInterface` | Gets or sets the `SerialPort` object that represents the serial interface connection.           |
| `rate`          | Gets or sets the baud rate for the serial connection.                                           |
| `port`          | Gets or sets the port name for the serial connection.                                          |
| `linksPatterns` | Gets or sets the list of `QLinksPattern` objects that define the patterns for data parsing.     |
| `Buffer`        | Gets or sets the buffer size for storing incoming data. The default value is 16 .              |
| `receiveMode`   | Gets or sets the receive mode for handling incoming data.                                       |
| `UseSerializer` | Gets or sets a value indicating whether serialization is enabled. The default value is `false`. |


### Events

| Event          | Description                                    |
| -------------- | ---------------------------------------------- |
| `JunkData`     | Event that occurs when junk data is received.  |
| `Received`     | Event that occurs when valid data is received. |
| `Deserialized` | Event that occurs when data is deserialized.   |