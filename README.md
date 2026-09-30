# Fanuc Robot Communication SDK for LabVIEW

<p align="center">
    <img width="100%" alt="Fanuc LabVIEW Library" src="https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/banner.png" >
</p>

[![LabVIEW](https://img.shields.io/badge/LabVIEW-2010_to_2024-yellow)](#compatibility)
[![License](https://img.shields.io/badge/license-commercial-blue)](https://underautomation.com/fanuc/eula)

**UnderAutomation.Fanuc** for LabVIEW is a library of VIs that communicates with Fanuc robot controllers
(R-J3iB, R-30iA, R-30iB, R-50iA) and with **ROBOGUIDE**. It wraps the .NET SDK `UnderAutomation.Fanuc.dll`.
Nothing is installed on the robot. No PCDK and no Robot Interface are needed on the PC.

Use it to read and write variables and registers, run and stop programs, reset alarms, set and simulate
I/O, and read the position, the I/O states and the safety status of the robot.

- Product page: [underautomation.com/fanuc](https://underautomation.com/fanuc)
- Documentation: [underautomation.com/fanuc/documentation](https://underautomation.com/fanuc/documentation)
- Also available for .NET: [Fanuc.NET](https://github.com/underautomation/Fanuc.NET), and for Python: [Fanuc.py](https://github.com/underautomation/Fanuc.py)

https://github.com/user-attachments/assets/cc3e3bc1-2e36-4d01-b94a-55ba77a85632

## What you can do

| Feature | Protocol | Controller option |
| --- | --- | --- |
| Run, pause, hold, abort programs, read and write variables, reset alarms, set and simulate ports | Telnet KCL | none |
| Read variable files, registers, I/O states, safety status, alarm history, current position, transfer files | FTP | none |
| Fast read and write of registers, current position | SNPX | R553 "HMI Device SNPX" on FANUC America controllers (R650 FRA), none on FANUC Ltd. controllers (R651 FRL) |
| Run, pause and abort programs, read and write variables | CGTP (web server of the controller) | none |

## Installation

Each release of this repository has one zip per LabVIEW version, from 2010 to 2024:
[releases page](https://github.com/underautomation/Fanuc.vi/releases). You can also clone this repository
and open the folder `LabVIEW_<version>` of your version.

Each folder contains:

- `UnderAutomation.Fanuc/UnderAutomation.Fanuc.lvlib`: the library of VIs, with the DLL;
- `Examples/1.Main demo.vi`: a demo application that uses every protocol;
- `UnderAutomation.Fanuc.lvproj`: the LabVIEW project that contains both.

<p align="center">
    <img height="250" src="https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/main-demo-connect-to-robot.png" >
    <img height="250" src="https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/main-demo-telnet.png" >
</p>
<p align="center">
    <img height="250" src="https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/main-demo-ftp.png" >
    <img height="250" src="https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/main-demo-snpx.png" >
</p>

<p align="center">
    <img src="https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/project-items.png" >
</p>

## Getting started

### Register the license

The library runs in trial mode for 30 days. After the trial, give your license key to
`RegisterLicense.vi`. Call it each time the application starts, before `ConnectToRobot.vi`.

![Register License](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/RegisterLicense.png)

### Connect to the robot

`ConnectToRobot.vi` connects to the robot with its IP address. Booleans enable or disable each protocol
(Telnet, FTP, SNPX). Telnet needs its password, FTP needs a user and a password. The VI returns the robot
and one reference per protocol: give them to the VIs below. `DisconnectFromRobot.vi` closes the
connection.

![Connect to robot](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/ConnectToRobot.png)

## Features

### Telnet KCL

Telnet KCL sends commands to the controller: reset the alarms, write variables, set an I/O... It needs no
option on the controller. To enable Telnet on the robot or in ROBOGUIDE, follow
[this tutorial](https://underautomation.com/fanuc/documentation/telnet-enable-on-robot).

To run a program:

- set `$RMT_MASTER = 1` and `$REMOTE_CFG.$REMOTE_TYPE = 1` (with `SetVariableValue.vi`);
- turn the switch of the teach pendant off;
- reset the alarms.

![Run](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/telnet-Run.png)

The other VIs of the `Telnet` folder:

| VI | Diagram |
| --- | --- |
| `Pause.vi` | ![Pause](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/telnet-Pause.png) |
| `Continue.vi` | ![Continue](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/telnet-Continue.png) |
| `Hold.vi` | ![Hold](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/telnet-Hold.png) |
| `Abort.vi` | ![Abort](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/telnet-Abort.png) |
| `AbortAllPrograms.vi` | ![Abort all programs](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/telnet-AbortAllPrograms.png) |
| `ClearProgram.vi` | ![Clear program](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/telnet-ClearProgram.png) |
| `GetCurrentPosition.vi` | ![Get current position](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/telnet-GetCurrentPosition.png) |
| `GetVariableValue.vi` | ![Get variable value](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/telnet-GetVariableValue.png) |
| `SetVariableValue.vi` | ![Set variable value](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/telnet-SetVariableValue.png) |
| `ClearVariables.vi` | ![Clear variables](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/telnet-ClearVariables.png) |
| `ResetAlarms.vi` | ![Reset alarms](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/telnet-ResetAlarms.png) |
| `SetPort.vi` | ![Set port](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/telnet-SetPort.png) |
| `Simulate.vi` | ![Simulate](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/telnet-Simulate.png) |
| `Unsimulate.vi` | ![Unsimulate](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/telnet-Unsimulate.png) |
| `UnsimulateAll.vi` | ![Unsimulate all](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/telnet-UnsimulateAll.png) |
| `TelnetIsConnected.vi` | ![Telnet is connected](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/telnet-TelnetIsConnected.png) |

`GetTaskInfo.vi` reads the state of a task.

### FTP

FTP gives access to the files of the controller, and reads and decodes the variable files (`.va`) and the
diagnostic files (`.dg`).

| VI | Diagram |
| --- | --- |
| `GetFtpCurrentPosition.vi` | ![Get current position](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/ftp-GetCurrentPosition.png) |
| `GetIoState.vi` | ![Get IO states](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/ftp-GetIOStates.png) |
| `GetSafetyStatus.vi` | ![Get safety status](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/ftp-GetSafetyStatus.png) |
| `GetAllErrorsList.vi` | ![Get all errors list](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/ftp-GetAllErrorsList.png) |
| Numeric registers (`KnownVariableFiles`) | ![Get numeric registers](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/ftp-GetNumericRegisters.png) |
| Position registers (`KnownVariableFiles`) | ![Get position registers](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/ftp-GetPositionRegisters.png) |
| String registers (`KnownVariableFiles`) | ![Get string registers](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/ftp-GetStringRegisters.png) |

Front panel of the I/O states:

![Get IO states front](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/ftp-GetIOStates-front.png)

`GetAllVariables.vi`, `GetVariableFiles.vi` and `GetVariableFromFile.vi` read the variables, and the VIs
of `DirectFileHandling` transfer files.

### SNPX

SNPX (also known as SRTP, RobotIF or Robot Interface) reads and writes data on the robot quickly. The
TCP port of the Robot IF server (60008 by default) must be reachable on the controller. In ROBOGUIDE, the
parameters are chosen in the "Advanced" tab of step 7 "Robot options" of the workcell creation wizard:
"FANUC America Corp." (R650 FRA) needs option R553 "HMI Device SNPX", "FANUC Ltd." (R651 FRL) needs no
option.

| VI | Diagram |
| --- | --- |
| `GetWorldPosition.vi` | ![Get world position](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/snpx-GetWorldPosition.png) |
| `GetUserFramePosition.vi` | ![Get user frame position](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/snpx-GetUserFramePosition.png) |
| Read a position register | ![Read position register](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/snpx-ReadPosition-Register.png) |
| Write a Cartesian position register | ![Write cartesian position register](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/snpx-WriteCartesianPositionRegister.png) |
| Write a joint position register | ![Write joints position register](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/snpx-WriteJointsPositionRegister.png) |
| Read a numeric register | ![Read numeric register](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/snpx-ReadNumericRegister.png) |
| Write a numeric register | ![Write numeric register](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/snpx-WriteNumericRegister.png) |
| Read a string register | ![Read string register](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/snpx-ReadStringRegister.png) |
| Write a string register | ![Write string register](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/snpx-WriteStringRegister.png) |
| `SnpxIsConnected.vi` | ![SNPX is connected](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/snpx-SnpxIsConnected.png) |

### CGTP (web server of the controller)

The VIs of the `Cgtp` folder use the web server of the controller: `CgtpRunProgram.vi`,
`CgtpPauseAllPrograms.vi`, `CgtpAbortTask.vi`, `CgtpReadVariableAsString.vi`,
`CgtpWriteVariableAsInteger.vi`, `CgtpWriteVariableAsReal.vi`, `CgtpWriteVariableAsString.vi` and
`CgtpIsEnabled.vi`.

## Compatibility

- **LabVIEW:** 2010 to 2024, one folder per version.
- **Operating system:** Windows.
- **Controllers:** R-J3iB, R-30iA, R-30iB, R-50iA, and ROBOGUIDE.

## License

This SDK needs a commercial license. A 30-day trial starts at the first use, no key needed.

- License agreement: [underautomation.com/fanuc/eula](https://underautomation.com/fanuc/eula) and [License.md](License.md)
- Trial, license key and source license: [underautomation.com/fanuc/documentation/license](https://underautomation.com/fanuc/documentation/license)
- Prices and quote: [underautomation.com/fanuc](https://underautomation.com/fanuc)

## Support

- Documentation: [underautomation.com/fanuc/documentation](https://underautomation.com/fanuc/documentation)
- Issues: [GitHub Issues](https://github.com/underautomation/Fanuc.vi/issues)
- Contact: [underautomation.com/contact](https://underautomation.com/contact)
