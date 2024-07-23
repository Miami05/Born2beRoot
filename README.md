#  Born2beRoot

Born2beRoot is a 42School project designed to build foundational skills in cybersecurity. It covers Linux system administration, network security, firewall configuration, user and group management, and secure service setups.
Through hands-on tasks, students learn to identify vulnerabilities, implement security measures, and ensure system integrity.

##  Index


1.  [Download Virtual Machine💿](#1-download-virtual-machine)

2.  [Choosing The Operating System💻](#2-choosing-the-operating-system-)

3.  [Download The Operating System💻](#3-download-the-operating-system-)

4.  [Virtual Machine Installation🛠️](#4-virtual-machine-installation)

5.  [Installing Debian🌀](#5-installing-debian)

6.  [Virtual Machine Setup📡](#6-virtual-machine-setup)<br>

	6.1 [Installing Sudo and Configuring Users and Groups👤](#61-installing-sudo-and-configuring-users-and-groups)<br>

	6.2 [Installing and Configuring SSH📶](#62-installing-and-configuring-ssh)<br>

	6.3 [Installing and Configuring UFW🔥](#63-installing-and-configuring-ufw)<br>

	6.4 [Setting Up the Sudo Policies🔒](#64-setting-up-the-sudo-policies)<br>

	6.5 [Setting up a strong password policy🔑](#65-setting-up-a-strong-password-policy)<br>

	6.6 [Connecting Via SSH through Nat🗣](#66-connecting-via-ssh-through-nat)<br>

	6.7 [Connecting Via SSH through Bridged Adapter🗣](#67-connecting-via-ssh-through-bridged-adapter)<br>

7.  [Script🚨](#7-script)

	7.1 [Total result of the script🆗](#71-total-result-of-the-script)

8.  [Crontab⏰](#8-crontab)

9.  [Signature.txt📝](#9-signaturetxt)

10. [Bonus⭐](#10-bonus)

    10.1 [Manual Partition](#101-manual-partition)

	10.2 [Wordpress and Services Configuration🌐](#102-wordpress-and-services-configuration)

    10.3

11.  [Correction sheet ✅](#correction-sheet)



-  [Evaluation answers 💯](#evaluation-answers)



-  [Evaluation commands ⌨️](#evaluation-commands)


##  1. Download Virtual Machine💿

If you haven't installed VirtualBox yet, you can download it from the official [VirtualBox website](https://www.virtualbox.org).
VirtualBox is essential for setting up and running the virtual machine that will host the operating system we will be working with.

##  2. Choosing The Operating System 💻

###  Debian

####  Stability and Reliability:

- Known for its robust stability and reliability, ideal for server environments.
- Well-established release cycle with long-term support options.

####  Community Support:

- Large and active community with extensive documentation and resources.
- Suitable for both beginners and experienced users in system administration.

####  Ease of Use:

- User-friendly package management system (APT) simplifies software installation and updates.
- Comprehensive documentation aids in setup and troubleshooting.

####  Security Features:

- Strong focus on security with features like SELinux and AppArmor.
- Regular security updates and patches ensure system integrity.

####  Flexibility and Compatibility:

- Versatile for various applications including servers, desktops, and embedded systems.
- Wide compatibility with diverse hardware and software configurations.

###  Rocky Linux

####  Enterprise Focus:

- Developed as a stable and secure distribution, aiming to replace CentOS in enterprise environments.
- Follows RHEL closely, ensuring compatibility with enterprise applications.

####  Community and Support:

- Growing community particularly among former CentOS users.
- Offers enterprise-level support options through third-party vendors.

####  Compatibility with CentOS/RHEL:

- Designed to be a drop-in replacement for CentOS, maintaining compatibility with RHEL repositories and workflows.
- Suitable for organizations requiring RHEL-like features without the associated costs.

####  Security and Stability:

- Built with enterprise-grade security features like SELinux and strict adherence to stability.
- Long-term support and predictable release cycles ensure reliability for critical systems.

####  Deployment and Scalability:

- Optimized for large-scale deployments and mission-critical applications.
- Provides tools and support for seamless scalability in enterprise environments.

##  Bonus Part Consideration

If you decide to pursue the bonus part of the project, Debian provides several advantages:
-  **Stable Platform:** Debian offers a stable environment, ensuring reliability for setting up additional services such as WordPress or custom services.
-  **Availability of Packages:** With over 50,000 packages in its repository, Debian provides ample software choices for installing and configuring additional services to expand the project's scope.
-  **Community and Documentation:** The extensive Debian community and documentation make it easier to find support and guidance when setting up and managing additional services, enhancing the project's scalability and customization.

##  3. Download The Operating System 💻

###  Download Debian:

-  **Official Website:** You can download Debian from [Debian's official download page](https://www.debian.org/download).

###  Download Rocky

-  **Official Website:** You can download Rocky from [Rocky's official download page](https://rockylinux.org/download).
And choose Boot ISO

##  4. Virtual Machine Installation

1 ◦ Open Oracle VirtualBox

2 ◦ Click on the New command on the top

<img  width  ="836"  src="<img width="836"  alt="Screenshot from 2024-07-16 16-53-38"  src="https://github.com/Vikingu-del/Born2beRoot/raw/main/photos/installation/newVm.png">">

3 ◦ We must choose a name for the machine and the folder which will locate it. IMPORTANT Store the machine created inside the sgoinfre folder located in your campus server; this is important because we will run out of memory space in our session and the installation will fail. (Ask your staff if you can't find it)

<img  width="836"  alt="Screenshot from 2024-07-16 16-50-55"  src="https://imgur.com/CCfeFs7.png">


4 ◦ Now we have to set up the memory size we want to use for our VM. You are free to choose How much memory you want to use from your computer but I would suggest that 1024MB is enough for this project.

<img  width="836"  alt="Screenshot from 2024-07-16 16-51-34"  src="https://imgur.com/qf8XQhX.png">

5 ◦ Now the next prompts are asking to set up a virtual Hard disk. In the VirtualBox setup process, ensure to select 'Dynamically allocated' for storage on the physical hard disk. This option allows the virtual hard disk file to grow in size as needed, optimizing disk space usage. Avoid checking the option to pre-allocate the full size, as it may lead to unnecessary disk space allocation. One we established the recommended `12 GB` we must click on `Create`. If we are doing the bonus we might set `30 GB`.

<img  width="836"  alt="Screenshot from 2024-07-16 16-51-44"  src="https://imgur.com/M3WvvRH.png">

6 ◦ Now click Finish.

<img  width="836"  alt="Screenshot from 2024-07-16 16-51-50"  src="https://imgur.com/LOArHmm.png">

7 ◦ It might seem that we have already finish the installation , but there's still some steps to do. Click on Settings.

<img  width="836"  alt="Screenshot from 2024-07-16 16-51-50"  src="https://imgur.com/fulL3xl.png">

8 ◦ Then click on Storage.

<img  width="836"  alt="Screenshot from 2024-07-16 16-51-50"  src="https://imgur.com/j6SfLp5.png">

9 ◦ Click on the blue disk icon, then select 'Choose a disk file', and finally, select the Debian ISO file that you downloaded.

<img  width="836"  alt="Screenshot from 2024-07-16 16-51-50"  src="https://imgur.com/zJxdFTC.png">

10 ◦ After that Click OK.

<img  width="836"  alt="Screenshot from 2024-07-16 16-51-50"  src="https://imgur.com/SYnM1xP.png">

11 ◦ After completing all the steps, click the 'Start' button to launch your new virtual machine.

<img  width="836"  alt="Screenshot from 2024-07-16 16-51-50"  src="https://imgur.com/rmtkgaX.png">

12 ◦ If it show this error.

<img  width="836"  alt="Screenshot from 2024-07-16 16-51-50"  src="https://imgur.com/e0eXvOy.png">

13 ◦ Navigate to Settings, then General, and ensure that the Version is specified as Oracle Linux (64bit).

<img  width="836"  alt="Screenshot from 2024-07-16 16-51-50"  src="https://imgur.com/tDF2G2A.png">

##  5. Installing Debian🌀

-  **Hey there! Your eyesight is important. 👀 Enlarge the window for a better view:**

1 ◦ It will have the view like below. To have a larger view for your eyes, right click with your mouse, choose the option Virtual Screen 1 and scale it to 200%. After choose the install option since we will use it without Graphical Interface.

<img  width="836"  src="https://user-images.githubusercontent.com/66915274/178788620-61064b58-0c0c-4f48-815e-60b4a8eaecae.png">

2 ◦ The language selection for the machine during installation, including the default setting, is now your choice. Please choose `English` or any other preferred language.

<img  width="836"  src="https://user-images.githubusercontent.com/66915274/178789949-4fe83ac8-23b8-4f82-a034-a6d5e81d4f17.png">

3 ◦ It's time to select the country. If your is not on the present list go to `Other`.

<img  width="836"  src="https://github.com/Vikingu-del/Born2beRoot/raw/main/photos/installation/Country.png">

4 ◦ Time to select continent. In our case we will select `Europe` 🇪🇺.

<img  width="836"  src="https://github.com/Vikingu-del/Born2beRoot/raw/main/photos/installation/europe.png">

5 ◦ Now we select the country. In my case is Germany 🇩🇪

<img  width="836"  src="https://github.com/Vikingu-del/Born2beRoot/raw/main/photos/installation/Germany.png">

6 ◦ Configuring locales: I will go with United States

<img  width="836"  src="https://github.com/Vikingu-del/Born2beRoot/raw/main/photos/installation/configuringLocales.png">

7 ◦ Now it's time to select a keymap. Our keyboard uses the ANSI standard, so please choose `American English`. If you're unsure about your keyboard's standard, we highly recommend asking your staff.

<img  width="836"  src="https://github.com/Vikingu-del/Born2beRoot/raw/main/photos/installation/Keyboard.png">

8 ◦ First, we need to set the `Hostname`, which should be your login followed by '42', as required by the subject
Then, press the Tab key and select Continue.

<img  width="836"  src="https://imgur.com/lVj1CF0.png">

9 ◦ For the `Domain Name`, leave this section empty, as the subject does not specify anything.
Then, press the Tab key and select Continue

<img  width="836"  src="https://imgur.com/pl6Z0bq.png">

10 ◦ We need to set a password for the root user. It is important to write it down or take a photo, as we will need it later. To verify the password, press the `Down Arrow ⬇️` to the option Show Password in Clear option and press the `Space Bar` to display it. You should see something like the photo below. Then, press the Tab key and select Continue

<img  width="836"  src="https://imgur.com/GeH6nHo.png">

11 ◦ Repeat the process as you need to confirm the password we just set.

<img  width="836"  src="https://imgur.com/Q7wARyG.png">

12 ◦ Set up the username as specified in the subject, we require a new user that is not the root user, and the username must be your student login.

<img  width="836"  src="https://imgur.com/k77lb6S.png">

13 ◦ Repeat you `User Name`.

<img  width="836"  src="https://imgur.com/z5jZ6Q4.png">

14 ◦ Now we need to set the password for our new user. I'm choosing the same password as for the `Root User`.

<img  width="836"  src="https://imgur.com/xDkMipw.png">

15 ◦ We confirm the password, to see the password use the `Down Arrow ⬇️` to reveal the password and press the `Space Bar` Than press Continue with the `Tab Bar`.

<img  width="836"  src="https://imgur.com/3ksvHxJ.png">

16 ◦ Select Guied - use entire disk and set up encrypted LVM. ⚠️❗️ If you want to do the bonus select Manual and then [click here](#10-bonus) ❗️⚠️

<img  width="836"  src="https://user-images.githubusercontent.com/66915274/178795367-b82018de-edc8-47d3-8cd6-b90c5e3be2fa.png">

17 ◦ Select the disk where you want to create the partition (only one disk should be displayed).

<img  width="836"  src="https://user-images.githubusercontent.com/66915274/178796481-29ef7ebc-0518-40f0-9429-3f43316b35d3.png">

18 ◦ After choosing the disk, proceed to create the partition as described in the subject. To do this correctly, select the second option `Separate /home partition`.

<img  width="836"  src="https://imgur.com/cwY7P0j.png">

19 ◦ We choose option `Yes` so the changes will be written in the disk and so we can set the logical volume manager (LVM).

<img  width="836"  src="https://user-images.githubusercontent.com/66915274/178797258-8c34bc31-16a7-4aef-8406-cecc21fdf028.png">

20 ◦ We click on `Cancel` the erasing of the data is not required.

<img  width="836"  src="https://user-images.githubusercontent.com/66915274/178797666-78cdf892-1a83-4c68-8f85-0d5440cd4854.png">

21 ◦ Once again, select a password for encrypting the `LVM`. As mentioned earlier, you'll need to repeat this process, so it's advisable to write it down. You can use the same password as before.

<img  width="836"  src="https://imgur.com/DSWYNrL.png">

22 ◦ Repeat the password we just set.

<img  width="836"  src="https://imgur.com/VXGHUeh.png">

23 ◦In this step, we must input the required amount of volume group to use during the guided partitioning. We can enter `max` or the total available memory, which in this case is `12.4 GB`.

<img  width="836"  src="https://user-images.githubusercontent.com/66915274/178799165-c6b05fd2-86ad-45b7-a026-9ee169eda5d5.png">

24 ◦ To wrap the partitioning and write the changes in the disk we choose the option `Finish partitioning and write changes to disk`.

<img  width="836"  src="https://imgur.com/ThEB4H7.png">

25 ◦ We choose the option `Yes` and then we confirm that we do not want more changes.

<img  width="836"  src="https://imgur.com/ho1HF2V.png">

26 ◦ We select the option `No` since additional packages are not required and we don't need them.

<img  width="836"  src="https://user-images.githubusercontent.com/66915274/178801099-2dda24f5-0d46-4184-8c44-a8fe0bf46527.png">

27 ◦ We choose our Country.

<img  width="836"  src="https://imgur.com/xVZHPcR.png">

28 ◦ We choose `deb.debian.org` as is the recommended by Debian itself.

<img  width="836"  src="https://imgur.com/w7Uc3Ch.png">

29 ◦ We will left this option blank and we click on `Continue`.

<img  width="836"  src="https://user-images.githubusercontent.com/66915274/178803208-2969acae-3fa7-423e-8a3c-bb7c76eff824.png">

30 ◦ We select the option `No` as we want to remain out of the statistics.

<img  width="836"  src="https://user-images.githubusercontent.com/66915274/178803926-a4efbc70-f3e2-4e6c-9809-9152478d8237.png">

31 ◦ We will leave all software choices blank by navigating with the `Down Arrow` key and selecting with the `Space Bar`, then click `Continue`.

<img  width="836"  src="https://user-images.githubusercontent.com/66915274/178804377-e775b89e-93d4-482f-a4d0-0ef126f47719.png">

32 ◦ We select `Yes` for install [GRUB boot](https://es.wikipedia.org/wiki/GNU_GRUB) in the hard disk.

<img  width="836"  src="https://user-images.githubusercontent.com/66915274/178804771-ba16e0b7-9f06-4c5b-9451-0bfd65efd2bb.png">

33 ◦ We will choose the device `/dev/sda (ata_VBOX_HARDDISK)` for the installation for boot loader.

<img  width="836"  src="https://user-images.githubusercontent.com/66915274/178806441-f1bf3159-4e09-4c9a-9102-b3261c9000d8.png">

34 ◦ To finish the installation we click on `Continue`.

<img  width="836"  src="https://user-images.githubusercontent.com/66915274/178807102-e2a9722e-791f-48a0-ae35-b05b36a37ed2.png">

##  6. Virtual Machine Setup📡

➤ First of all, we must select `Debian GNU/Linux`.

<img  width="836"  src="https://imgur.com/gjPh3EF.png">

➤ Now, we must enter the encryption password that we previously set. In my case, it is `ldurmish42`.

<img  width="836"  src="https://imgur.com/ZoPXpI7.png">

➤ After that we must introduce the user and password that we created.

<img  width="836"  src="https://imgur.com/dbvFPQg.png">

➤In my case the user is `ldurmish` and the password is `ldurmish42`.

<img  width="836"  src="https://imgur.com/Xp3M5o3.png">

###  We have set everything ready for starting the setup of our Debian virtual machine❗️

##  6.1 Installing Sudo and Configuring Users and Groups👤

1 ◦ The installation begins by switching the user to root so we can install `sudo`. To do this, enter `su` at the bash prompt and provide the root password, which is `ldurmish42` in my case. Once logged in as root, run the command `apt install sudo` to have the package manager install the required packages for `sudo`.

<img  width="836"  src="https://imgur.com/86gUU8q.png">

2 ◦ We must reboot machine so the changes can be applied. For that purpose we will use the command `sudo reboot`

<img  width="836"  src="https://imgur.com/PFs6oEr.png">

3 ◦ Once the machine is rebooted we have to input the encryption password and the login again. To check if sudo have been installed correctly we must switch to root user and then use the command `sudo -V`; this command will show the sudo version (it will show extra info like the plugins installed).

<img  width="836"  src="https://imgur.com/cFc0sCu.png">

**OPTIONAL** ➤ In case of the output being too large we can redirect the command output to a file via `sudo -V > file.txt` . The `> file.txt` part of the command saves the output into a file named `file.txt`, replacing any existing content in that file.

<img  width="836"  src="https://imgur.com/gICBKU5.png">

Then edit the file using `nano file.txt` ,`vim` or `cat`.

<img  width="836"  src="https://imgur.com/T6QohNe.png">

Exit from `nano file.txt` using `Ctrl X`

<img  width="836"  src="https://imgur.com/qTSA49M.png">

Other option would be putting `sudo -V| more` after the command.

<img  width="836"  src="https://imgur.com/DT7ycDo.png">

4 ◦ **Now, this step is for the everyone that didn't put his user as the other user asked by the subject during the installation of the system.** Still in the root user we will create an additional user with `sudo adduser <login>`. If you had already done it will show the same message as is the image.

<img  width="836"  src="https://imgur.com/S4LsIGa.png">

5 ◦ We will create a new group called `user42`. For that we must use `sudo addgroup user42`.

<img  width="836"  src="https://imgur.com/GMR4re8.png">

6 ◦ With `sudo adduser <user> <groupname>` we can include a user to a group. We must include out user in the groups `sudo` and `user42`.

<img  width="836"  src="https://imgur.com/KGcKP8W.png">

7 ◦ Or editing the /etc/group file using `nano /etc/group` the groups `sudo` and `user42` must be present with our user.

<img  width="836"  src="https://imgur.com/sRq3jFC.png">

🤔 **Was the group created without problems?** Truth is that there is no sign of one, still we can check it using `getent group <groupname>` or we can also use `cat /etc/group` and see all groups and the users in any of them.
8 ◦ Once we are done with that we can check it using `getent group <groupname>` the groups `sudo` and `user42` must be present with our user.

<img  width="836"  src="https://imgur.com/Wis6XA2.png">

<img  width="836"  src="https://imgur.com/4gQ943a.png">

##  6.2 Installing and Configuring SSH📶

##  🧠 What is SSH❓

SSH stands for "Secure Shell." It is a protocol designed to provide a secure way to access a remote computer. Unlike older methods that weren't secure, SSH encrypts the connection between your computer and the remote computer, making it safe from eavesdropping and hacking.

###  How Does SSH Work?

SSH works using a client-server model, where:

-  **Client:** This is your computer.
-  **Server:** This is the remote computer you want to connect to.

When you use SSH to connect to the server, a secure channel is created between the client and the server, allowing you to send commands and receive data safely.

1 ◦ First thing, we write the command `su` to switch in the root and we should update the system using `sudo apt update`.

<img  width="836"  src="https://imgur.com/T3jZ3el.png">

2 ◦ Following up we will install the main tool for remote access with the SSH protocol, using Open SSH. The installation requires the package `sudo apt install openssh-server`.
When we are asked for confirmation we will write `y`, and just then the installation will proceed.

<img  width="836"  src="https://imgur.com/iPIWYjM.png">

Curious to see if the installation has been completed without problems?
You can use `sudo service ssh status` to check the status. It should show **Active** to confirm that it is running correctly.

<img  width="836"  src="https://imgur.com/4L4Aey3.png">

3 ◦ Going on, some files have been created and we need to configure them. For that we will use [Nano](https://en.wikipedia.org/wiki/GNU_Nano) or [VIM](https://en.wikipedia.org/wiki/Vim_(text_editor)) (we will need to install vim since it's not preinstalled using `sudo apt install vim`) or any other text editor.
Press y to confirm the installation.

<img  width="836"  src="https://imgur.com/gGaFmAb.png">

4 ◦ First file that we will edit will be `/etc/ssh/sshd_config`. If you are not on root you will not be able to edit the file, as you know, for switching to root we use `su`.

<img  width="836"  src="https://imgur.com/7uyBoXP.png">

5 ◦ The `#` symbol indicates that the line is commented out. We need to uncomment the lines that we'll be editing. When editing the file in `VIM`, press the `i` key to enter insert mode. You can navigate through the file using the arrow keys.

➤ #Port 22 -> Port 4242

<img  width="836"  src="https://imgur.com/q45SdVq.png">

➤ #PermitRootLogin prohibit-password -> PermitRootLogin no

<img  width="836"  src="https://imgur.com/Qf3YFD8.png">

6 ◦ To exit insert mode in `VIM`, press the `ESC` key. Then, to save your changes and quit, press `Shift` + `:` to enter command mode, type `wq`(write &quit), and press `Enter`. If you didn't make any changes, simply type `:q` and press `Enter` to quit without saving.

<img  width="836"  src="https://imgur.com/nOEMcBX.png">


7 ◦ Now with the file `/etc/ssh/ssh_config`. (not `sshd_config`)

<img  width="836"  src="https://imgur.com/cKkxpew.png">


Edit the following line:

➤ #Port 22 -> Port 4242

<img  width="836"  src="https://imgur.com/jjEx9vD.png">
To exit insert mode in `VIM`, press the `ESC` key. Then, to save your changes and quit, press `Shift` + `:` to enter command mode, type `wq`(write &quit), and press `Enter`.


8 ◦ Finally we must restart the ssh service so it can be updated. For that purpose we will use `sudo service ssh restart`.

<img  width="836"  src="https://imgur.com/ZFaw2s9.png">

9 ◦ When it is done we will check the service state with `sudo service ssh status` and confirm that everything is alright.

<img  width="836"  src="https://imgur.com/gThOP8O.png">

##  6.3 Installing and Configuring UFW🔥

🧠 **What is [UFW](https://en.wikipedia.org/wiki/Uncomplicated_Firewall)❓** It is a [firewall](https://en.wikipedia.org/wiki/Firewall_(computing)) which use the command line for setting up [iptables](https://en.wikipedia.org/wiki/Iptables) using a small number of easy commands.

1 ◦ First things first, we need to install the packages for UFW, for that we will use `sudo apt install ufw`, then when we are asked for confirmation type `y` and the installation will proceed.

<img  width="836"  src="https://imgur.com/Kfri3Cf.png">

2 ◦ When we are done with it, we want to start it using the command `sudo ufw enable` and then it have to show us the the _firewall is active._

<img  width="836"  src="https://imgur.com/cqrJggA.png">

3 ◦ Then we must allow our firewall to accept the connections that will happens in the 4242 port. What we will do is use `sudo ufw allow 4242`.

<img  width="836"  src="https://imgur.com/enh6PfU.png">

4 ◦ Lastly we will check if everything done here is correct checking the actual state of our firewall. For that we will use `sudo ufw status`. Alternatively `sudo ufw status verbose` or `sudo ufw status numbered` can be used.

<img  width="836"  src="https://imgur.com/57sQoM8.png">

## 6.4 Setting Up the Sudo Policies🔒

1 ◦ Beginning with this section, we will create a file in _/etc/sudoerd.d/_. The file will serve the purpose of storing our sudo policy. The command that we will use will be `touch /etc/sudoers.d/sudo_config`.

<img  width="836"  src="https://imgur.com/DT2aAtP.png">

2 ◦ Then we must create a directory as is asked in the subject in _/var/log/_ because each commands need to be logged, the input and output. We will use `mkdir /var/log/sudo` for our folder.

<img  width="836"  src="https://imgur.com/YPBH6Ep.png">

3 ◦ We must edit the file that we created in the first step of this section. Use any text editor, but for this guide as is in every screenshot we will use nano. Use `nano /etc/sudoers.d/sudo_config`.

<img  width="836"  src="https://imgur.com/lK1aLrX.png">

4 ◦ Once we are editing the file we must set it up with the following commands.
```sh
Defaults  passwd_tries=3
Defaults  badpass_message="Wrong password"
Defaults  logfile="/var/log/sudo/sudo_config"
Defaults  log_input, log_output
Defaults  iolog_dir="/var/log/sudo"
Defaults  requiretty
Defaults  secure_path="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/snap/bin"
```

➤ As it should be on the file.

<img  width="836"  src="https://imgur.com/KjPbhVz.png">

🤔 **What does each command❓**

-   **Password Tries**: If you enter your password incorrectly 3 times, sudo will stop trying and you'll have to start over.
-   **Custom Error Message**: Displays a personalized message for wrong passwords.
-   **Logfile**: All the commands run with sudo will be recorded in the file located at /var/log/sudo/sudo_config.
-   **Log Input/Output**: This setting helps keep track of what was typed and what the system responded when using sudo commands.
-   **Log Directory**: The logs of what you type and see when using sudo are saved in the /var/log/sudo directory.
-   **Require TTY**: Ensures `sudo` is used from a terminal.
-   **Secure Path**: Defines safe directories for `sudo` commands.

## 6.5 Setting up a strong password policy🔑

1 ◦ First step will be editing the login.defs file.

<img  width="836"  src="https://imgur.com/jq3KVHI.png">

2 ◦ Once we are done editing the file, we will set the next parameters:

➤ PASS_MAX_DAYS 99999 -> PASS_MAX_DAYS 30

➤ PASS_MIN_DAYS 0 -> PASS_MIN_DAYS 2

<img  width="836"  src="https://user-images.githubusercontent.com/66915274/179328449-32a40f67-a18d-4f29-993b-94d013cd7670.png">

PASS_MAX_DAYS: It's the max days till password expiration.

PASS_MIN_DAYS: It's the min days till password change.

PASS_WARN_AGE: It's the days till password warning.

3 ◦ For continuing the installation we must install the next packages with the following command`sudo apt install libpam-pwquality` , then we write `Y` so we can continue, we wait till it finish.

<img  width="836"  src="https://imgur.com/nxsgXMT.png">

4 ◦ Next thing we must do is is edit a file and change itś content. We will use `nano /etc/pam.d/common-password`.

<img  width="836"  src="https://imgur.com/rtYusAj.png">

5 ◦ After retry=3 we must add the following commands:
```sh
minlen=10
ucredit=-1
dcredit=-1
lcredit=-1
maxrepeat=3
reject_username
difok=7
enforce_for_root
```

➤ This is how the line must be↙️
<img  width="836"  src="https://imgur.com/9srPwvE.png">

➤ This is how the file must look ↙️

<img  width="836"  src="https://imgur.com/Bql97y1.png">

**What does each command❓**

minlen=10 ➤ The minimum characters a password must contain.

ucredit=-1 ➤ The password at least have to contain a capital letter. We must write it with a - sign, as is how it knows that's referring to minimum characters; if we put a + sign it will refer to maximum characters.

dcredit=-1 ➤ The password at least have to contain a digit.

lcredit=-1 ➤ The password at least have to contain a lowercase letter.

maxrepeat=3 ➤ The password can not have the same character repeated three continuously times.

reject_username ➤ The password can not contain the username inside itself.

difok=7 ➤ The password it have to contain at least seven different characters from the last password used.

enforce_for_root ➤ We will implement this password policy to root.

6 ◦ Now this password policy applies to new users created later or change a new password. But for the root user and login user we create at the beginning, we need to manually change the time setting of days between password change.

Use command: `sudo chage -l <username>` to check the password of root and login user.

As the picture below, the minimum, maximum days between password change are still default, because we create these two users before we create the password policy.

<img  width="836"  src="https://imgur.com/ObBpyEu.png">

We use command `sudo chage -m <time> <username>` where -m is for minimum days should be 2 days to modify the days between password change.

<img  width="836"  src="https://imgur.com/PN8JJmM.png">

We use command `sudo chage -M <time> <username>` where -M is maximum days, should be 30 days.

<img  width="836"  src="https://imgur.com/HRfCDrS.png">

Then check it again.

<img  width="836"  src="https://imgur.com/xmLO25A.png">

## 6.6 Connecting Via SSH through Nat🗣

1 ◦ If we want to connect via SSH through NAT we must close the machine and go to settings.

<img  width="836"  src="https://imgur.com/EYpBIgQ.png">

2 ◦ Once there we will click on `Network`.

<img  width="836"  src="https://imgur.com/1PkiyQx.png">

3 ◦ We check if it's attached to NAT(Network Address Translation)

<img  width="836"  src="https://imgur.com/JlSqFMS.png">

4 ◦ Click on `Advanced` so it shows more options, then we click on `Port forwarding`.

<img  width="836"  src="https://imgur.com/ZSM08jE.png">

5 ◦ Click on the emoji for adding a new rule.

<img  width="836"  src="https://imgur.com/WnFOHCq.png">

6 ◦ Lastly we will add the `2222` port to host and `4242` port to client. The IP's are not required. We will click accept so changes can be saved.

<img  width="836"  src="https://imgur.com/eUTWmtd.png">

➤ To connect via ssh from the machine to the virtual machine using and the use the command `ssh <user>@localhost -p 2222`. It will require for your password.

<img  width="836"  src="https://imgur.com/J3cktmC.png">

7 ◦ Now you are connected.

<img  width="836"  src="https://imgur.com/8JsHyhI.png">

## 6.7 Connecting Via SSH through Bridged Adapter🗣

1 ◦ If we want to connect via SSH through Bridged Adapter we must close the machine and go to settings.

<img  width="836"  src="https://imgur.com/EYpBIgQ.png">

2 ◦ Once there we will click on `Network`.

<img  width="836"  src="https://imgur.com/1PkiyQx.png">

3 ◦ Under `Adapter 1`, change the "Attached to" dropdown from `NAT` to `Bridged Adapter`.

<img  width="836"  src="https://imgur.com/JlSqFMS.png">

4 ◦ Click `OK` to save the settings and close the dialog.

<img  width="836"  src="https://imgur.com/60Z7mHm.png">

5 ◦ Boot up your virtual machine and open a terminal within the VM and run the following command to find its IP address
`ip a`

<img  width="836"  src="https://imgur.com/x4jshuA.png">

U will see the IP of your virtual machine.

6 ◦ To connect via ssh from the machine to the virtual machine using and the use the command
`ssh <username>@<vm_ip_address> -p 4242`. Which on my case is `ssh ldurmish@10.12.245.227 -p 4242`
You will be prompted to enter the password.

<img  width="836"  src="https://imgur.com/OybBTji.png">

7 ◦ Now you are connected.
<img  width="836"  src="https://imgur.com/BmK8ojy.png">

## 7. Script🚨

Going into this part, you need to take special attention to everything, as is important to learn all that is here. **Do not cheat this part!** You will be asked how the script works during the evaluation, or as the evaluator sees.

🧠 **What is a script❓** It is a sequence of commands stored in a file that when executed will do the function of each command.

### 7-1 Architecture

For the architecture of the SO to be shown, you will use the command `uname -a` ("-a" == "--all"). What this command does is print all information, except if the CPU is unknown or the platform hardware.

<img  width="836"  src="https://imgur.com/On8kR8P.png">

### 7-2 Physical Cores

For the number of fiscal cores to be shown we will use the file /proc/cpuinfo, which give us information about the CPU: its type, brand, model, performance, etc. We will use `grep "physical id" /proc/cpuinfo | wc -l` with the command grep looking inside the file "physical id" and with wc -l to count the line of the grep output.

<img  width="836"  src="https://imgur.com/CEZaJIS.png">

### 7-3 Virtual Cores
To show the number of virtual cores is very similar to the previous one. We will again use the file /proc/cpuinfo, but in this case we will use the command `grep processor /proc/cpuinfo | wc -l`. The usage is practically the same as before, only that instead of counting the lines of "physical id" we will do it with "processor". We do it this way for the same reason as before, the way of quantifying marks 0 if there is a processor.

<img  width="836"  src="https://imgur.com/rv1ggkB.png">

### 7- 4 RAM

1 ◦ To show the RAM memory we will use the command `free` to see at the moment information about the RAM, the used part, free, reserved for other resources, etc. For more info about the command we will put free --help. We will use free --mega since that unit of measure appears in the subject.

<img  width="836"  src="https://imgur.com/QKfkAj6.png">

2 ◦ Once we have run this command, we must filter our search since we do not need all the information that it provides. The first thing we need to show is the used memory, for which we will use the command `awk`, which processes data based on text files, that is, we can use the data that interests us from a file. Finally, what we will do is compare if the first word of a row is equal to "Mem:" we will print the third word of that row, which will be the used memory. The whole command together would be `free --mega | awk '$1 == "Mem:" {print $3}'`. In the script the return value of this command will be assigned to a variable that will be concatenated with other variables so that everything is the same as specified in the subject.

<img  width="836"  src="https://imgur.com/XWd5JpO.png">

3 ◦ To obtain the total memory, the command is practically the same as the previous one, the only thing we must change is that instead of printing the third word of the row, we want the second one `free --mega | awk '$1 == "Mem:" {print $2}'`.

<img  width="836"  src="https://imgur.com/Svkw466.png">

4 ◦ Finally, we must calculate the % of used memory. The command is again similar to the previous ones, the only modification we will make is in the printing part. As the operation to get the percentage is not exact, it can give us many decimals and in the subject only 2 appear, so we will do the same, that is why we use `%.2f` so that only 2 decimals are shown. Another thing you may not know is that in printf to show a `%` you have to put `%%`. The whole command `free --mega | awk '$1 == "Mem:" {printf("(%.2f%%)\n", $3/$2*100)}'`.

<img  width="836"  src="https://imgur.com/uHCTeHm.png">

### 7-5 Disk memory

1 ◦ To view the occupied and available memory of the disk, we will use the `df` command, which stands for "disk filesystem", it is used to get a complete summary of the use of disk space. As indicated in the subject, the used memory is shown in MB, so we will then use the -m flag. Next, we will do a grep to only show us the lines that contain "/dev/" and then we will do another grep with the -v flag to exclude lines that contain "/boot". Finally, we will use the awk command and sum the value of the third word of each line to once all the lines are summed, print the final result of the sum. The entire command is as follows: `df -m | grep "/dev/" | grep -v "/boot" | awk '{memory_use += $3} END {print memory_use "\n"}'`.

<img  width="836"  src="https://imgur.com/gsJ7YOF.png">

2 ◦ To obtain the total space, we will use a very similar command. The only differences will be that the values we will sum will be $2 instead of $3 and the other difference is that in the subject the total size appears in Gb, so as the result of the sum gives us the number in Mb we must transform it to Gb, for this we must divide the number by 1024 and remove the decimals.
`df -m | grep "/dev/" | grep -v "/boot" | awk '{memory_result += $2} END {printf ("%.0fGb\n"), memory_result/1024}'`

<img  width="836"  src="https://imgur.com/GxMlM7S.png">

3 ◦ Finally, we must show a percentage of the used memory. To do this, again, we will use a command very similar to the previous two. The only thing we will change is that we will combine the two previous commands to have two variables, one that represents the used memory and the other the total. Once we have done this, we will perform an operation to obtain the percentage `use/total*100` and the result of this operation will be printed as it appears in the subject, between parentheses and with the % symbol at the end. The final command is this: `df -m | grep "/dev/" | grep -v "/boot" | awk '{use += $3} {total += $2} END {printf("(%d%%)\n"), use/total*100}'`.

<img  width="836"  src="https://imgur.com/n76fihy.png">

###  7-6  CPU usage percentage

### 1 ◦ Using `vmstat` to Capture CPU Statistics

The `vmstat` command reports virtual memory statistics and other system performance metrics. We will use it to gather CPU statistics.

<img  width="836"  src="https://imgur.com/3Fk7Qcz.png">

-   **`1`**: Interval in seconds between updates.
-   **`2`**: Number of updates (including the initial report).

This command provides two reports of system statistics. The first report is a summary since the last boot, and the second report is an update after 1 second.

### 2 ◦ Extracting the Last Report

We need the most recent data, so we extract the last line of the output from `vmstat` we use `tail -1`.

<img  width="836"  src="https://imgur.com/PK2scpS.png">

### 3 ◦ Extracting the CPU Idle Percentage

We use `awk` to extract the 15th column from the last line, which represents the CPU idle percentage (`%id`).

<img  width="836"  src="https://imgur.com/uY5d8Yt.png">

### 4 ◦ Calculating the CPU Usage Percentage

To find the CPU usage percentage, we subtract the idle percentage from 100.

<img  width="836"  src="https://imgur.com/wq8VXwB.png">

If you see `0.0%` CPU usage, it usually means your computer isn't doing much work at the moment. This can also happen if you’re checking the CPU usage for a very short time, which might miss small bursts of activity.

### 7-7 Last reboot

To find out when your system was last restarted, you can use the `who` command combined with `awk` to extract and display the relevant information. Follow the steps below to get a concise view of the last boot time:

### 1 ◦ View Last System Boot Time

Run the following command to display the time of the last system boot:

<img  width="836"  src="https://imgur.com/ywhbSJA.png">

### 2 ◦ Extract and Display Only the Date and Time

To filter out the unnecessary information and display only the date and time of the last boot, use the `awk` command as follows:

<img  width="836"  src="https://imgur.com/g5mFulX.png">

-   `who -b` provides the last system boot information.
-   `awk '$1 == "system" {print $3 " " $4}'` processes the output to extract only the date and time:
    -   `$1` matches the first field in the output, which is `system`.
    -   `$3` and `$4` represent the date and time fields, respectively.
    -   The command outputs the date and time in a clean format.

### 7-8 LVM active

To determine if Logical Volume Management (LVM) is active on your system, you can use the `lsblk` command combined with some basic shell scripting.

### 1 ◦ Use `lsblk` to Check for LVM

The `lsblk` command lists information about all available block devices (e.g., hard drives, SSDs, memory devices) and their properties. We need to look for "lvm" in the output, which indicates the presence of LVM volumes.

<img  width="836"  src="https://imgur.com/IIMp2ph.png">

### 2 ◦ Filter Output for LVM Information

To automate the process of determining whether LVM is active, you can use a shell script to search for "lvm" in the `lsblk` output. The script will count occurrences of "lvm" and print "yes" if LVM is present, or "no" if it is not.

<img  width="836"  src="https://imgur.com/78v58Sp.png">

**Explanation:**

-   `lsblk`: Lists block devices and their details.
-   `grep "lvm"`: Searches for the term "lvm" in the `lsblk` output.
-   `wc -l`: Counts the number of lines containing "lvm".
-   `if [ $(...) -gt 0 ]`: Checks if the count is greater than 0.
-   `echo "yes"`: Prints "yes" if LVM is found.
-   `echo "no"`: Prints "no" if LVM is not found.
-   `fi`: Ends the `if` block.

### 7 - 9 TCP connections

To determine the number of established TCP connections on your system, you can use the `ss` command. This command replaces the outdated `netstat` utility and provides a more modern and efficient way to view socket statistics.

### 1 ◦ Use the `ss` Command: The `ss` command is used to display detailed information about network sockets. We will use it with specific flags to filter the results for TCP connections.

<img  width="836"  src="https://imgur.com/1l01GrM.png">

### 2 ◦ Filter for TCP Connections:

-   Use the `-ta` flag with `ss` to list all TCP connections.
-   `-t` stands for TCP sockets.
-   `-a` shows all sockets (both listening and non-listening).

<img  width="836"  src="https://imgur.com/XXVRrdl.png">

### 3 ◦ Counting the Number of Established Connections

To count the number of established connections, pipe the filtered results to `wc -l`, which counts the number of lines in the output `ss -ta | grep ESTAB | wc -l`.

<img  width="836"  src="https://imgur.com/qojExku.png">

`wc -l`: Counts the number of lines in the output, which corresponds to the number of established connections.

### 7 - 10 Number of users

We will use the `users` command which will show us the names of the users there are, knowing this, we will put `wc -w` to count the number of words in the command output. The entire command is as follows: `users | wc -w`.

<img  width="836"  src="https://imgur.com/3NVwEm0.png">

### 7-11 IP Address & MAC

### 1 ◦ Get the Host IP Address

To obtain the host's IP address, use the `hostname` command with the `-I` option.

<img  width="836"  src="https://imgur.com/pYG1wJj.png">

`hostname -I`: Displays all IP addresses assigned to the host. If multiple IP addresses are assigned, they will all be shown.

### 2 ◦ Get the MAC Address

To retrieve the MAC address, which uniquely identifies your network interface, use the `ip link` command combined with `grep` and `awk`.

<img  width="836"  src="https://imgur.com/JtC1e2k.png">

### 7-12 Number of commands executed with sudo

To determine the number of commands executed with `sudo`, you can use `journalctl`, a tool for managing system logs. The following steps outline how to filter and count these entries effectively.

### 1 ◦ Use `journalctl` to Access Logs

`journalctl` allows you to view and manage logs collected by `systemd`. We'll use it to filter logs related to `sudo`.

<img  width="836"  src="https://imgur.com/fKC9AMK.png">

**`_COMM=sudo`**: Filters the logs to include only entries where the command (`_COMM`) is `sudo`. This shows all logs where `sudo` was invoked, including system startup and shutdown entries.

### 2 ◦ Filter for Specific Commands

To focus on commands executed via `sudo`, filter further to exclude irrelevant log entries (such as root session starts/ends). Use `grep` to show only the lines related to actual commands.

<img  width="836"  src="https://imgur.com/PGyUb55.png">

**`grep COMMAND`**: Filters the output to include only lines that contain "COMMAND", which represents actual commands run via `sudo`.

### 3 ◦ Count the Number of Commands

Finally, count the number of filtered lines using `wc -l` to get the total number of commands executed with `sudo`.

<img  width="836"  src="https://imgur.com/y0GTKJ8.png">

## 7.1 Total result of the script🆗

⚠️ Remember not to copy and paste if you do not know the function of each command. ⚠️
```
#!/bin/bash

# ARCH
arch=$(uname -a)

# CPU PHYSICAL
cpuf=$(grep "physical id" /proc/cpuinfo | wc -l)

# CPU VIRTUAL
cpuv=$(grep "processor" /proc/cpuinfo | wc -l)

# RAM
ram_total=$(free --mega | awk '$1 == "Mem:" {print $2}')
ram_use=$(free --mega | awk '$1 == "Mem:" {print $3}')
ram_percent=$(free --mega | awk '$1 == "Mem:" {printf("%.2f"), $3/$2*100}')

# DISK
disk_total=$(df -m | grep "/dev/" | grep -v "/boot" | awk '{disk_t += $2} END {printf ("%.1fGb\n"), disk_t/1024}')
disk_use=$(df -m | grep "/dev/" | grep -v "/boot" | awk '{disk_u += $3} END {print disk_u}')
disk_percent=$(df -m | grep "/dev/" | grep -v "/boot" | awk '{disk_u += $3} {disk_t+= $2} END {printf("%d"), disk_u/disk_t*100}')

# CPU LOAD
cpul=$(vmstat 1 2 | tail -1 | awk '{printf $15}')
cpu_op=$(expr 100 - $cpul)
cpu_fin=$(printf "%.1f" $cpu_op)

# LAST BOOT
lb=$(who -b | awk '$1 == "system" {print $3 " " $4}')

# LVM USE
lvmu=$(if [ $(lsblk | grep "lvm" | wc -l) -gt 0 ]; then echo yes; else echo no; fi)

# TCP CONNEXIONS
tcpc=$(ss -ta | grep ESTAB | wc -l)

# USER LOG
ulog=$(users | wc -w)

# NETWORK
ip=$(hostname -I)
mac=$(ip link | grep "link/ether" | awk '{print $2}')

# SUDO
cmnd=$(journalctl _COMM=sudo | grep COMMAND | wc -l)

wall "	Architecture: $arch
	CPU physical: $cpuf
	vCPU: $cpuv
	Memory Usage: $ram_use/${ram_total}MB ($ram_percent%)
	Disk Usage: $disk_use/${disk_total} ($disk_percent%)
	CPU load: $cpu_fin%
	Last boot: $lb
	LVM use: $lvmu
	Connections TCP: $tcpc ESTABLISHED
	User log: $ulog
	Network: IP $ip ($mac)
	Sudo: $cmnd cmd"
```

Script viewed from nano ↙️

<img  width="836"  src="https://imgur.com/uXxNGC4.png">

Result after executing the script ↙️

<img  width="836"  src="https://imgur.com/hcAdhjx.png">

## 8. Crontab⏰

🧠 What is Crontab?

Crontab is the timekeeper of your system, responsible for scheduling background tasks to run at specific times or intervals. This powerful tool enables the automation of repetitive tasks without requiring manual intervention.

To configure crontab, follow these steps:

    Edit the Crontab File:
    Use the command `sudo crontab -u root -e` to edit the crontab file for the root user.

Within the file, you'll add the following command to execute your script every 10 minutes: */10 * * * * sh /path/to/your/script.

<img  width="836"  src="https://imgur.com/c8c9Zzo.png">

Operation of each crontab parameter:

```
* m: Represents the minute when the script will be executed. Valid values range from 0 to 59.

* h: Indicates the hour in the 24-hour format. Values range from 0 to 23, where 0 represents midnight (12:00 AM).

* dom: Stands for the day of the month. For example, setting it to 15 would execute the script on the 15th day of each month.

* dow: Denotes the day of the week, either as a numeric value (0 to 7, where 0 and 7 represent Sunday) or using the first three letters of the English day names: mon, tue, wed, thu, fri, sat, sun.

* user: Specifies the user who will execute the command. This can be root or another user with appropriate permissions to run the script.

* command: Refers to the command or the absolute path of the script to be executed.
```

## 9. Signature.txt📝

1 ◦ To obtain the signature, the first thing we must do is shut down the virtual machine, since once you turn it on or modify something, the signature will change.

<img  width="836"  src="https://imgur.com/cgsV5T9.png">

2 ◦ The next step is to navigate to the directory where your virtual machine's .vdi file is located. To do this, open your terminal and use the cd command:

cd `/home/ldurmish/sgoinfre/Born2beRoot/`

<img  width="836"  src="https://imgur.com/aoqADk0.png">

3 ◦ Before performing the shasum command to verify the integrity of your .vdi file, it's important to take a screenshot of your current virtual machine state. This helps in comparing the state of your virtual machine before and after any operations. Once there we will click on 3 dots.

<img  width="836"  src="https://imgur.com/mPIebPK.png">

4 ◦ Change the  dropdown from `Details` to `Snapshot`.

<img  width="836"  src="https://imgur.com/gemIIqn.png">

5 ◦ Press the `Take` button to capture a screenshot of the current state. This screenshot will serve as a reference to ensure that the machine's state remains consistent.

<img  width="836"  src="https://imgur.com/HXN0Yug.png">

6 ◦ Finally, we will run shasum machinename.vdi and this will give us the signature. The result of this signature is what we will need to add to our signature.txt file and subsequently upload the file to the intra repository.

<img  width="836"  src="https://imgur.com/QW37nQk.png">

**Important**: You can safely reopen and use the virtual machine because the state is saved in the snapshot. If you need to make changes and then verify the integrity again, revert to this snapshot before generating a new shasum.

## 10. Bonus⭐

### 10.1 Manual partition

1 ◦ When choosing disk partitioning, we will select manual. This way we can edit the partitions one by one.

[![Screen Shot 2022-10-23 at 4 30 48 PM](https://user-images.githubusercontent.com/66915274/197397840-b6ae9d65-a6aa-4a5d-a03f-856d9ce81644.png)](https://user-images.githubusercontent.com/66915274/197397840-b6ae9d65-a6aa-4a5d-a03f-856d9ce81644.png)

2 ◦ In this section, it shows us a general description of our partitions and mount points. Currently, we do not have any partitions. To create a new partition table, we must choose the device where we want to create them. In our case, we will choose the only one available.

[![Screen Shot 2022-10-23 at 4 35 39 PM](https://user-images.githubusercontent.com/66915274/197398114-44abc561-d34d-47c9-b512-581b4ec6fddb.png)](https://user-images.githubusercontent.com/66915274/197398114-44abc561-d34d-47c9-b512-581b4ec6fddb.png)

3 ◦ We accept the confirmation message. Basically, it warns us that if there are already partitions on the device, they will be deleted and that if we are sure to create a new empty partition table.

[![Screen Shot 2022-10-23 at 4 36 08 PM](https://user-images.githubusercontent.com/66915274/197398137-b9fe1f96-5907-462e-8a50-44b71ae2aefe.png)](https://user-images.githubusercontent.com/66915274/197398137-b9fe1f96-5907-462e-8a50-44b71ae2aefe.png)

4 ◦ Once we have completed the previous step, we can see how our partition table appears empty. Now we must configure it, for this we must select it.

[![Screen Shot 2022-10-23 at 4 36 35 PM](https://user-images.githubusercontent.com/66915274/197398172-b05fa7aa-e5b4-40cb-afd4-03a1404d7885.png)](https://user-images.githubusercontent.com/66915274/197398172-b05fa7aa-e5b4-40cb-afd4-03a1404d7885.png)

5 ◦ We will create a new partition.

[![Screen Shot 2022-10-23 at 4 36 54 PM](https://user-images.githubusercontent.com/66915274/197398199-70570553-de1b-49a9-8c44-da9a1e4b5c1e.png)](https://user-images.githubusercontent.com/66915274/197398199-70570553-de1b-49a9-8c44-da9a1e4b5c1e.png)

We will start by creating this:

[![image](https://user-images.githubusercontent.com/66915274/197427077-48636236-4012-4edf-b0e4-319db502e685.png)](https://user-images.githubusercontent.com/66915274/197427077-48636236-4012-4edf-b0e4-319db502e685.png)

6 ◦ As the subject indicates, the size of the partition must be 500 megabytes.

[![Screen Shot 2022-10-23 at 4 37 27 PM](https://user-images.githubusercontent.com/66915274/197398241-604b2bb2-7303-412a-b382-40bfbf443ed0.png)](https://user-images.githubusercontent.com/66915274/197398241-604b2bb2-7303-412a-b382-40bfbf443ed0.png)

7 ◦ We choose the type of partition. We choose primary because it will be the partition where the Operating System will be installed.

[![Screen Shot 2022-10-23 at 4 37 38 PM](https://user-images.githubusercontent.com/66915274/197398253-2c0f8205-3d3f-4ab7-94a3-70c37ee014d9.png)](https://user-images.githubusercontent.com/66915274/197398253-2c0f8205-3d3f-4ab7-94a3-70c37ee014d9.png)

Brief description of all types of partitions:

◦ **Primary:** The only partition on which an OS can be installed. There can only be 4 primary partitions per hard drive or 3 primary and one extended.

◦ **Secondary/Extended:** It was designed to break the 4 primary partition limitation on a single physical disk. There can only be one partition of this type per disk, and it only serves to contain logical partitions.

◦ **Logical:** It occupies a portion of the primary/extended partition or the whole of it, which has been formatted with a specific type of file system (in our case we will use ext4) and has been assigned a unit, so the operating system recognizes the logical partitions or its file system. There can be a maximum of 23 logical partitions in an extended partition, however, Linux, the OS we are currently working with, reduces it to 15, more than enough for this project.

8 ◦ We will select beginning because we want the new partition to be created at the beginning of the available space.

[![Screen Shot 2022-10-23 at 4 37 52 PM](https://user-images.githubusercontent.com/66915274/197398265-c63d7b32-55b7-45ad-86b3-166e44cfd598.png)](https://user-images.githubusercontent.com/66915274/197398265-c63d7b32-55b7-45ad-86b3-166e44cfd598.png)

9 ◦ In the following screenshot it shows the details of the partition. We will modify the mount point as specified in the subject.

[![Screen Shot 2022-10-23 at 4 38 27 PM](https://user-images.githubusercontent.com/66915274/197398293-2487ded0-2584-48c4-a5ea-1f2464ec39f9.png)](https://user-images.githubusercontent.com/66915274/197398293-2487ded0-2584-48c4-a5ea-1f2464ec39f9.png)

10 ◦ We choose boot as the mount point for our partition.

[![Screen Shot 2022-10-23 at 4 38 49 PM](https://user-images.githubusercontent.com/66915274/197398322-51b9854b-ab32-4d81-8126-3ef3913858a6.png)](https://user-images.githubusercontent.com/66915274/197398322-51b9854b-ab32-4d81-8126-3ef3913858a6.png)

11 ◦ We finish configuring the current partition.

[![Screen Shot 2022-10-23 at 4 39 07 PM](https://user-images.githubusercontent.com/66915274/197398336-72b17153-73dc-48a5-b7d3-839877e8983b.png)](https://user-images.githubusercontent.com/66915274/197398336-72b17153-73dc-48a5-b7d3-839877e8983b.png)

12 ◦ Once we have completed the previous step, the partition should already appear. Now we must create a logical partition with all the available space on the disk, which has no mount point and is encrypted. To do this, we select the free space where we want to create it.

[![Screen Shot 2022-10-23 at 4 39 37 PM](https://user-images.githubusercontent.com/66915274/197398367-ee8a1f5d-3941-4a86-a775-90f29b1c955e.png)](https://user-images.githubusercontent.com/66915274/197398367-ee8a1f5d-3941-4a86-a775-90f29b1c955e.png)

As is requires on the subject.
[![image](https://user-images.githubusercontent.com/66915274/197431553-718358bb-6570-41dd-b114-09acc347999d.png)](https://user-images.githubusercontent.com/66915274/197431553-718358bb-6570-41dd-b114-09acc347999d.png)

13 ◦ We create a new partition.

[![Screen Shot 2022-10-23 at 4 39 58 PM](https://user-images.githubusercontent.com/66915274/197398396-843c7fb3-b945-4305-a960-02aa9d4ca940.png)](https://user-images.githubusercontent.com/66915274/197398396-843c7fb3-b945-4305-a960-02aa9d4ca940.png)

14 ◦ We select the maximum size.

[![Screen Shot 2022-10-23 at 4 40 26 PM](https://user-images.githubusercontent.com/66915274/197398425-63205376-839f-4986-a8d0-981cdaa380e4.png)](https://user-images.githubusercontent.com/66915274/197398425-63205376-839f-4986-a8d0-981cdaa380e4.png)

15 ◦ We select the type of partition, in this case logical.

[![Screen Shot 2022-10-23 at 4 40 53 PM](https://user-images.githubusercontent.com/66915274/197398448-49c99180-9a3d-4dd4-a9ce-d680bfdefa1c.png)](https://user-images.githubusercontent.com/66915274/197398448-49c99180-9a3d-4dd4-a9ce-d680bfdefa1c.png)

16 ◦ We will modify the mount point.

[![Screen Shot 2022-10-23 at 4 41 44 PM](https://user-images.githubusercontent.com/66915274/197398500-188cc4fb-4eb5-4a56-893b-58838877c056.png)](https://user-images.githubusercontent.com/66915274/197398500-188cc4fb-4eb5-4a56-893b-58838877c056.png)

17 ◦ We will choose the option not to mount it.

[![Screen Shot 2022-10-23 at 4 42 11 PM](https://user-images.githubusercontent.com/66915274/197398518-f6fb7588-8c53-40a9-9ceb-238d6a62d942.png)](https://user-images.githubusercontent.com/66915274/197398518-f6fb7588-8c53-40a9-9ceb-238d6a62d942.png)

18 ◦ We finish configuring the current partition.

[![Screen Shot 2022-10-23 at 4 42 41 PM](https://user-images.githubusercontent.com/66915274/197398541-922f2c4d-ed5a-4d92-8083-ccf57aec3dee.png)](https://user-images.githubusercontent.com/66915274/197398541-922f2c4d-ed5a-4d92-8083-ccf57aec3dee.png)

19 ◦ We will configure encrypted volumes. This way we can encrypt our partition.

[![Screen Shot 2022-10-23 at 4 43 08 PM](https://user-images.githubusercontent.com/66915274/197398562-2369fa90-7db9-4ba3-abed-7ac15ede8b81.png)](https://user-images.githubusercontent.com/66915274/197398562-2369fa90-7db9-4ba3-abed-7ac15ede8b81.png)

20 ◦ We accept the confirmation message.

[![Screen Shot 2022-10-23 at 4 43 27 PM](https://user-images.githubusercontent.com/66915274/197398573-9720e351-04f4-49f0-a3dc-fe0ce1ada296.png)](https://user-images.githubusercontent.com/66915274/197398573-9720e351-04f4-49f0-a3dc-fe0ce1ada296.png)

21 ◦ We create the encrypted volumes.

[![Screen Shot 2022-10-23 at 4 43 46 PM](https://user-images.githubusercontent.com/66915274/197398595-b36ab8da-86c6-483a-99fd-079293a92570.png)](https://user-images.githubusercontent.com/66915274/197398595-b36ab8da-86c6-483a-99fd-079293a92570.png)

22 ◦ We select which partition we want to encrypt.

[![Screen Shot 2022-10-23 at 4 44 06 PM](https://user-images.githubusercontent.com/66915274/197398615-7c9f8e45-7885-4f39-84eb-e3a056eeb2c7.png)](https://user-images.githubusercontent.com/66915274/197398615-7c9f8e45-7885-4f39-84eb-e3a056eeb2c7.png)

23 ◦ We finish configuring the current partition.

[![Screen Shot 2022-10-23 at 4 44 35 PM](https://user-images.githubusercontent.com/66915274/197398649-06749ec8-903d-4b1a-af2a-c2dad77bcaec.png)](https://user-images.githubusercontent.com/66915274/197398649-06749ec8-903d-4b1a-af2a-c2dad77bcaec.png)

24 ◦ We finish because we don't want to create more encrypted volumes.

[![Screen Shot 2022-10-23 at 4 44 49 PM](https://user-images.githubusercontent.com/66915274/197398663-0bd74c65-b3fd-430c-b3e6-4f1e0c76ae8d.png)](https://user-images.githubusercontent.com/66915274/197398663-0bd74c65-b3fd-430c-b3e6-4f1e0c76ae8d.png)

25 ◦ We accept the confirmation message. It tells us that everything inside the partition will be encrypted and it should not take long to finish.

[![Screen Shot 2022-10-23 at 4 45 06 PM](https://user-images.githubusercontent.com/66915274/197398670-91db3e3e-b271-4e1b-ad8a-28ceb06e0897.png)](https://user-images.githubusercontent.com/66915274/197398670-91db3e3e-b271-4e1b-ad8a-28ceb06e0897.png)

26 ◦ We don't care if it takes a long time or not, we cancel it because there is nothing to encrypt since the partition is empty.

[![Screen Shot 2022-10-23 at 4 45 27 PM](https://user-images.githubusercontent.com/66915274/197398685-6603ef31-d499-46da-949f-ade8e2a05bf9.png)](https://user-images.githubusercontent.com/66915274/197398685-6603ef31-d499-46da-949f-ade8e2a05bf9.png)

27 ◦ Again we must enter a password, this time it will be the encryption phrase. As I previously mentioned, you must repeat the process and write it down as it will be important in the future.

<img  src="https://imgur.com/nNzSkrx.png">

28 ◦ We repeat the encryption phrase.

<img  src="https://imgur.com/az22E4l.png">


29 ◦ We will configure the logical volume manager.

[![Screen Shot 2022-10-23 at 4 50 17 PM](https://user-images.githubusercontent.com/66915274/197398933-85e0025e-0a4d-41f0-8fd0-5f0c8ee32e9b.png)](https://user-images.githubusercontent.com/66915274/197398933-85e0025e-0a4d-41f0-8fd0-5f0c8ee32e9b.png)

30 ◦ We will accept the confirmation message as we agree to save the changes to the disk.

[![Screen Shot 2022-10-23 at 4 50 42 PM](https://user-images.githubusercontent.com/66915274/197398945-d79ea2a7-a13e-4e6a-9e9c-40bdcd2dd502.png)](https://user-images.githubusercontent.com/66915274/197398945-d79ea2a7-a13e-4e6a-9e9c-40bdcd2dd502.png)

31 ◦ We will create a new volume group. Volume groups group partitions.

[![Screen Shot 2022-10-23 at 4 52 04 PM](https://user-images.githubusercontent.com/66915274/197399021-29b21274-37c1-4fd9-8526-962969d1cce3.png)](https://user-images.githubusercontent.com/66915274/197399021-29b21274-37c1-4fd9-8526-962969d1cce3.png)

32 ◦ We will enter the name we want to give it. `LVMGroup` as indicated in the subject.

[![Screen Shot 2022-10-23 at 4 52 58 PM](https://user-images.githubusercontent.com/66915274/197399065-1ac8d80d-9e18-4b4a-a60f-11496e7de26d.png)](https://user-images.githubusercontent.com/66915274/197399065-1ac8d80d-9e18-4b4a-a60f-11496e7de26d.png)

33 ◦ We will select the partition where we want to create the group.

[![Screen Shot 2022-10-23 at 4 53 22 PM](https://user-images.githubusercontent.com/66915274/197399089-5ea5f48e-176c-4278-8b14-a13b7f5ee45c.png)](https://user-images.githubusercontent.com/66915274/197399089-5ea5f48e-176c-4278-8b14-a13b7f5ee45c.png)

34 ◦ Now we must create all the logical partitions. As we have to repeat the same actions several times, there are captures that will not be documented.

[![image](https://user-images.githubusercontent.com/66915274/197439138-889d6368-1875-402b-a094-bd146bb7cb8a.png)](https://user-images.githubusercontent.com/66915274/197439138-889d6368-1875-402b-a094-bd146bb7cb8a.png)

[![Screen Shot 2022-10-23 at 4 53 50 PM](https://user-images.githubusercontent.com/66915274/197399108-fb566eb4-664f-4509-8948-ab4ed04407b5.png)](https://user-images.githubusercontent.com/66915274/197399108-fb566eb4-664f-4509-8948-ab4ed04407b5.png)

35 ◦ We will start by choosing the group where we want them to be created. We select the only one available (the one we just created).

[![Screen Shot 2022-10-23 at 4 54 02 PM](https://user-images.githubusercontent.com/66915274/197399115-e7d3b313-763c-421c-a71d-850d318432e7.png)](https://user-images.githubusercontent.com/66915274/197399115-e7d3b313-763c-421c-a71d-850d318432e7.png)

36 ◦ The order of creation of the logical units will be the same as indicated in the subject, so we will start with root and end with var-log. Then we will select the name of the logical volume.

[![Screen Shot 2022-10-23 at 4 55 42 PM](https://user-images.githubusercontent.com/66915274/197399188-6ae8c83b-057d-498f-b112-9116079b0808.png)](https://user-images.githubusercontent.com/66915274/197399188-6ae8c83b-057d-498f-b112-9116079b0808.png)

37 ◦ Size, as indicated in the subject, will be 10g.

[![Screen Shot 2022-10-23 at 4 56 21 PM](https://user-images.githubusercontent.com/66915274/197399216-c65f43ca-fb8e-4d05-9212-24ad2ee87b39.png)](https://user-images.githubusercontent.com/66915274/197399216-c65f43ca-fb8e-4d05-9212-24ad2ee87b39.png)

38 ◦ We repeat the process for `swap`. We only change the name and size.

[![Screen Shot 2022-10-23 at 4 56 49 PM](https://user-images.githubusercontent.com/66915274/197399239-c26598cb-e7bb-474c-aece-90f043e1990f.png)](https://user-images.githubusercontent.com/66915274/197399239-c26598cb-e7bb-474c-aece-90f043e1990f.png)

[![Screen Shot 2022-10-23 at 4 57 26 PM](https://user-images.githubusercontent.com/66915274/197399278-c5cd5a9c-2ab1-42b9-8871-b58e9b33b4b6.png)](https://user-images.githubusercontent.com/66915274/197399278-c5cd5a9c-2ab1-42b9-8871-b58e9b33b4b6.png)

[![Screen Shot 2022-10-23 at 4 57 41 PM](https://user-images.githubusercontent.com/66915274/197399288-7ecf6adf-aaf5-46bf-959f-2159d19b7bbf.png)](https://user-images.githubusercontent.com/66915274/197399288-7ecf6adf-aaf5-46bf-959f-2159d19b7bbf.png)

[![Screen Shot 2022-10-23 at 4 58 11 PM](https://user-images.githubusercontent.com/66915274/197399310-fc6c397e-8257-4e06-8fba-ad35431c9b96.png)](https://user-images.githubusercontent.com/66915274/197399310-fc6c397e-8257-4e06-8fba-ad35431c9b96.png)

39 ◦ We repeat the process for `home`. We only change the name and size.

[![Screen Shot 2022-10-23 at 4 58 57 PM](https://user-images.githubusercontent.com/66915274/197399347-a815d58b-686e-4d9d-bb5c-34a7b54476ab.png)](https://user-images.githubusercontent.com/66915274/197399347-a815d58b-686e-4d9d-bb5c-34a7b54476ab.png)

[![Screen Shot 2022-10-23 at 4 59 07 PM](https://user-images.githubusercontent.com/66915274/197399355-28617029-c28c-4ca4-b56b-646e066cded6.png)](https://user-images.githubusercontent.com/66915274/197399355-28617029-c28c-4ca4-b56b-646e066cded6.png)

[![Screen Shot 2022-10-23 at 5 01 13 PM](https://user-images.githubusercontent.com/66915274/197399433-1e9c7110-9240-4982-9835-b026ed73171f.png)](https://user-images.githubusercontent.com/66915274/197399433-1e9c7110-9240-4982-9835-b026ed73171f.png)

[![Screen Shot 2022-10-23 at 5 04 34 PM](https://user-images.githubusercontent.com/66915274/197399610-247a7a35-0141-4c14-884e-7ecd07caa96d.png)](https://user-images.githubusercontent.com/66915274/197399610-247a7a35-0141-4c14-884e-7ecd07caa96d.png)

40 ◦ We repeat the process for `var`. We only change the name and size.

[![Screen Shot 2022-10-23 at 5 05 10 PM](https://user-images.githubusercontent.com/66915274/197399644-58da651c-f4ad-4d1e-b128-de87c92cc292.png)](https://user-images.githubusercontent.com/66915274/197399644-58da651c-f4ad-4d1e-b128-de87c92cc292.png)

[![Screen Shot 2022-10-23 at 5 05 30 PM](https://user-images.githubusercontent.com/66915274/197399662-32ab0a06-c14d-4a0e-ac80-cb0d12fc24eb.png)](https://user-images.githubusercontent.com/66915274/197399662-32ab0a06-c14d-4a0e-ac80-cb0d12fc24eb.png)

[![Screen Shot 2022-10-23 at 5 06 03 PM](https://user-images.githubusercontent.com/66915274/197399693-b49c2ffe-b21a-43c5-bd3f-160bc544b072.png)](https://user-images.githubusercontent.com/66915274/197399693-b49c2ffe-b21a-43c5-bd3f-160bc544b072.png)

41 ◦ We repeat the process for `srv`. We only change the name.

[![Screen Shot 2022-10-23 at 5 06 14 PM](https://user-images.githubusercontent.com/66915274/197399702-6d531de3-690d-458d-9a3b-bf6ceedd7cda.png)](https://user-images.githubusercontent.com/66915274/197399702-6d531de3-690d-458d-9a3b-bf6ceedd7cda.png)

[![Screen Shot 2022-10-23 at 5 06 39 PM](https://user-images.githubusercontent.com/66915274/197399724-0fdd75ad-e978-4468-8509-a62cdc4a3faf.png)](https://user-images.githubusercontent.com/66915274/197399724-0fdd75ad-e978-4468-8509-a62cdc4a3faf.png)

[![Screen Shot 2022-10-23 at 5 06 57 PM](https://user-images.githubusercontent.com/66915274/197399744-b82b1dcd-09c7-44cc-a2ab-b6079abcbb5a.png)](https://user-images.githubusercontent.com/66915274/197399744-b82b1dcd-09c7-44cc-a2ab-b6079abcbb5a.png)

[![Screen Shot 2022-10-23 at 5 07 13 PM](https://user-images.githubusercontent.com/66915274/197399757-94732b16-585e-4f7d-a20f-f7ef0814b4e7.png)](https://user-images.githubusercontent.com/66915274/197399757-94732b16-585e-4f7d-a20f-f7ef0814b4e7.png)

42 ◦ We repeat the process for `tmp`. We only change the name.

[![Screen Shot 2022-10-23 at 5 07 34 PM](https://user-images.githubusercontent.com/66915274/197399777-9d871f2a-856d-4b4d-ad18-1195001b0fdf.png)](https://user-images.githubusercontent.com/66915274/197399777-9d871f2a-856d-4b4d-ad18-1195001b0fdf.png)

[![Screen Shot 2022-10-23 at 5 07 46 PM](https://user-images.githubusercontent.com/66915274/197399792-0794ace5-c236-4f68-b023-bb471753eba2.png)](https://user-images.githubusercontent.com/66915274/197399792-0794ace5-c236-4f68-b023-bb471753eba2.png)

[![Screen Shot 2022-10-23 at 5 07 55 PM](https://user-images.githubusercontent.com/66915274/197399798-84a31102-6953-468b-85d4-0a248e98cb17.png)](https://user-images.githubusercontent.com/66915274/197399798-84a31102-6953-468b-85d4-0a248e98cb17.png)

[![Screen Shot 2022-10-23 at 5 08 19 PM](https://user-images.githubusercontent.com/66915274/197399827-5dfc8571-e82c-4a28-aae7-dc716fb6e77b.png)](https://user-images.githubusercontent.com/66915274/197399827-5dfc8571-e82c-4a28-aae7-dc716fb6e77b.png)

43 ◦ Finally, we repeat the process for `var-log`. We only change the name and size.

[![Screen Shot 2022-10-23 at 5 08 34 PM](https://user-images.githubusercontent.com/66915274/197399838-2cd49171-45dd-469a-887c-3ce99d84b7cd.png)](https://user-images.githubusercontent.com/66915274/197399838-2cd49171-45dd-469a-887c-3ce99d84b7cd.png)

[![Screen Shot 2022-10-23 at 5 08 40 PM](https://user-images.githubusercontent.com/66915274/197399841-04b75112-4d21-456c-bf50-8335839764e0.png)](https://user-images.githubusercontent.com/66915274/197399841-04b75112-4d21-456c-bf50-8335839764e0.png)

[![Screen Shot 2022-10-23 at 5 08 59 PM](https://user-images.githubusercontent.com/66915274/197399859-d706de2e-bb20-4a04-96db-4dd57b3778be.png)](https://user-images.githubusercontent.com/66915274/197399859-d706de2e-bb20-4a04-96db-4dd57b3778be.png)

[![Screen Shot 2022-10-23 at 5 09 28 PM](https://user-images.githubusercontent.com/66915274/197399886-a1e9ee69-78a4-4071-af99-2192d535c6cd.png)](https://user-images.githubusercontent.com/66915274/197399886-a1e9ee69-78a4-4071-af99-2192d535c6cd.png)

44 ◦ Once we have completed all the previous steps, we will finish the configuration of the logical volume manager.

[![Screen Shot 2022-10-23 at 5 09 51 PM](https://user-images.githubusercontent.com/66915274/197399904-c584fcdf-eb38-486f-af12-7374f1e04465.png)](https://user-images.githubusercontent.com/66915274/197399904-c584fcdf-eb38-486f-af12-7374f1e04465.png)

45 ◦ Now we can see how in the section where it shows us all our partitions and free space, all the logical partitions that we just created are already appearing. Good, we must configure all of them to select the file system that we want and the mount point indicated in the subject. Again we will go in order and select the first one that appears, which is `home`.

[![Screen Shot 2022-10-23 at 5 10 36 PM](https://user-images.githubusercontent.com/66915274/197399944-bccbe599-b80a-4abe-ac6c-d770447ea727.png)](https://user-images.githubusercontent.com/66915274/197399944-bccbe599-b80a-4abe-ac6c-d770447ea727.png)

46 ◦ Show us the configuration of the partition. We must choose a file system as it currently does not have one.

[![Screen Shot 2022-10-23 at 5 10 55 PM](https://user-images.githubusercontent.com/66915274/197399976-9b871bda-9425-4dbe-b8c9-25c8c6d6c811.png)](https://user-images.githubusercontent.com/66915274/197399976-9b871bda-9425-4dbe-b8c9-25c8c6d6c811.png)

47 ◦ Choose the Ext4 file system, it is the most commonly used file system in Linux distributions.

[![Screen Shot 2022-10-23 at 5 11 18 PM](https://user-images.githubusercontent.com/66915274/197400000-2e855fc9-10b1-4f3e-9c58-85b6ff02a4fb.png)](https://user-images.githubusercontent.com/66915274/197400000-2e855fc9-10b1-4f3e-9c58-85b6ff02a4fb.png)

48 ◦ Now we need to select the mount point.

[![Screen Shot 2022-10-23 at 5 11 44 PM](https://user-images.githubusercontent.com/66915274/197400023-387a70aa-b491-43c0-91d2-cb378da9fc75.png)](https://user-images.githubusercontent.com/66915274/197400023-387a70aa-b491-43c0-91d2-cb378da9fc75.png)

49 ◦ We select `home` as indicated in the subject.

[![Screen Shot 2022-10-23 at 5 11 54 PM](https://user-images.githubusercontent.com/66915274/197400040-e79cad4f-368b-4cee-9ec0-942f38b2f785.png)](https://user-images.githubusercontent.com/66915274/197400040-e79cad4f-368b-4cee-9ec0-942f38b2f785.png)

50 ◦ Once we have selected it, we will finish the configuration of the partition.

[![Screen Shot 2022-10-23 at 5 12 10 PM](https://user-images.githubusercontent.com/66915274/197400059-ab96f2c4-cd92-47cb-a9ee-61257537ee6a.png)](https://user-images.githubusercontent.com/66915274/197400059-ab96f2c4-cd92-47cb-a9ee-61257537ee6a.png)

51 ◦ Again, these steps can become very repetitive so I won't comment much. We repeat everything the same way (except for the mount point) for `root`.

[![Screen Shot 2022-10-23 at 5 13 36 PM](https://user-images.githubusercontent.com/66915274/197400135-c08444fe-e39d-45fa-a3b6-3c73db2a4935.png)](https://user-images.githubusercontent.com/66915274/197400135-c08444fe-e39d-45fa-a3b6-3c73db2a4935.png)

[![Screen Shot 2022-10-23 at 5 13 53 PM](https://user-images.githubusercontent.com/66915274/197400146-41ce0b0c-142c-46b4-a3c5-918676a3a852.png)](https://user-images.githubusercontent.com/66915274/197400146-41ce0b0c-142c-46b4-a3c5-918676a3a852.png)

[![Screen Shot 2022-10-23 at 5 14 08 PM](https://user-images.githubusercontent.com/66915274/197400155-92759327-5671-41f4-8104-dd1de4bc88cb.png)](https://user-images.githubusercontent.com/66915274/197400155-92759327-5671-41f4-8104-dd1de4bc88cb.png)

[![Screen Shot 2022-10-23 at 5 14 22 PM](https://user-images.githubusercontent.com/66915274/197400171-6fd04783-e833-4afd-a753-4b943133a4ab.png)](https://user-images.githubusercontent.com/66915274/197400171-6fd04783-e833-4afd-a753-4b943133a4ab.png)

[![Screen Shot 2022-10-23 at 5 14 39 PM](https://user-images.githubusercontent.com/66915274/197400182-780e1917-3f77-4986-b0e8-b50a90d75403.png)](https://user-images.githubusercontent.com/66915274/197400182-780e1917-3f77-4986-b0e8-b50a90d75403.png)

[![Screen Shot 2022-10-23 at 5 14 52 PM](https://user-images.githubusercontent.com/66915274/197400186-88da831a-c672-4ec0-a64c-0ad2808bb6c5.png)](https://user-images.githubusercontent.com/66915274/197400186-88da831a-c672-4ec0-a64c-0ad2808bb6c5.png)

52 ◦ Repeat the process for `srv` and change the mount point.

[![Screen Shot 2022-10-23 at 5 15 05 PM](https://user-images.githubusercontent.com/66915274/197400198-599b4aa3-a511-45d1-86b0-dd42da4c380f.png)](https://user-images.githubusercontent.com/66915274/197400198-599b4aa3-a511-45d1-86b0-dd42da4c380f.png)

[![Screen Shot 2022-10-23 at 5 15 31 PM](https://user-images.githubusercontent.com/66915274/197400218-e6b26eb7-7933-426f-a7cd-a791400ebdab.png)](https://user-images.githubusercontent.com/66915274/197400218-e6b26eb7-7933-426f-a7cd-a791400ebdab.png)

[![Screen Shot 2022-10-23 at 5 15 37 PM](https://user-images.githubusercontent.com/66915274/197400222-95107b34-8d28-4d4d-a74b-7de6c6a46d33.png)](https://user-images.githubusercontent.com/66915274/197400222-95107b34-8d28-4d4d-a74b-7de6c6a46d33.png)

[![Screen Shot 2022-10-23 at 5 15 44 PM](https://user-images.githubusercontent.com/66915274/197400227-20c13dc0-52cd-4c70-bf4e-531979c54a3e.png)](https://user-images.githubusercontent.com/66915274/197400227-20c13dc0-52cd-4c70-bf4e-531979c54a3e.png)

[![Screen Shot 2022-10-23 at 5 15 52 PM](https://user-images.githubusercontent.com/66915274/197400238-3b403294-74d1-4e63-aca7-7d83447ed5b8.png)](https://user-images.githubusercontent.com/66915274/197400238-3b403294-74d1-4e63-aca7-7d83447ed5b8.png)

[![Screen Shot 2022-10-23 at 5 16 04 PM](https://user-images.githubusercontent.com/66915274/197400249-035f6b9d-3716-4565-9776-aa0af49b3fd7.png)](https://user-images.githubusercontent.com/66915274/197400249-035f6b9d-3716-4565-9776-aa0af49b3fd7.png)

53 ◦ For `swap`, we will make an exception because the file system will be different. We select `swap`.

[![Screen Shot 2022-10-23 at 5 16 32 PM](https://user-images.githubusercontent.com/66915274/197400272-112b44ef-4996-438a-90b8-6620cdd7d2ff.png)](https://user-images.githubusercontent.com/66915274/197400272-112b44ef-4996-438a-90b8-6620cdd7d2ff.png)

54 ◦ At the time of selecting the file system, we leave it on `swap area`.

[![Screen Shot 2022-10-23 at 5 16 41 PM](https://user-images.githubusercontent.com/66915274/197400281-e12ee636-8696-4bee-9198-862b7d6be199.png)](https://user-images.githubusercontent.com/66915274/197400281-e12ee636-8696-4bee-9198-862b7d6be199.png)

55 ◦ Once the previous step is completed, we will finish the partition configuration.

[![Screen Shot 2022-10-23 at 5 16 59 PM](https://user-images.githubusercontent.com/66915274/197400297-8eed129d-0ec0-49a8-8b2a-dd0d04055f75.png)](https://user-images.githubusercontent.com/66915274/197400297-8eed129d-0ec0-49a8-8b2a-dd0d04055f75.png)

[![Screen Shot 2022-10-23 at 5 17 09 PM](https://user-images.githubusercontent.com/66915274/197400309-74e83209-4b2a-4e27-9a67-44373c1db362.png)](https://user-images.githubusercontent.com/66915274/197400309-74e83209-4b2a-4e27-9a67-44373c1db362.png)

56 ◦ Now we will do the same thing as before, but now we will do it with `tmp` and changing the mount point.

[![Screen Shot 2022-10-23 at 5 17 41 PM](https://user-images.githubusercontent.com/66915274/197400341-608516f6-0f5a-4cdd-83d8-c8fbd1635624.png)](https://user-images.githubusercontent.com/66915274/197400341-608516f6-0f5a-4cdd-83d8-c8fbd1635624.png)

[![Screen Shot 2022-10-23 at 5 17 49 PM](https://user-images.githubusercontent.com/66915274/197400346-e9647c7a-a9a2-4a0f-b439-a912247fb3f9.png)](https://user-images.githubusercontent.com/66915274/197400346-e9647c7a-a9a2-4a0f-b439-a912247fb3f9.png)

[![Screen Shot 2022-10-23 at 5 18 01 PM](https://user-images.githubusercontent.com/66915274/197400360-1816d06a-252e-4d41-b1a2-fc547961f353.png)](https://user-images.githubusercontent.com/66915274/197400360-1816d06a-252e-4d41-b1a2-fc547961f353.png)

[![Screen Shot 2022-10-23 at 5 18 08 PM](https://user-images.githubusercontent.com/66915274/197400370-0474b71f-c1c3-445f-ba02-088dc1c64ce3.png)](https://user-images.githubusercontent.com/66915274/197400370-0474b71f-c1c3-445f-ba02-088dc1c64ce3.png)

[![Screen Shot 2022-10-23 at 5 18 24 PM](https://user-images.githubusercontent.com/66915274/197400386-f66494c5-97b9-4bb9-8c75-5856d69d26cc.png)](https://user-images.githubusercontent.com/66915274/197400386-f66494c5-97b9-4bb9-8c75-5856d69d26cc.png)

[![Screen Shot 2022-10-23 at 5 18 40 PM](https://user-images.githubusercontent.com/66915274/197400405-4a368bfb-f862-4bbd-a33e-b87c3038d232.png)](https://user-images.githubusercontent.com/66915274/197400405-4a368bfb-f862-4bbd-a33e-b87c3038d232.png)

57 ◦ We repeat the process again for `var`, changing the mount point.

[![Screen Shot 2022-10-23 at 5 19 13 PM](https://user-images.githubusercontent.com/66915274/197400447-85bcad13-8083-4aec-acb2-fa467e5d4e33.png)](https://user-images.githubusercontent.com/66915274/197400447-85bcad13-8083-4aec-acb2-fa467e5d4e33.png)

[![Screen Shot 2022-10-23 at 5 19 21 PM](https://user-images.githubusercontent.com/66915274/197400452-aed22368-4889-4c04-bf60-5a06fb93944e.png)](https://user-images.githubusercontent.com/66915274/197400452-aed22368-4889-4c04-bf60-5a06fb93944e.png)

[![Screen Shot 2022-10-23 at 5 19 28 PM](https://user-images.githubusercontent.com/66915274/197400459-b6f59948-e804-414a-b41d-21d2f495fccc.png)](https://user-images.githubusercontent.com/66915274/197400459-b6f59948-e804-414a-b41d-21d2f495fccc.png)

[![Screen Shot 2022-10-23 at 5 19 36 PM](https://user-images.githubusercontent.com/66915274/197400462-788d29e5-7798-418a-8725-3cb8dd2849bd.png)](https://user-images.githubusercontent.com/66915274/197400462-788d29e5-7798-418a-8725-3cb8dd2849bd.png)

[![Screen Shot 2022-10-23 at 5 19 51 PM](https://user-images.githubusercontent.com/66915274/197400473-4508d9d6-481d-4f3a-9630-6c1eba7c5cc0.png)](https://user-images.githubusercontent.com/66915274/197400473-4508d9d6-481d-4f3a-9630-6c1eba7c5cc0.png)

[![Screen Shot 2022-10-23 at 5 20 00 PM](https://user-images.githubusercontent.com/66915274/197400482-1f8c147f-66d8-438b-866f-3e9eff75ef5e.png)](https://user-images.githubusercontent.com/66915274/197400482-1f8c147f-66d8-438b-866f-3e9eff75ef5e.png)

58 ◦ Finally, we repeat the process again for `var-log`. In this case, we will have to manually enter the mount point..

[![Screen Shot 2022-10-23 at 5 20 23 PM](https://user-images.githubusercontent.com/66915274/197400513-53b3f899-47f5-4cdb-ab4b-205b1d1bce31.png)](https://user-images.githubusercontent.com/66915274/197400513-53b3f899-47f5-4cdb-ab4b-205b1d1bce31.png)

[![image](https://user-images.githubusercontent.com/66915274/197602511-fa34155b-3244-4b0c-8054-2778edecfb16.png)](https://user-images.githubusercontent.com/66915274/197602511-fa34155b-3244-4b0c-8054-2778edecfb16.png)

[![image](https://user-images.githubusercontent.com/66915274/197602585-03b540af-5d7a-4364-b90a-559bac0cb2a2.png)](https://user-images.githubusercontent.com/66915274/197602585-03b540af-5d7a-4364-b90a-559bac0cb2a2.png)

[![image](https://user-images.githubusercontent.com/66915274/197602630-cc749189-9ac9-48bc-a595-dc33282840ec.png)](https://user-images.githubusercontent.com/66915274/197602630-cc749189-9ac9-48bc-a595-dc33282840ec.png)

[![image](https://user-images.githubusercontent.com/66915274/197602673-5c18be85-1b0f-430b-b507-66711b807115.png)](https://user-images.githubusercontent.com/66915274/197602673-5c18be85-1b0f-430b-b507-66711b807115.png)

[![image](https://user-images.githubusercontent.com/66915274/197602699-fddadd2d-c54d-4313-8165-a93db1249b26.png)](https://user-images.githubusercontent.com/66915274/197602699-fddadd2d-c54d-4313-8165-a93db1249b26.png)

[![image](https://user-images.githubusercontent.com/66915274/197602741-431bd866-1558-4735-bb34-ab57dc5745b7.png)](https://user-images.githubusercontent.com/66915274/197602741-431bd866-1558-4735-bb34-ab57dc5745b7.png)

59 ◦ Once we have completed all of the previous steps, we are almost finished. We must click 'finish partitioning' to save all of the changes to the disk.

[![image](https://user-images.githubusercontent.com/66915274/197602907-4a3ba459-1a5d-468e-81dc-5206403cf034.png)](https://user-images.githubusercontent.com/66915274/197602907-4a3ba459-1a5d-468e-81dc-5206403cf034.png)

60 ◦ We accept the message and the changes will be saved. Make sure that all of the partitions look the same as in the screenshot.

[![image](https://user-images.githubusercontent.com/66915274/197602944-13ca67b2-bcc5-476c-84dc-aadc5e1d3baf.png)](https://user-images.githubusercontent.com/66915274/197602944-13ca67b2-bcc5-476c-84dc-aadc5e1d3baf.png)

61 ◦ We select the option `No` because we do not need additional packages.

[![Captura de pantalla 2022-07-13 a las 20 05 42](https://user-images.githubusercontent.com/66915274/178801099-2dda24f5-0d46-4184-8c44-a8fe0bf46527.png)](https://user-images.githubusercontent.com/66915274/178801099-2dda24f5-0d46-4184-8c44-a8fe0bf46527.png)

62 ◦ We choose our Country.29 ◦ We will configure the logical volume manager.

[![Screen Shot 2022-10-23 at 4 50 17 PM](https://user-images.githubusercontent.com/66915274/197398933-85e0025e-0a4d-41f0-8fd0-5f0c8ee32e9b.png)](https://user-images.githubusercontent.com/66915274/197398933-85e0025e-0a4d-41f0-8fd0-5f0c8ee32e9b.png)

30 ◦ We will accept the confirmation message as we agree to save the changes to the disk.

[![Screen Shot 2022-10-23 at 4 50 42 PM](https://user-images.githubusercontent.com/66915274/197398945-d79ea2a7-a13e-4e6a-9e9c-40bdcd2dd502.png)](https://user-images.githubusercontent.com/66915274/197398945-d79ea2a7-a13e-4e6a-9e9c-40bdcd2dd502.png)

31 ◦ We will create a new volume group. Volume groups group partitions.

[![Screen Shot 2022-10-23 at 4 52 04 PM](https://user-images.githubusercontent.com/66915274/197399021-29b21274-37c1-4fd9-8526-962969d1cce3.png)](https://user-images.githubusercontent.com/66915274/197399021-29b21274-37c1-4fd9-8526-962969d1cce3.png)

32 ◦ We will enter the name we want to give it. `LVMGroup` as indicated in the subject.

[![Screen Shot 2022-10-23 at 4 52 58 PM](https://user-images.githubusercontent.com/66915274/197399065-1ac8d80d-9e18-4b4a-a60f-11496e7de26d.png)](https://user-images.githubusercontent.com/66915274/197399065-1ac8d80d-9e18-4b4a-a60f-11496e7de26d.png)

33 ◦ We will select the partition where we want to create the group.

[![Screen Shot 2022-10-23 at 4 53 22 PM](https://user-images.githubusercontent.com/66915274/197399089-5ea5f48e-176c-4278-8b14-a13b7f5ee45c.png)](https://user-images.githubusercontent.com/66915274/197399089-5ea5f48e-176c-4278-8b14-a13b7f5ee45c.png)

34 ◦ Now we must create all the logical partitions. As we have to repeat the same actions several times, there are captures that will not be documented.

[![image](https://user-images.githubusercontent.com/66915274/197439138-889d6368-1875-402b-a094-bd146bb7cb8a.png)](https://user-images.githubusercontent.com/66915274/197439138-889d6368-1875-402b-a094-bd146bb7cb8a.png)

[![Screen Shot 2022-10-23 at 4 53 50 PM](https://user-images.githubusercontent.com/66915274/197399108-fb566eb4-664f-4509-8948-ab4ed04407b5.png)](https://user-images.githubusercontent.com/66915274/197399108-fb566eb4-664f-4509-8948-ab4ed04407b5.png)

35 ◦ We will start by choosing the group where we want them to be created. We select the only one available (the one we just created).

[![Screen Shot 2022-10-23 at 4 54 02 PM](https://user-images.githubusercontent.com/66915274/197399115-e7d3b313-763c-421c-a71d-850d318432e7.png)](https://user-images.githubusercontent.com/66915274/197399115-e7d3b313-763c-421c-a71d-850d318432e7.png)

36 ◦ The order of creation of the logical units will be the same as indicated in the subject, so we will start with root and end with var-log. Then we will select the name of the logical volume.

[![Screen Shot 2022-10-23 at 4 55 42 PM](https://user-images.githubusercontent.com/66915274/197399188-6ae8c83b-057d-498f-b112-9116079b0808.png)](https://user-images.githubusercontent.com/66915274/197399188-6ae8c83b-057d-498f-b112-9116079b0808.png)

37 ◦ Size, as indicated in the subject, will be 10g.

[![Screen Shot 2022-10-23 at 4 56 21 PM](https://user-images.githubusercontent.com/66915274/197399216-c65f43ca-fb8e-4d05-9212-24ad2ee87b39.png)](https://user-images.githubusercontent.com/66915274/197399216-c65f43ca-fb8e-4d05-9212-24ad2ee87b39.png)

38 ◦ We repeat the process for `swap`. We only change the name and size.

[![Screen Shot 2022-10-23 at 4 56 49 PM](https://user-images.githubusercontent.com/66915274/197399239-c26598cb-e7bb-474c-aece-90f043e1990f.png)](https://user-images.githubusercontent.com/66915274/197399239-c26598cb-e7bb-474c-aece-90f043e1990f.png)

[![Screen Shot 2022-10-23 at 4 57 26 PM](https://user-images.githubusercontent.com/66915274/197399278-c5cd5a9c-2ab1-42b9-8871-b58e9b33b4b6.png)](https://user-images.githubusercontent.com/66915274/197399278-c5cd5a9c-2ab1-42b9-8871-b58e9b33b4b6.png)

[![Screen Shot 2022-10-23 at 4 57 41 PM](https://user-images.githubusercontent.com/66915274/197399288-7ecf6adf-aaf5-46bf-959f-2159d19b7bbf.png)](https://user-images.githubusercontent.com/66915274/197399288-7ecf6adf-aaf5-46bf-959f-2159d19b7bbf.png)

[![Screen Shot 2022-10-23 at 4 58 11 PM](https://user-images.githubusercontent.com/66915274/197399310-fc6c397e-8257-4e06-8fba-ad35431c9b96.png)](https://user-images.githubusercontent.com/66915274/197399310-fc6c397e-8257-4e06-8fba-ad35431c9b96.png)

39 ◦ We repeat the process for `home`. We only change the name and size.

[![Screen Shot 2022-10-23 at 4 58 57 PM](https://user-images.githubusercontent.com/66915274/197399347-a815d58b-686e-4d9d-bb5c-34a7b54476ab.png)](https://user-images.githubusercontent.com/66915274/197399347-a815d58b-686e-4d9d-bb5c-34a7b54476ab.png)

[![Screen Shot 2022-10-23 at 4 59 07 PM](https://user-images.githubusercontent.com/66915274/197399355-28617029-c28c-4ca4-b56b-646e066cded6.png)](https://user-images.githubusercontent.com/66915274/197399355-28617029-c28c-4ca4-b56b-646e066cded6.png)

[![Screen Shot 2022-10-23 at 5 01 13 PM](https://user-images.githubusercontent.com/66915274/197399433-1e9c7110-9240-4982-9835-b026ed73171f.png)](https://user-images.githubusercontent.com/66915274/197399433-1e9c7110-9240-4982-9835-b026ed73171f.png)

[![Screen Shot 2022-10-23 at 5 04 34 PM](https://user-images.githubusercontent.com/66915274/197399610-247a7a35-0141-4c14-884e-7ecd07caa96d.png)](https://user-images.githubusercontent.com/66915274/197399610-247a7a35-0141-4c14-884e-7ecd07caa96d.png)

40 ◦ We repeat the process for `var`. We only change the name and size.

[![Screen Shot 2022-10-23 at 5 05 10 PM](https://user-images.githubusercontent.com/66915274/197399644-58da651c-f4ad-4d1e-b128-de87c92cc292.png)](https://user-images.githubusercontent.com/66915274/197399644-58da651c-f4ad-4d1e-b128-de87c92cc292.png)

[![Screen Shot 2022-10-23 at 5 05 30 PM](https://user-images.githubusercontent.com/66915274/197399662-32ab0a06-c14d-4a0e-ac80-cb0d12fc24eb.png)](https://user-images.githubusercontent.com/66915274/197399662-32ab0a06-c14d-4a0e-ac80-cb0d12fc24eb.png)

[![Screen Shot 2022-10-23 at 5 06 03 PM](https://user-images.githubusercontent.com/66915274/197399693-b49c2ffe-b21a-43c5-bd3f-160bc544b072.png)](https://user-images.githubusercontent.com/66915274/197399693-b49c2ffe-b21a-43c5-bd3f-160bc544b072.png)

41 ◦ We repeat the process for `srv`. We only change the name.

[![Screen Shot 2022-10-23 at 5 06 14 PM](https://user-images.githubusercontent.com/66915274/197399702-6d531de3-690d-458d-9a3b-bf6ceedd7cda.png)](https://user-images.githubusercontent.com/66915274/197399702-6d531de3-690d-458d-9a3b-bf6ceedd7cda.png)

[![Screen Shot 2022-10-23 at 5 06 39 PM](https://user-images.githubusercontent.com/66915274/197399724-0fdd75ad-e978-4468-8509-a62cdc4a3faf.png)](https://user-images.githubusercontent.com/66915274/197399724-0fdd75ad-e978-4468-8509-a62cdc4a3faf.png)

[![Screen Shot 2022-10-23 at 5 06 57 PM](https://user-images.githubusercontent.com/66915274/197399744-b82b1dcd-09c7-44cc-a2ab-b6079abcbb5a.png)](https://user-images.githubusercontent.com/66915274/197399744-b82b1dcd-09c7-44cc-a2ab-b6079abcbb5a.png)

[![Screen Shot 2022-10-23 at 5 07 13 PM](https://user-images.githubusercontent.com/66915274/197399757-94732b16-585e-4f7d-a20f-f7ef0814b4e7.png)](https://user-images.githubusercontent.com/66915274/197399757-94732b16-585e-4f7d-a20f-f7ef0814b4e7.png)

42 ◦ We repeat the process for `tmp`. We only change the name.

[![Screen Shot 2022-10-23 at 5 07 34 PM](https://user-images.githubusercontent.com/66915274/197399777-9d871f2a-856d-4b4d-ad18-1195001b0fdf.png)](https://user-images.githubusercontent.com/66915274/197399777-9d871f2a-856d-4b4d-ad18-1195001b0fdf.png)

[![Screen Shot 2022-10-23 at 5 07 46 PM](https://user-images.githubusercontent.com/66915274/197399792-0794ace5-c236-4f68-b023-bb471753eba2.png)](https://user-images.githubusercontent.com/66915274/197399792-0794ace5-c236-4f68-b023-bb471753eba2.png)

[![Screen Shot 2022-10-23 at 5 07 55 PM](https://user-images.githubusercontent.com/66915274/197399798-84a31102-6953-468b-85d4-0a248e98cb17.png)](https://user-images.githubusercontent.com/66915274/197399798-84a31102-6953-468b-85d4-0a248e98cb17.png)

[![Screen Shot 2022-10-23 at 5 08 19 PM](https://user-images.githubusercontent.com/66915274/197399827-5dfc8571-e82c-4a28-aae7-dc716fb6e77b.png)](https://user-images.githubusercontent.com/66915274/197399827-5dfc8571-e82c-4a28-aae7-dc716fb6e77b.png)

43 ◦ Finally, we repeat the process for `var-log`. We only change the name and size.

[![Screen Shot 2022-10-23 at 5 08 34 PM](https://user-images.githubusercontent.com/66915274/197399838-2cd49171-45dd-469a-887c-3ce99d84b7cd.png)](https://user-images.githubusercontent.com/66915274/197399838-2cd49171-45dd-469a-887c-3ce99d84b7cd.png)

[![Screen Shot 2022-10-23 at 5 08 40 PM](https://user-images.githubusercontent.com/66915274/197399841-04b75112-4d21-456c-bf50-8335839764e0.png)](https://user-images.githubusercontent.com/66915274/197399841-04b75112-4d21-456c-bf50-8335839764e0.png)

[![Screen Shot 2022-10-23 at 5 08 59 PM](https://user-images.githubusercontent.com/66915274/197399859-d706de2e-bb20-4a04-96db-4dd57b3778be.png)](https://user-images.githubusercontent.com/66915274/197399859-d706de2e-bb20-4a04-96db-4dd57b3778be.png)

[![Screen Shot 2022-10-23 at 5 09 28 PM](https://user-images.githubusercontent.com/66915274/197399886-a1e9ee69-78a4-4071-af99-2192d535c6cd.png)](https://user-images.githubusercontent.com/66915274/197399886-a1e9ee69-78a4-4071-af99-2192d535c6cd.png)

44 ◦ Once we have completed all the previous steps, we will finish the configuration of the logical volume manager.

[![Screen Shot 2022-10-23 at 5 09 51 PM](https://user-images.githubusercontent.com/66915274/197399904-c584fcdf-eb38-486f-af12-7374f1e04465.png)](https://user-images.githubusercontent.com/66915274/197399904-c584fcdf-eb38-486f-af12-7374f1e04465.png)

45 ◦ Now we can see how in the section where it shows us all our partitions and free space, all the logical partitions that we just created are already appearing. Good, we must configure all of them to select the file system that we want and the mount point indicated in the subject. Again we will go in order and select the first one that appears, which is `home`.

[![Screen Shot 2022-10-23 at 5 10 36 PM](https://user-images.githubusercontent.com/66915274/197399944-bccbe599-b80a-4abe-ac6c-d770447ea727.png)](https://user-images.githubusercontent.com/66915274/197399944-bccbe599-b80a-4abe-ac6c-d770447ea727.png)

46 ◦ Show us the configuration of the partition. We must choose a file system as it currently does not have one.

[![Screen Shot 2022-10-23 at 5 10 55 PM](https://user-images.githubusercontent.com/66915274/197399976-9b871bda-9425-4dbe-b8c9-25c8c6d6c811.png)](https://user-images.githubusercontent.com/66915274/197399976-9b871bda-9425-4dbe-b8c9-25c8c6d6c811.png)

47 ◦ Choose the Ext4 file system, it is the most commonly used file system in Linux distributions.

[![Screen Shot 2022-10-23 at 5 11 18 PM](https://user-images.githubusercontent.com/66915274/197400000-2e855fc9-10b1-4f3e-9c58-85b6ff02a4fb.png)](https://user-images.githubusercontent.com/66915274/197400000-2e855fc9-10b1-4f3e-9c58-85b6ff02a4fb.png)

48 ◦ Now we need to select the mount point.

[![Screen Shot 2022-10-23 at 5 11 44 PM](https://user-images.githubusercontent.com/66915274/197400023-387a70aa-b491-43c0-91d2-cb378da9fc75.png)](https://user-images.githubusercontent.com/66915274/197400023-387a70aa-b491-43c0-91d2-cb378da9fc75.png)

49 ◦ We select `home` as indicated in the subject.

[![Screen Shot 2022-10-23 at 5 11 54 PM](https://user-images.githubusercontent.com/66915274/197400040-e79cad4f-368b-4cee-9ec0-942f38b2f785.png)](https://user-images.githubusercontent.com/66915274/197400040-e79cad4f-368b-4cee-9ec0-942f38b2f785.png)

50 ◦ Once we have selected it, we will finish the configuration of the partition.

[![Screen Shot 2022-10-23 at 5 12 10 PM](https://user-images.githubusercontent.com/66915274/197400059-ab96f2c4-cd92-47cb-a9ee-61257537ee6a.png)](https://user-images.githubusercontent.com/66915274/197400059-ab96f2c4-cd92-47cb-a9ee-61257537ee6a.png)

51 ◦ Again, these steps can become very repetitive so I won't comment much. We repeat everything the same way (except for the mount point) for `root`.

[![Screen Shot 2022-10-23 at 5 13 36 PM](https://user-images.githubusercontent.com/66915274/197400135-c08444fe-e39d-45fa-a3b6-3c73db2a4935.png)](https://user-images.githubusercontent.com/66915274/197400135-c08444fe-e39d-45fa-a3b6-3c73db2a4935.png)

[![Screen Shot 2022-10-23 at 5 13 53 PM](https://user-images.githubusercontent.com/66915274/197400146-41ce0b0c-142c-46b4-a3c5-918676a3a852.png)](https://user-images.githubusercontent.com/66915274/197400146-41ce0b0c-142c-46b4-a3c5-918676a3a852.png)

[![Screen Shot 2022-10-23 at 5 14 08 PM](https://user-images.githubusercontent.com/66915274/197400155-92759327-5671-41f4-8104-dd1de4bc88cb.png)](https://user-images.githubusercontent.com/66915274/197400155-92759327-5671-41f4-8104-dd1de4bc88cb.png)

[![Screen Shot 2022-10-23 at 5 14 22 PM](https://user-images.githubusercontent.com/66915274/197400171-6fd04783-e833-4afd-a753-4b943133a4ab.png)](https://user-images.githubusercontent.com/66915274/197400171-6fd04783-e833-4afd-a753-4b943133a4ab.png)

[![Screen Shot 2022-10-23 at 5 14 39 PM](https://user-images.githubusercontent.com/66915274/197400182-780e1917-3f77-4986-b0e8-b50a90d75403.png)](https://user-images.githubusercontent.com/66915274/197400182-780e1917-3f77-4986-b0e8-b50a90d75403.png)

[![Screen Shot 2022-10-23 at 5 14 52 PM](https://user-images.githubusercontent.com/66915274/197400186-88da831a-c672-4ec0-a64c-0ad2808bb6c5.png)](https://user-images.githubusercontent.com/66915274/197400186-88da831a-c672-4ec0-a64c-0ad2808bb6c5.png)

52 ◦ Repeat the process for `srv` and change the mount point.

[![Screen Shot 2022-10-23 at 5 15 05 PM](https://user-images.githubusercontent.com/66915274/197400198-599b4aa3-a511-45d1-86b0-dd42da4c380f.png)](https://user-images.githubusercontent.com/66915274/197400198-599b4aa3-a511-45d1-86b0-dd42da4c380f.png)

[![Screen Shot 2022-10-23 at 5 15 31 PM](https://user-images.githubusercontent.com/66915274/197400218-e6b26eb7-7933-426f-a7cd-a791400ebdab.png)](https://user-images.githubusercontent.com/66915274/197400218-e6b26eb7-7933-426f-a7cd-a791400ebdab.png)

[![Screen Shot 2022-10-23 at 5 15 37 PM](https://user-images.githubusercontent.com/66915274/197400222-95107b34-8d28-4d4d-a74b-7de6c6a46d33.png)](https://user-images.githubusercontent.com/66915274/197400222-95107b34-8d28-4d4d-a74b-7de6c6a46d33.png)

[![Screen Shot 2022-10-23 at 5 15 44 PM](https://user-images.githubusercontent.com/66915274/197400227-20c13dc0-52cd-4c70-bf4e-531979c54a3e.png)](https://user-images.githubusercontent.com/66915274/197400227-20c13dc0-52cd-4c70-bf4e-531979c54a3e.png)

[![Screen Shot 2022-10-23 at 5 15 52 PM](https://user-images.githubusercontent.com/66915274/197400238-3b403294-74d1-4e63-aca7-7d83447ed5b8.png)](https://user-images.githubusercontent.com/66915274/197400238-3b403294-74d1-4e63-aca7-7d83447ed5b8.png)

[![Screen Shot 2022-10-23 at 5 16 04 PM](https://user-images.githubusercontent.com/66915274/197400249-035f6b9d-3716-4565-9776-aa0af49b3fd7.png)](https://user-images.githubusercontent.com/66915274/197400249-035f6b9d-3716-4565-9776-aa0af49b3fd7.png)

53 ◦ For `swap`, we will make an exception because the file system will be different. We select `swap`.

[![Screen Shot 2022-10-23 at 5 16 32 PM](https://user-images.githubusercontent.com/66915274/197400272-112b44ef-4996-438a-90b8-6620cdd7d2ff.png)](https://user-images.githubusercontent.com/66915274/197400272-112b44ef-4996-438a-90b8-6620cdd7d2ff.png)

54 ◦ At the time of selecting the file system, we leave it on `swap area`.

[![Screen Shot 2022-10-23 at 5 16 41 PM](https://user-images.githubusercontent.com/66915274/197400281-e12ee636-8696-4bee-9198-862b7d6be199.png)](https://user-images.githubusercontent.com/66915274/197400281-e12ee636-8696-4bee-9198-862b7d6be199.png)

55 ◦ Once the previous step is completed, we will finish the partition configuration.

[![Screen Shot 2022-10-23 at 5 16 59 PM](https://user-images.githubusercontent.com/66915274/197400297-8eed129d-0ec0-49a8-8b2a-dd0d04055f75.png)](https://user-images.githubusercontent.com/66915274/197400297-8eed129d-0ec0-49a8-8b2a-dd0d04055f75.png)

[![Screen Shot 2022-10-23 at 5 17 09 PM](https://user-images.githubusercontent.com/66915274/197400309-74e83209-4b2a-4e27-9a67-44373c1db362.png)](https://user-images.githubusercontent.com/66915274/197400309-74e83209-4b2a-4e27-9a67-44373c1db362.png)

56 ◦ Now we will do the same thing as before, but now we will do it with `tmp` and changing the mount point.

[![Screen Shot 2022-10-23 at 5 17 41 PM](https://user-images.githubusercontent.com/66915274/197400341-608516f6-0f5a-4cdd-83d8-c8fbd1635624.png)](https://user-images.githubusercontent.com/66915274/197400341-608516f6-0f5a-4cdd-83d8-c8fbd1635624.png)

[![Screen Shot 2022-10-23 at 5 17 49 PM](https://user-images.githubusercontent.com/66915274/197400346-e9647c7a-a9a2-4a0f-b439-a912247fb3f9.png)](https://user-images.githubusercontent.com/66915274/197400346-e9647c7a-a9a2-4a0f-b439-a912247fb3f9.png)

[![Screen Shot 2022-10-23 at 5 18 01 PM](https://user-images.githubusercontent.com/66915274/197400360-1816d06a-252e-4d41-b1a2-fc547961f353.png)](https://user-images.githubusercontent.com/66915274/197400360-1816d06a-252e-4d41-b1a2-fc547961f353.png)

[![Screen Shot 2022-10-23 at 5 18 08 PM](https://user-images.githubusercontent.com/66915274/197400370-0474b71f-c1c3-445f-ba02-088dc1c64ce3.png)](https://user-images.githubusercontent.com/66915274/197400370-0474b71f-c1c3-445f-ba02-088dc1c64ce3.png)

[![Screen Shot 2022-10-23 at 5 18 24 PM](https://user-images.githubusercontent.com/66915274/197400386-f66494c5-97b9-4bb9-8c75-5856d69d26cc.png)](https://user-images.githubusercontent.com/66915274/197400386-f66494c5-97b9-4bb9-8c75-5856d69d26cc.png)

[![Screen Shot 2022-10-23 at 5 18 40 PM](https://user-images.githubusercontent.com/66915274/197400405-4a368bfb-f862-4bbd-a33e-b87c3038d232.png)](https://user-images.githubusercontent.com/66915274/197400405-4a368bfb-f862-4bbd-a33e-b87c3038d232.png)

57 ◦ We repeat the process again for `var`, changing the mount point.

[![Screen Shot 2022-10-23 at 5 19 13 PM](https://user-images.githubusercontent.com/66915274/197400447-85bcad13-8083-4aec-acb2-fa467e5d4e33.png)](https://user-images.githubusercontent.com/66915274/197400447-85bcad13-8083-4aec-acb2-fa467e5d4e33.png)

[![Screen Shot 2022-10-23 at 5 19 21 PM](https://user-images.githubusercontent.com/66915274/197400452-aed22368-4889-4c04-bf60-5a06fb93944e.png)](https://user-images.githubusercontent.com/66915274/197400452-aed22368-4889-4c04-bf60-5a06fb93944e.png)

[![Screen Shot 2022-10-23 at 5 19 28 PM](https://user-images.githubusercontent.com/66915274/197400459-b6f59948-e804-414a-b41d-21d2f495fccc.png)](https://user-images.githubusercontent.com/66915274/197400459-b6f59948-e804-414a-b41d-21d2f495fccc.png)

[![Screen Shot 2022-10-23 at 5 19 36 PM](https://user-images.githubusercontent.com/66915274/197400462-788d29e5-7798-418a-8725-3cb8dd2849bd.png)](https://user-images.githubusercontent.com/66915274/197400462-788d29e5-7798-418a-8725-3cb8dd2849bd.png)

[![Screen Shot 2022-10-23 at 5 19 51 PM](https://user-images.githubusercontent.com/66915274/197400473-4508d9d6-481d-4f3a-9630-6c1eba7c5cc0.png)](https://user-images.githubusercontent.com/66915274/197400473-4508d9d6-481d-4f3a-9630-6c1eba7c5cc0.png)

[![Screen Shot 2022-10-23 at 5 20 00 PM](https://user-images.githubusercontent.com/66915274/197400482-1f8c147f-66d8-438b-866f-3e9eff75ef5e.png)](https://user-images.githubusercontent.com/66915274/197400482-1f8c147f-66d8-438b-866f-3e9eff75ef5e.png)

58 ◦ Finally, we repeat the process again for `var-log`. In this case, we will have to manually enter the mount point..

[![Screen Shot 2022-10-23 at 5 20 23 PM](https://user-images.githubusercontent.com/66915274/197400513-53b3f899-47f5-4cdb-ab4b-205b1d1bce31.png)](https://user-images.githubusercontent.com/66915274/197400513-53b3f899-47f5-4cdb-ab4b-205b1d1bce31.png)

[![image](https://user-images.githubusercontent.com/66915274/197602511-fa34155b-3244-4b0c-8054-2778edecfb16.png)](https://user-images.githubusercontent.com/66915274/197602511-fa34155b-3244-4b0c-8054-2778edecfb16.png)

[![image](https://user-images.githubusercontent.com/66915274/197602585-03b540af-5d7a-4364-b90a-559bac0cb2a2.png)](https://user-images.githubusercontent.com/66915274/197602585-03b540af-5d7a-4364-b90a-559bac0cb2a2.png)

[![image](https://user-images.githubusercontent.com/66915274/197602630-cc749189-9ac9-48bc-a595-dc33282840ec.png)](https://user-images.githubusercontent.com/66915274/197602630-cc749189-9ac9-48bc-a595-dc33282840ec.png)

[![image](https://user-images.githubusercontent.com/66915274/197602673-5c18be85-1b0f-430b-b507-66711b807115.png)](https://user-images.githubusercontent.com/66915274/197602673-5c18be85-1b0f-430b-b507-66711b807115.png)

[![image](https://user-images.githubusercontent.com/66915274/197602699-fddadd2d-c54d-4313-8165-a93db1249b26.png)](https://user-images.githubusercontent.com/66915274/197602699-fddadd2d-c54d-4313-8165-a93db1249b26.png)

[![image](https://user-images.githubusercontent.com/66915274/197602741-431bd866-1558-4735-bb34-ab57dc5745b7.png)](https://user-images.githubusercontent.com/66915274/197602741-431bd866-1558-4735-bb34-ab57dc5745b7.png)

59 ◦ Once we have completed all of the previous steps, we are almost finished. We must click 'finish partitioning' to save all of the changes to the disk.

[![image](https://user-images.githubusercontent.com/66915274/197602907-4a3ba459-1a5d-468e-81dc-5206403cf034.png)](https://user-images.githubusercontent.com/66915274/197602907-4a3ba459-1a5d-468e-81dc-5206403cf034.png)

60 ◦ We accept the message and the changes will be saved. Make sure that all of the partitions look the same as in the screenshot.

[![image](https://user-images.githubusercontent.com/66915274/197602944-13ca67b2-bcc5-476c-84dc-aadc5e1d3baf.png)](https://user-images.githubusercontent.com/66915274/197602944-13ca67b2-bcc5-476c-84dc-aadc5e1d3baf.png)

61 ◦ We select the option `No` because we do not need additional packages.

[![Captura de pantalla 2022-07-13 a las 20 05 42](https://user-images.githubusercontent.com/66915274/178801099-2dda24f5-0d46-4184-8c44-a8fe0bf46527.png)](https://user-images.githubusercontent.com/66915274/178801099-2dda24f5-0d46-4184-8c44-a8fe0bf46527.png)

62 ◦ We choose our Country.

<img  src="https://imgur.com/2l0qU8r.png">

63 ◦ We choose deb.debian.org because, considering our region, it is where we will have the best connection.

<img  src="https://imgur.com/w7Uc3Ch.png">


64 ◦ We will leave this option empty and click directly on `Continue`.

[![Captura de pantalla 2022-07-13 a las 20 17 24](https://user-images.githubusercontent.com/66915274/178803208-2969acae-3fa7-423e-8a3c-bb7c76eff824.png)](https://user-images.githubusercontent.com/66915274/178803208-2969acae-3fa7-423e-8a3c-bb7c76eff824.png)

65 ◦ We selected the option `No` because we do not want developers to see our statistics even though they are anonymous.

[![Captura de pantalla 2022-07-13 a las 20 21 54](https://user-images.githubusercontent.com/66915274/178803926-a4efbc70-f3e2-4e6c-9809-9152478d8237.png)](https://user-images.githubusercontent.com/66915274/178803926-a4efbc70-f3e2-4e6c-9809-9152478d8237.png)

66 ◦ To remove all software options, use the `Down Arrow` key to navigate through the list, press the `Spacebar` to deselect each option, and then press `Continue`.

[![Captura de pantalla 2022-07-13 a las 20 24 17](https://user-images.githubusercontent.com/66915274/178804377-e775b89e-93d4-482f-a4d0-0ef126f47719.png)](https://user-images.githubusercontent.com/66915274/178804377-e775b89e-93d4-482f-a4d0-0ef126f47719.png)

67 ◦ We will select `Yes` to install [GRUB boot](https://es.wikipedia.org/wiki/GNU_GRUB) on the hard drive.

[![Captura de pantalla 2022-07-13 a las 20 26 24](https://user-images.githubusercontent.com/66915274/178804771-ba16e0b7-9f06-4c5b-9451-0bfd65efd2bb.png)](https://user-images.githubusercontent.com/66915274/178804771-ba16e0b7-9f06-4c5b-9451-0bfd65efd2bb.png)

68 ◦ We will choose the device for the bootloader installation `/dev/sda (ata_VBOX_HARDDISK)`.

[![Captura de pantalla 2022-07-13 a las 20 35 46](https://user-images.githubusercontent.com/66915274/178806441-f1bf3159-4e09-4c9a-9102-b3261c9000d8.png)](https://user-images.githubusercontent.com/66915274/178806441-f1bf3159-4e09-4c9a-9102-b3261c9000d8.png)

69 ◦ We will press `Continue` to finish the installation.

[![Captura de pantalla 2022-07-13 a las 20 39 30](https://user-images.githubusercontent.com/66915274/178807102-e2a9722e-791f-48a0-ae35-b05b36a37ed2.png)](https://user-images.githubusercontent.com/66915274/178807102-e2a9722e-791f-48a0-ae35-b05b36a37ed2.png)

70 ◦ Once we have finished with the installation of Debian, we must set up our virtual machine.
[Click here to navigate to the virtual machine settings ⚙️](https://github.com/Miami05/Born2beRoot?tab=readme-ov-file#6-virtual-machine-setup)

### 10.2 Wordpress and Services Configuration🌐

Lighttpd<br>
🧠 What is Lighttpd❓ Lighttpd is a web server designed to be fast, secure, flexible, and standards-compliant. It is optimized for environments where speed is a top priority because it consumes less CPU and RAM than other servers.

1 ◦ Installation of Lighttpd packages.

<img  src="https://imgur.com/xgCNO8T.png">

2 ◦ We allow connections through port 80 with the command sudo ufw allow 80.

<img  src="https://imgur.com/JCCr3eo.png">

3 ◦ We check that we have actually allowed it. Port 80 and allow should appear.

<img  src="https://imgur.com/O6OiFby.png">

4 ◦ We add the rule that includes port 80. If you don't remember how to add rules in port forwarding.<br>
**Settings → Network → Advanced → Port forwarding → Replicate the capture**

<img  src="https://imgur.com/6keGD2p.png">

### WordPress

🧠 **What is Wordpress❓** It is a content management system focused on the creation of any type of website.

1 ◦ To install the latest version of WordPress we must first install wget and zip. To do this we will use the following command `sudo apt install wget zip`.

🧠 **What is wget❓** It is a command line tool used to download files from the web.

🧠 **What is zip❓** It is a command line utility for compressing and decompressing files in ZIP format.

<img  src="https://imgur.com/BwdDL3C.png">

2 ◦ Once we have installed the packages we must locate ourselves in the folder /var/www/ with the command cd we will access it cd /var/www/.

<img  src="https://imgur.com/DhF7JyO.png">

3 ◦ Once we are in the path /var/www/ we must download the latest version of WordPress. We will use the following command `sudo wget https://wordpress.org/latest.zip`

4 ◦ Unzip the file you just downloaded with the command `sudo unzip latest.zip`.

5 ◦ We will rename the folder html and call it html_old. sudo mv html/ html_old/.

<img  src="https://imgur.com/2SiWUi3>

6 ◦ Now we will rename the wordpress folder and call it html. sudo mv wordpress/ html

<img  src="https://imgur.com/ZnV1Av5.png">

7 ◦ Finally, we will set the permissions for the `html` folder using the command `sudo chmod -R 755 html`.

<img  src="https://imgur.com/vAg1JVe.png">

Here’s a breakdown of the command and what the permissions mean:

-   **`chmod`**: Stands for "change mode," the command used to modify file and directory permissions.
-   **`-R`**: Stands for "recursive," meaning the command will apply the permissions to the `html` directory and all its subdirectories and files.
-   **`755`**: The numeric mode representing the permissions:
    -   **7**: The owner has read (`4`), write (`2`), and execute (`1`) permissions.
    -   **5**: The group has read (`4`) and execute (`1`) permissions, but no write permissions.
    -   **5**: Others have read (`4`) and execute (`1`) permissions, but no write permissions.

### Mariadb
🧠 What is MariaDB❓ It is a database. It is used for various purposes, such as data warehousing, e-commerce, enterprise-level functions, and logging applications.

1 ◦ We will install the packages with the command `sudo apt install mariadb-server`.

<img  src="https://imgur.com/Qt7Efcf.png">

2 ◦ Because the default configuration leaves your MariaDB installation unsecure, we will use a script provided by the mariadb-server package to restrict access to the server and remove unused accounts. We will run the script with the following command `sudo mysql_secure_installation`. It will ask if we want to switch to Unix socket authentication. Since we already have a protected root account we will type `N`.

```
Switch to unix_socket authentication? → N
Change the root password? → N
Remove anonymous users? → Y
Disallow root login remotely? → Y
Remove test database and access to it? → Y
Reload privilege tables now? → Y
```

<img  src="https://imgur.com/iCxisJu.png">

<img  src="https://imgur.com/w4dNGaX.png">

<img  src="https://imgur.com/X7QBQ6z.png">

<img  src="https://imgur.com/Mk3I6ha.png">

<img  src="https://imgur.com/FBBqJe3.png">

<img  src="https://imgur.com/sDBw6Jp.png">

-   **Switch to unix_socket authentication?** Choose **N**. This means we’ll keep using the regular password method for accessing MariaDB, as we already have a secure root account set up.

-   **Change the root password?** Choose **N**. We don’t need to set a new root password right now. By default, MariaDB doesn’t have a root password until we set one, and root privileges need to be assigned separately.

-   **Remove anonymous users?** Choose **Y**.MariaDB starts with an anonymous user for testing, but it’s important to remove it for better security, especially before moving to a production environment.

-   **Disallow root login remotely?** Choose **Y**. This option prevents anyone from logging into the root account from outside your computer. This makes it safer by only allowing root access from the local machine.

-   **Remove test database and access to it?** Choose **Y**. This will delete the test database that comes with MariaDB and remove any users who had access to it, which is a good practice for cleaning up.

-   **Reload privilege tables now?** Choose **Y**. This command updates the system so that all the changes you’ve made take effect right away.

3 ◦ Once we have finished with the installation of mariadb we must create the database and the user for the WordPress. First we must access mariadb.

<img  src="https://imgur.com/slRkfsx.png">

4 ◦ We create a database for the WordPress. In my case I'm going to call it wp_database. I will do all this with the command `CREATE DATABASE wp_database;`.

5 ◦ To make sure that the database for WordPress has been created we can view all existing databases with the command `SHOW DATABASES;`.

<img  src="https://imgur.com/UE1j5Tc.png">

6 ◦ Next we need to create a user inside the database. We will use the command `CREATE USER 'ldurmish'@'localhost' IDENTIFIED BY '12345';`.

<img  src="https://imgur.com/BXcn8qZ.png">

7 ◦ We bind the new user to our database so that we grant him the necessary permissions to be able to work. We will use the command `GRANT ALL PRIVILEGES ON wp_database.* TO 'ldurmish'@'localhost';`.

<img  src="https://imgur.com/6cAcveT.png">

8 ◦ We update the permissions for the changes to take effect with the command `FLUSH PRIVILEGES;`

<img  src="https://imgur.com/PnvsWLl.png">

9 ◦ Once we have completed the previous step, we can exit mariadb.

<img  src="https://imgur.com/rtLWX5z.png">

PHP

🧠 What is PHP❓ It is a programming language. It is mainly used to develop dynamic web applications and interactive websites. PHP runs on the server side.

1 ◦ We install the necessary packages to be able to run web applications written in PHP language and that need to connect to a MySQL database. Run the following command `sudo apt install php-cgi php-mysql`.

<img  src="https://imgur.com/VU38xDh.png">