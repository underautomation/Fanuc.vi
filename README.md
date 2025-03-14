# Fanuc LabVIEW Library

<p align="center">
    <img width="100%" alt="Fanuc LabVIEW Library" src="https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/banner.png" >
</p>


[![LABView 2010](https://img.shields.io/badge/LABView-2010-yellow?logo=LabVIEW)](#)
[![LABView 2011](https://img.shields.io/badge/LABView-2011-yellow?logo=LabVIEW)](#)
[![LABView 2012](https://img.shields.io/badge/LABView-2012-yellow?logo=LabVIEW)](#)
[![LABView 2013](https://img.shields.io/badge/LABView-2013-yellow?logo=LabVIEW)](#)
[![LABView 2014](https://img.shields.io/badge/LABView-2014-yellow?logo=LabVIEW)](#)
[![LABView 2015](https://img.shields.io/badge/LABView-2015-yellow?logo=LabVIEW)](#)
[![LABView 2016](https://img.shields.io/badge/LABView-2016-yellow?logo=LabVIEW)](#)
[![LABView 2017](https://img.shields.io/badge/LABView-2017-yellow?logo=LabVIEW)](#)
[![LABView 2018](https://img.shields.io/badge/LABView-2018-yellow?logo=LabVIEW)](#)
[![LABView 2019](https://img.shields.io/badge/LABView-2019-yellow?logo=LabVIEW)](#)
[![LABView 2020](https://img.shields.io/badge/LABView-2020-yellow?logo=LabVIEW)](#)
[![LABView 2021](https://img.shields.io/badge/LABView-2021-yellow?logo=LabVIEW)](#)
[![LABView 2022](https://img.shields.io/badge/LABView-2022-yellow?logo=LabVIEW)](#)
[![LABView 2023](https://img.shields.io/badge/LABView-2023-yellow?logo=LabVIEW)](#)
[![LABView 2024](https://img.shields.io/badge/LABView-2024-yellow?logo=LabVIEW)](#)

### 🤖 Effortlessly Communicate with Fanuc robots

The **Fanuc SDK** enables seamless integration with Fanuc robots for automation, data exchange, and remote control. Ideal for industrial automation, research, and advanced robotics applications.

🔗 **More Information:** [https://underautomation.com/fanuc](https://underautomation.com/fanuc)  
🔗 Also available for **[💻 .NET (C# / VB)](https://github.com/underautomation/Fanuc.NET)** & **[🐍 Python](https://github.com/underautomation/Fanuc.py)**

---

[⭐ Star if you like it !](https://github.com/underautomation/Fanuc.vi/stargazers)

[👁️ Watch to be notified of latest updates !](https://github.com/underautomation/Fanuc.vi/watchers)

---

## 🚀 TL;DR (Too Long; Didn’t Read)

- ✔️ **PCDK / RobotIF Alternative:** No need for Fanuc’s PCDK or Robot Interface
- 📖 **Read/Write Variables:** Access and modify system variables.
- 🔄 **Register Control:** Read/write registers for positions, numbers, and strings.
- 🎬 **Program Control:** Run, abort, and reset programs.
- 🔔 **Alarm Management:** Reset alarms and view alarm history.
- ⚡ **I/O Control:** Manage ports and I/O values (UI, UO, GI, GO, etc.).
- 🔍 **State Monitoring:** Get safety status, position, diagnostics, and more.
- 📂 **File Management:** Easily manipulate files.

No additional installations or Fanuc options are required to use this SDK.

---

## 📥 Download Example Applications

Explore the **Fanuc SDK** with fully functional example applications for your LabVIEW version.

A Windows Forms application demonstrating all the features of the library.

📌 **Download:** [📥 UnderAutomation.Fanuc.lvproj](https://github.com/underautomation/Fanuc.vi/releases)

<p align="center">
    <img height="250" src="https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/main-demo-connect-to-robot.png" >
    <img height="250" src="https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/main-demo-telnet.png" >
</p>
<p align="center">
    <img height="250" src="https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/main-demo-ftp.png" >
    <img height="250" src="https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/main-demo-snpx.png" >
</p>

---
### Connect to the robot
![Connect to robot](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/telnet-ConnectToRobot.png)

### Telnet

#### Run
![Run](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/telnet-Run.png)

#### Pause
![Pause](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/telnet-Pause.png)

#### Continue
![Continue](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/telnet-Continue.png)

#### Hold
![Hold](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/telnet-Hold.png)

#### Abort
![Abort](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/telnet-Abort.png)

#### Abort all programs
![Abort all programs](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/telnet-AbortAllPrograms.png)

#### Clear program
![Clear program](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/telnet-ClearProgram.png)

#### Get current position
![Get current position](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/telnet-GetCurrentPosition.png)

#### Get variable value
![Get variable value](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/telnet-GetVariableValue.png)

#### Set variable value
![Set variable value](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/telnet-SetVariableValue.png)

#### Clear variables
![Clear variables](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/telnet-ClearVariables.png)

#### Reset alarms
![Reset alarms](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/telnet-ResetAlarms.png)

#### Set port
![Set port](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/telnet-SetPort.png)

#### Simulate
![Simulate](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/telnet-Simulate.png)

#### Unsimulate
![Unsimulate](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/telnet-Unsimulate.png)

#### Unsimulate all
![Unsimulate all](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/telnet-UnsimulateAll.png)

#### Telnet is connected
![Telnet is connected](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/telnet-TelnetIsConnected.png)

### FTP

#### Get current position
![Get current position](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/ftp-GetCurrentPosition.png)

#### Get IO states
![Get IO states](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/ftp-GetIOStates.png)

![Get IO states front](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/ftp-GetIOStates-front.png)

#### Get safety status
![Get safety status](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/ftp-GetSafetyStatus.png)

#### Get all errors list
![Get all errors list](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/ftp-GetAllErrorsList.png)

#### Get numeric registers
![Get numeric registers](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/ftp-GetNumericRegisters.png)

#### Get position registers
![Get position registers](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/ftp-GetPositionRegisters.png)

#### Get string registers
![Get string registers](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/ftp-GetStringRegisters.png)

### SNPX

#### Get world position
![Get world position](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/snpx-GetWorldPosition.png)

#### Get user frame position
![Get user frame position](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/snpx-GetUserFramePosition.png)

#### Read position register
![Read position register](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/snpx-ReadPosition-Register.png)

#### Write position register

- Write cartesian position

![Write cartesian position register](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/snpx-WriteCartesianPositionRegister.png)

- Write joints position

![Write joints position register](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/snpx-WriteJointsPositionRegister.png)

#### Read numeric register
![Read numeric register](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/snpx-ReadNumericRegister.png)

#### Write numeric register
![Write numeric register](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/snpx-WriteNumericRegister.png)

#### Read string register
![Read string register](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/snpx-ReadStringRegister.png)

#### Write string register
![Write string register](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/snpx-WriteStringRegister.png)

#### SNPX is connected
![SNPX is connected](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/snpx-SnpxIsConnected.png)

### Register License

![Register License](https://raw.githubusercontent.com/underautomation/Fanuc.vi/refs/heads/main/.github/assets/RegisterLicense.png)

---

## 🔍 Compatibility

✅ **Supported Robots:** R-J3iB, R-30iA, R-30iB  
✅ **Operating Systems:** Windows  
✅ **LabVIEW Versions:** LV2010 and newer  

---

## 📢 Contributing

We welcome contributions! Feel free to:

- Report issues via [GitHub Issues](https://github.com/underautomation/Fanuc.vi/issues)
- Submit pull requests with improvements
- Share feedback & feature requests

---

## 📜 License

**⚠️ This SDK requires a commercial license.**  
🔗 Learn more: [UnderAutomation Licensing](https://underautomation.com/fanuc/eula)

---

## 📬 Need Help?

If you have any questions or need support:

- 📖 **Check the Docs**: [Documentation](https://underautomation.com/fanuc/documentation)
- 📩 **Contact Us**: [Support](https://underautomation.com/contact)
