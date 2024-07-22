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

10.  [Bonus⭐](#10-bonus)

	10.1 [Manual partition](#101-manual-partition)

	10.2 [Wordpress & services configuration 🌐](#102-wordpress--services-configuration)

	10.3 [Additional service ➕](#103-additional-service)

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