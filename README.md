# QistasLinks
**The perfect solution for projects that depend on serial communications**

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.8248290.svg)](https://doi.org/10.5281/zenodo.8248290) ,
[![Author: Khaled HAMIDI](https://orcid.org/sites/default/files/images/orcid_16x16.png)](https://orcid.org/0009-0004-2962-0833) [Khaled HAMIDI](https://orcid.org/0009-0004-2962-0833)



QistasLinks: C# library, make serial interface(RS232) communication easy and efficient for any project utilizing a serial connection. With its user-friendly methods and robust features, QistasLinks simplifies the process of establishing communication with microcontrollers and facilitates seamless data exchange, By integrating QistasLinks into your application, you can benefit from enhanced performance and extended capabilities, making it the ideal choice for any project relying on serial connections.


## Who can benefit from using this project
The QistasLinks project is designed for individuals and developers who are working on projects that rely on serial communication with microcontrollers, projects based on Arduino boards,PIC and AVR microcontrollers. also electronic devices that need to send and receive data. It provides a convenient and efficient solution and facilitates data exchange between microcontrollers and computers.
Tags: serial communication, C#, .NET, microcontrollers, Arduino, PIC, AVR,Patterns,commands system,structure

## Features

- Serial Communication: QistasLinks enables easy and efficient read/write operations for serial or RS232 interfaces. It provides a reliable and flexible communication channel between microcontrollers and computers.

- Data Transfer Pattern: The library offers a data transfer pattern that simplifies the process of exchanging data between microcontrollers and computers. It provides a structured approach for sending and receiving data packets.

- The QistasLinks offers support for a custom command or instruction format, allowing users to communicate with the serial devices in a structured manner. This format enables precise control and configuration of the connected devices based on specific commands issued.
Keywords: serial communication, microcontrollers, communication protocols, UART, I2C, SPI
### Customizable Data Transfer Pattern Support 

The QistasLinks library offers the flexibility for users to define their own data patterns. Instead of being restricted to a specific pattern, such as `<data...>`,`{data...}` or `data...\n` , users have the freedom to create their own custom patterns based on their project specific requirements.


###  Serialization and Deserialization Command/Instruction

The QistasLinks provides a custom command or instruction format that simplifies communication with serial devices in a structured way. This format allows you to precisely control and configure connected devices by issuing specific commands.

Let's get an example:
In this format, each command follows a consistent structure: `"<operation> <key>:<value>"`.

To illustrate how QistasLinks works, first you have to make the pattren for that structure : `"#opration# #key#:#value#"`. This format can be used as a pattern. and when data recived, its will  build a dynamic object where the command elements correspond to object properties.`obj.operation` `obj.key,` and `obj.value` that hold the respective values of the command.

By utilizing this custom command format, you can easily construct and parse commands for interacting with serial devices using the QistasLinks DLL library. It provides a flexible and intuitive way to control device behavior and configuration.

For more detailed instructions and specific command examples, please refer to the documentation and examples provided with the library.


## Installation

To get started with QistasLinks, you have two options for installation:

### Manual Installation

1. Download the QistasLinks.Dll file from the Downloads folder.
2. Add the QistasLinks DLL reference to your C# project.
3. Make sure that your project is targeting the appropriate .NET version.
4. Build your project to ensure that the QistasLinks library is properly included.

### Installation via NuGet

Alternatively, you can use the NuGet package manager to install QistasLinks by following these steps:

1. Using .NET CLI: Run the command `dotnet add package Qistas.QistasLinks --version 1.0.0`.
2. Using the Package Manager Console in Visual Studio: Run the command `NuGet\Install-Package Qistas.QistasLinks -Version 1.0.0`. Please note that this command is intended to be used within the Package Manager Console and utilizes the NuGet module's version of Install-Package.

[![Download QistasLinks-Serial-Communication-Library](https://a.fsdn.com/con/app/sf-download-button)](https://sourceforge.net/projects/qistaslinks-serial-library/files/latest/download)  
also you can download it from sourceforge.

Make sure to choose the installation method that best suits your needs.

## Usage

Use this space to show useful examples of how a project can be used. Additional screenshots, code examples and demos work well in this space. You may also link to more resources.

For more examples, please refer to the Documentation folder


## Open-Source project files 
you can find it in [Qistas> QistasLinks](https://github.com/khaledHamidi/Qistas/tree/master/QistasLinks)

## License

QistasLinks is open-source software licensed under the [MIT license](https://opensource.org/licenses/MIT).

## Support

If you encounter any issues or have any questions, please [create an issue](https://github.com/KhalidHamidi/QistasLinks/issues) on the GitHub repository.

## Acknowledgements

- QistasLinks is part of the Qistas project, which aims to provide a collection of libraries and tools for microcontroller communication and integration.

- We would like to express our gratitude to the open-source community for their contributions and support.

## Contact

For any further inquiries or information, please contact our team at [engHamidi@yahoo.com]

Thank you for using QistasLinks!
```
