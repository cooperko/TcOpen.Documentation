## Architecture of TcOpen

1. [TcoCore](TcOpenFramework/TcoCore/Introduction.md)

## Getting started

1. [Get started using TcOpen libraries](TcOpenFramework/howtos/How_to_include_tcopen_in_a_project/article.md)

1. [Get started using TcOpen libraries with Inxton](TcOpenFramework/howtos/How_to_get_started_using_tcopen_libraries/article.md)

1. [How to write a sequence](TcOpenFramework/howtos/How_to_write_a_sequence/article.md)

1. [TcOpen101 YouTube channel](https://www.youtube.com/watch?v=X-w73HMjw4g&list=PL-0IxLiTmB6IMKKtGn5bDb9e35CSZZaB7)


## Features

- *main* is released to production (x = implemented)
- *dev* is in current development branch (x = implemented)
- *IVF* feature requires inxton vortex framework to operate (x = implemented)
- *WPF* feature has an UI control for WPF platform (requires IVF) (x = implemented)
- *Blazor* feature has an UI control for Blazor platform (requires IVF) (x = implemented)

### TcoCore

| main | dev | PLC Class                                               | Description                                                                        | IVF | WPF | Blazor |
|------|-----|---------------------------------------------------------|------------------------------------------------------------------------------------|-----|-----|--------|
|      | x   | TcoRtc                                                  | Single source of **real time clock** for the application                           |     |     |        |
|      | x   | [TcoContext](TcOpenFramework/TcoCore/TcoContext.md)     | Provides **encapsulation** for coherent unit of control                            |     |     |        |
|      | x   | [TcoComponent](TcOpenFramework/TcoCore/TcoComponent.md) | Base class from which all components should derive                                 |     |     |        |
|      | x   | [TcoObject](TcOpenFramework/TcoCore/TcoObject.md)       | Base class from which all objects (FBs) in the framework should derive             |     |     |        |
|      | x   | [TcoMessenger](TcOpenFramework/TcoCore/TcoMessenger.md) | Static **messaging mechanism**; Messages can be read from higher level application |     | x   |        |
|      | x   | [TcoLogger](TcOpenFramework/TcoCore/TcoLogger.md)       | **Logs messages** from the PLC program.                                            |     |     |        |
|      | x   | [TcoTask](TcOpenFramework/TcoCore/TcoTask.md)           | Task coordinator for synch and asynch run of arbitary code.                        |     | x   | x      |
|      | x   | TcoToggleTask                                           | Task coordinator for switching between two branches of logic.                      |     | x   | x      |
|      | x   | TcoRemoteTask                                           | Task coordinator for executing arbitrary code in .net evironment.                  | x   | x   | x      |
|      | x   | TcoMomentaryTask                                        | Task coordinator for executing arbitrary logic while a codition is met.            |     |     |        |
|      | x   | [TcoState](TcOpenFramework/TcoCore/TcoState.md)         | Basic state controller enhances the ST language (IF,CASE, ELSIF) coordination      |     |     |        |
|      | x   | [TcoSequencer](TcOpenFramework/TcoCore/TcoSequencer.md) | Advanced sequencing coordination primitive for step-by-step operations.            |     | x   | x      |


### TcOpen Inxton application specific

| main | dev | Package                           | Description                                                                                   | IVF | WPF | Blazor |
|------|-----|-----------------------------------|-----------------------------------------------------------------------------------------------|-----|-----|--------|
|      | x   | [Inxton.Vortex.Package.Core](https://www.nuget.org/packages/Inxton.Package.Vortex.Core/)        | Compiler and communication libraries                                                          | x   | x   |        |
|      | x   | [Inxton.Vortex.Package.Essentials](https://www.nuget.org/packages/Inxton.Package.Vortex.Essentials/)  | Automated UI generation WPF                                                                   | x   | x   |        |
|      | x   | [Inxton.Vortex.Blazor-experimental](https://www.nuget.org/packages/Inxton.Vortex.Presentation.Controls.Blazor-experimental/) | Automated UI generation Blazor                                                                | x   |     | x      |
|      | x   | TcOpen.Inxton.Logging             | Logs user action and application events from inxton application                               | x   |     |        |
|      | x   | TcOpen.Inxton.Local.Security      | Limits user access to protected section of inxton application                                 | x   | x   | x      |
|      | x   | TcOpen.Inxton.Swift               | Experimental implementation of auto programer (creates program capturing manual mode actions) | x   | x   |        |


### TcoData

| main | dev | PLC Class           | Description                                            | IVF | WPF | Blazor |
|------|-----|---------------------|--------------------------------------------------------|-----|-----|--------|
|      | x   | TcoDataExchage      | **CRUD capabale** from PLC code                        | x   | x   |        |
|      | x   | InMemory repository | IRepository implementation for in memory storage       | x   |     |        |
|      | x   | Json repository     | IRepository implementation string object as Json files | x   |     |        |
|      | x   | MongoDb repository  | IRepository implementation for **mongodb** databases   | x   |     |        |
|      |     | RavenDb repository  | IRepository implementation for **ravendb** databases   | x   |     |        |

### TcoDrivesBeckhoff

|main| dev | PLC Class      | Description                                                              | IVF | WPF | Blazor |
|-|-----|----------------|--------------------------------------------------------------------------|-----|-----|--------|
|| x   | TcoDriveSimple | Simple implementation of motion tasks (absolute, relative, velo, jog...) |     | x   | x      |

### TcoElements

| main | dev | PLC Class | Description                                    | IVF | WPF | Blazor |
|------|-----|-----------|------------------------------------------------|-----|-----|--------|
|      | x   | TcoDi     | Simple class for managing **discrete inputs**  |     | x   | x      |
|      | x   | TcoDo     | Simple class for managing **discrete outputs** |     | x   | x      |
|      |     | TcoAi     | Simple class for managing **analogue inputs**  |     |     |        |
|      |     | TcoAo     | Simple class for managing **analogue outputs** |     |     |        |

### TcoPnematics

| main | dev | PLC Class   | Description                                       | IVF | WPF | Blazor |
|------|-----|-------------|---------------------------------------------------|-----|-----|--------|
|      | x   | TcoCylinder | Simple class for managing **pneumatic cyclinder** |     | x   | x      |
