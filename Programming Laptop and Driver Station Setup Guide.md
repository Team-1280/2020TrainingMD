# Programming Environment Setup

All software utilized by the programming team is listed below, with software not distributed by robotics-related companies below. If you are a Team 1280 programmer and the current year is not listed, please yell at the Programming Lead or whomever they have delegated the task to, or failing that, message @aerottd on GitHub.
Do note that as the season progresses, patches will be released for some FRC software, namely the RoboRIO image and the WPILib  VS Code installation. For **only** the WPILib VS Code installation, it may be better to avoid updating, as uninstalling WPILib VS Code may mess with robot code on your PC (note: if you're using Git properly, this isn't an issue).
>This guide is accurate as of: `27 September 2020`

## Glossary

Some of the terms used in this guide may be confusing, so the following is a list of definitions in case you find a word you can't understand. As the guide is updated, please add new confusing terms and their definitions below.

**C-Biscuit** - Our team mascot, named after Seabiscuit, the famous racehorse.
**Markdown / Markdown file** - A fancy text file that allows formatting (e.g. bold text, italics, headers, lists, links, images). You are currently reading a markdown file.
**GNU GPL** - The "General Public License" used by GNU, the organization that distributes Linux, a massive open-source operating system that is widely used in technical applications.
**EULA** - End user license agreement. In essence, a wall of text that you are legally required to "read" and agree to. 
**Image / Imaging** - In computing, 'imaging' a disk or drive refers to putting either a 'template' or a full program onto it, and especially when that drive is to be used in a microcomputer or some other form of embedded system.
**Microcomputer** - A small device that has computing power but isn't generally large enough to be considered a computer on its own right. Depending on who you ask, a Raspberry Pi, an Arduino, and the RoboRIO (our robot's "brain") are all microcomputers.
**Embedded System** - Any form of system that is 'embedded' in hardware and is not intended to be changed by the person using the hardware. Motor controllers, parts of the PDP and VRMs, and various other small electronic parts we use have embedded systems.
**PDP / VRM** - PDP stands for Power Distribution Panel. Sends power to robot components. VRM stands for Voltage Regulator Module. Prevents the output power from the PDP from frying sensitive lower-power electronics.
**[.zip] Archive** - A "Zipped" file that is compressed, meaning its size has been reduced from the original. Virtually the only way to download a folder of items from the Internet is to put that folder into a "dot zip archive", or ".zip archive", or simply an "archive". The terms are mostly interchangeable. You'll probably get one of these every time you click a download link below.
**Toolchain** -  A collection of software items that make up a programmer's metaphorical "toolbelt" that are required to make a final product--in our case, a robot. FRC's own toolchain is part of our team's specific toolchain, which includes the items listed as "Non-FRC Software".
**API** - Application Programming Interface; a way for software to "talk" with other software or hardware, or simply a way to make that "talking" easier.
**NI** - The company formerly known as National Instruments, who produces a large amount of software, hardware, etc. for FRC teams such as ours (e.g. LabView and its various components).

## Non-FRC Software (Version Control)

Certain items of software are basically required for managing a codebase, and those items are called Git. 

Joke aside, Git is essential for properly coordinating a team of programmers (read: more than one person), and prevents annoying things like hardware faults or sleep deprivation from accidentally removing your codebase directory and causing you to lose your entire year's worth of robot code.

 - What does Git actually do?
 
Git is a version control system that allows users to push their files to a remote server. In addition to Git, our team uses GitHub (note that these are two entirely separate entities), a website that acts as a host for remote Git servers. This means that we have access to our own free remote fileserver, running its own copy of Git. In fact, you're currently reading this Markdown file on GitHub (unless it's been moved)!
The following is an example of one use case for Git:
 1. C-Biscuit creates a robot project in VS Code. C-Biscuit finishes programming, and opens the file directory containing his program. They right-click in this directory, and click `Git Bash here`, which opens up a Git command-line, initialized to that directory.
 2. Having already [configured his email and username](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup) in Git, C-Biscuit goes to www.github.com, and creates a new repository. C-Biscuit copies the Git URL listed in their new repository, and executes `$git init`, followed by `$git add .`, `$git commit -m 'Initial Commit'`, and `$git push --set-upstream origin master`.
 3. OctoCat executes `$git clone` followed by the Git URL and begins coding on C-Biscuit's codebase.

There are obviously many more uses and commands for Git; this is simply serves as a basic example.
**Roger Dudler's [Git guide](https://rogerdudler.github.io/git-guide/) is very helpful**, though it does contain some non-PG language.

### Installation

 1. Navigate to the Git SCM (Source Code Management) [downloads page](https://git-scm.com/downloads).
 2. Download the latest version, ideally 64-bit Windows Setup. All versions are back-compatible with prior versions.
 3. Once the installer has been downloaded, run it. If it asks for administrator access, grant it.
 4. Agree to the license (it's GNU GPL, which is one of the most commonly-used free software licenses).
 5. You should see an install screen that looks like this:
 
![The Git SCM component selection screen.](https://i.imgur.com/6ifAXbW.png)

You will likely find all of these boxes checked. Desktop icons are a personal choice; **make sure you have Git Bash Here enabled!** It's also recommended to select 'Check daily for Git for Windows updates' as well, but it's a personal choice.
6. Press next and select a directory, then press next again. You will arrive on this screen:

![Default Git editor select screen.](https://i.imgur.com/vvMA1Eg.png)

This option really falls down to personal choice. So long as BASH is installed as the Git Bash option, which it should be if you've followed the tutorial, you can choose almost anything. If you've installed VS Code or selected an existing install using the most recent-year tutorial, using that is recommended, but *it doesn't really matter since you will almost certainly be using VS Code to write and Git Bash to upload*. Vi and Vim are both outdated and a pain to use, but they're also very powerful. Press 'Next' when done.
7. Yet another important screen:

![The PATH environment screen.](https://i.imgur.com/qFOOuCT.png)

This one can be dangerous if you mess with it. If you're super cautious (e.g. your parents are reading this over your shoulder and red text scares them), you can go with the first option, since our team really only uses Bash, but in a hurry using `cmd` instead can be quicker. Sticking with the Recommended option, already selected above, is, well, recommended. Hit 'Next' when you've made up your mind, and **do not** take the third option.
8. You will reach a less important screen, this time for OpenSSL versus Windows Secure Channel. Whichever option is highlighted is best; if none are highlighted, select OpenSSL. Press 'Next'.
9. You will reach a screen concerning line endings. Click the first option ('Checkout Windows style . . . ') if not already selected, and hit 'Next'.
10. You will reach a screen prompting you to choose between `MinTTY` and `cmd`. Select `MinTTY` if not already selected and hit 'Next'.
11. You will reach a screen prompting you to choose `$git pull` behavior. Select 'Default' if not already selected and hit 'Next'.
12. This next one is slightly important, concerning the credential manager for Git. In order to push to GitHub from Git, you will need a credential that ensures that your GitHub account matches with your Git account, so as to prevent you from accessing other people's repositories. Select 'Git Credential Manager' if not already selected and hit 'Next'.
13. You will reach a screen concerning configuring 'Extra Options'. Leave any checked or unchecked options be, and hit 'Next' (i.e. without changing anything). On the next screen, do not enable experimental support for pseudo-consoles, and hit 'Install'. 
14. Git is now installed. If you'd like, you can check the release notes, but it's not necessary.

And that's it. A tutorial on how to use Git and GitHub from an FRC point-of-view will be coming Soon™, and will be linked right here when it's done; most likely as another Markdown file in the repository in which you are currently 
reading this.

## Non-FRC Software (Limelight Vision System & Balena Etcher)

Our team uses the Limelight 2.0 camera system to provide vision capabilities to our robot. The Limelight provides a (blindingly bright) light source and a great object detection system, and it requires little to no actual code other than mathematical formulas, thanks to mankind's greatest invention: the slider.
You will be installing the following software items:

 - [Limelight Finder](http://downloads.limelightvision.io/software/LimelightFinderSetup1_0_1.exe) (direct download)
 - [Balena Etcher](https://github.com/balena-io/etcher/releases/download/v1.5.70/balenaEtcher-Portable-1.5.70.exe) (direct download)
 - [Bonjour Printing Services](http://support.apple.com/downloads/DL999/en_US/BonjourPSSetup.exe) (yes, the name is a misnomer; direct download)
 
1. Once the above items have finished downloading, run the executable titled `LimelightFinderSetup1_0_1` (the numbers at the end may be different). If Windows blocks it from running, hit 'More Info' and then 'Run Anyways'. 
2. Bam! Just like that, no setup necessary, Limelight Finder is installed. You should also have a desktop icon; delete it if you want. The program will most likely have started as well; if so, exit out of it and continue this guide.
3. Run the executable titled `BonjourPSSetup` in your Downloads folder. Press 'Next', then "thoroughly" read and accept the EULA.
4. After pressing 'Next' again, you should be on a page with two checkboxes and an 'Install' button. It is *highly* recommended to uncheck 'Automatically update Bonjour Print Services and other Apple software', especially if you are using a non-Apple device. The desktop icon is your choice. After unchecking automatic updates (or not, if you so desire), press 'Install'. Allow the installer to make changes if prompted.
5. When prompted, press 'Finish' to exit out of the installer.
6. An executable entitled `balenaEtcher-Portable-1.5.70` (the numbers at the end may be different) should have been downloaded as well. This doesn't actually need setup; as the 'portable' in the name implies, the entire software is packaged into a single `.exe` file that you can move around. Stick it in a folder of your choice (Documents will do, but you can leave it in your Downloads folder if you really want). 

All Balena and Limelight software is now installed. You shouldn't ever actually have to run the Bonjour executable--according to the Limelight website, at least, the installer is just for allowing the Limelight Finder software to send packets to the actual hardware. In any case, you are now capable of configuring and imaging the Limelight camera.

## Non-FRC Software (Phoenix Tuner & CTRE Software)

> Note: Documentation for all CTRE software and a bunch of tips that will probably come in handy can be found at [their ReadTheDocs webpage.](https://phoenix-documentation.readthedocs.io/en/latest/index.html)

CTRE, or Cross The Road Electronics, is a company that manufactures some very important items (Motor controllers, PDP, VRMs) for operating a robot. These items need to talk to the robot and the driver station, and they need to be imaged. The software and image files to do so can be found on their [technical resources page](http://www.ctr-electronics.com/hro.html#product_tabs_technical_resources).
You will be installing the following software items:

 - [CTRE LifeBoat, Phoenix Tuner, and all drivers](https://github.com/CrossTheRoadElec/Phoenix-Releases/releases/download/v5.18.4.3/CTRE.Phoenix.Framework.v5.18.4.3.zip) (direct download)
 1. Once the `.zip` archive has finished downloading, right-click on it and press 'Extract all' to your Downloads folder, and open the resultant unzipped folder if it doesn't automatically open. Run the executable titled 'CTRE Phoenix Framework v5.18.4.3' (numbers may differ). 
 2. Windows "Smart" Screen may detect it as potentially harmful; if so, press 'More info' and then 'Run anyway' at the bottom. The installer may ask for admin permissions; press 'Allow Access' if prompted. 
 3. You will see a welcome screen. Press 'Next', and you will continue to the installation selection screen. LifeBoat and Phoenix Tuner are 'mandatory installs', and are auto-checked; **make sure to check C++/Java under RoboRIO-FRC** if it hasn't already been checked. Press 'Next'. 
 
 ![The CTRE Framework Setup Installation Selection screen.](https://i.imgur.com/OKqPr1t.png)
 
 4. Read the EULA (this one is only like a paragraph long, thank God), press 'I Agree', and then "thoroughly" read the Hero SDK agreement and hit 'I Agree'.
 5. The installer will begin automatically unpacking and installing everything. When finished, Windows Security will prompt you to install CTRE drivers; press Install, and check 'Always trust software from "Cross The Road Electronics, LLC". 
 
![The Windows Security driver installation popup.](https://i.imgur.com/OKApipu.png)

 7. You will be taken to the installation finish screen. Leave release notes checked or unchecked depending on whether or not you care, and press 'Finish'.

Congrats! You now have copies of all CTRE software. You can now image/update/(hopefully not) debug CTRE devices. Phoenix Tuner is the software item; the `.crf` files in the folder (it's most likely a shortcut) are the images for all of the devices you'll be using. You'll need a direct USB hookup to the RoboRIO to image anything.

# Yearly Software

The following sections are added yearly to keep up with FRC software toolchain releases. Please, please, *please* add new sections below as necessary.
## 2020 
You may find a list of all Java Toolchain software [here](https://docs.wpilib.org/en/stable/docs/getting-started/getting-started-frc-control-system/control-system-software.html). The following software items should be installed in addition to the Non-FRC Software mentioned above:

 - WPILib Installer (Bundled)
	 - WPILib VS Code 
	 - FRC SmartDashboard (superseded by Shuffleboard)
	 - FRC Shuffleboard
- National Instruments Package Installer (Bundled)
	- FRC RoboRIO Imaging Tool
	- FRC Driver Station
- FRC Radio Configuration Utility 

Necessary install locations linked [here](https://docs.wpilib.org/en/stable/docs/getting-started/getting-started-frc-control-system/offline-installation-preparations.html):

 - [FRC Radio Configuration Utility](https://firstfrc.blob.core.windows.net/frc2020/Radio/FRC_Radio_Configuration_20_0_0.zip) (direct download link)
- [FRC Game Tools](https://www.ni.com/en-us/support/downloads/drivers/download.frc-game-tools.html#333285) 
- [WPILib Installer](https://github.com/wpilibsuite/allwpilib/releases/download/v2020.3.2/WPILibInstaller_Windows64-2020.3.2.zip) (direct download link)
>Note that the WPILib installer is slightly larger than 1 GB and will take a while to install. As of 9/18/2020, the most recent WPILib installer version is `2020.3.2`, which can also be found by scrolling down to Assets on the [release post](https://github.com/wpilibsuite/allwpilib/releases).

Once you've downloaded all three packages linked above, do the following:

 1. Once the WPILib Installer `.zip` file finishes downloading, right click on it and hit `Extract All` to your  downloads folder.
 2. Once the WPILib Installer is unzipped, open the regular folder of the same name now in your downloads folder and run the single executable inside (yes, that one file is over a gigabyte in size).
 3. You will be prompted with a window asking you if you want to install for all users, or just the current user. Select `All Users` and grant the installer administrator access.
 4. At this point, you will reach a screen that looks like this: 
 
![The WPILib installer main dialogue. If this image has broken, you are looking at a window with seven checkboxes, and a prompt at the bottom reading 'Execute Install'.](https://i.imgur.com/e3QPFKf.png)

 This tutorial will assume you do NOT have an existing VS Code install. Press 'Select/Download VS Code' and then 'Download'. The previously grayed-out boxes shown in the last image should now be checked. Press 'Execute Install' and wait for the installation to finish. 
 5. There should now be a pop-up reading `Finished! Use Desktop Icon to Open VS Code`. Press OK.
 6.  The NI Package Manager should have finished downloading. Run it, and you will be greeted with an End User License Agreement. Accept it after "thoroughly" reading it.
 7. You are now on the `Review` tab. You may be prompted to disable Windows Fast Startup; if this happens, leave the box checked and proceed. If you need to, grant the executable administrator access.
 8. The package manager will now show 'Install' above 'NI Package Manager'. Press 'Next' and let it install. This will probably take a good while.
 9. The Package Manager may prompt you to install the NI Certificates Installer; if prompted, check the box (or leave it checked) and hit 'Next'.
 10. The Package Manager installer will (read: should) automatically segway into the Package Manager itself, and you will be prompted to "read" and accept the EULA(s) for the FRC Game Tools.  "Read" and accept them, and proceed onwards.
 11. You should now have reached a screen that looks like this:
 
![FRC Game Tools](https://i.imgur.com/u0ypavL.png)

Ensure that FRC Game Tools, the NI License Manager, and (if you checked it on Step 9) the NI Certificates Installer are all present, at the very least, and then proceed by pressing 'Next'.
12. The items listed in the last screen should now be installing. Wait for completion.
13.  Another window will pop up before the install completes called 'NI Licensing Wizard'. To continue, create or log in with a National Instruments account. 
14. Once prompted, you will have to enter in serial codes for yet-to-be-activated products, most likely something related to the NI Vision package. You should have been provided with the serial number by either the Programming Lead, Team Captain, or Head Mentor (ask in that order). Enter the serial code and proceed to activate your products.
Note: If you don't have the serial number, you can finish the installation *without* activating the product. Once you do have the key, open up 'NI License Manager' and you can input the serial code from there by clicking 'Activate Product'. In either case, the FRC Game Tools have been installed, and you now have all the NI products required.
15. By this point, you have installed VS Code, which you will use to program and debug robot code, and all of the FRC Game Tools, which will allow you to operate the robot.
16. The Radio Configuration Utility should have finished downloading; it will most likely be in a `.zip` archive titled `FRC_Radio_Configuration_Utility_20_0_0`. Extract the files and run the installer executable. Windows 10 might detect it as an "unrecognized app" and prevent it from running; if this happens, press 'More Info' and hit 'Run Anyway'.
17. Press 'Next' through all context menus: you can decide the path and whether or not you want a desktop icon, but these are all personal preference options. Hit 'Install'.
18. You will most likely be prompted with a message that reads:

![The Npcap installer prompt.](https://i.imgur.com/aAEcdiT.png)

Npcap is a service, or more specifically, an API, that allows the Radio Configuration Utility to capture packets. In other words, without Npcap, the Radio Configuration Utility cannot 'talk' to the radio. Press 'OK', followed by 'I Agree' to the EULA, and then 'Install'. *Do not check or uncheck any boxes on the 'Install' page*.
19. You should be able to now press 'Next', followed by 'Finish' to exit out of the Npcap installer, and then 'Finish' again to exit out of the FRC Radio Configuration Utility installer.

Congratulations! If you've followed all of the above directions, and you've installed the items under the 'Non-FRC Software' headers, then you are now in possession of a fully-functioning programming computer and/or drive computer. Thanks for reading!
