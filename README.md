
#  Born2beRoot

Born2beRoot is a 42School project designed to build foundational skills in cybersecurity. It covers Linux system administration, network security, firewall configuration, user and group management, and secure service setups.

Through hands-on tasks, students learn to identify vulnerabilities, implement security measures, and ensure system integrity.

  

##  Index

1.  [Download Virtual Machine💿](#Download-Virtual-Machine)

2.  [Choosing The Operating System💻](#Choosing-the-Operating-System-)

3.  [Download The Operating System💻](#Download-The-Operating-System-)

4.  [Virtual Machine Installation🛠️](#Virtual-Machine-Installation)

5.  [Installing Debian🌀](#Installing-Debian)
6. [Virtual Machine Setup⚙️](#Virtual-Machine-Setup)
7. [Script 🚨]
	7.1 [Total result of the script 🆗]
8. [Crontab ⏰]
9. [Signature.txt 📝]
10. [Bonus ⭐]
    10.1 [Manual partition]
	10.2 [Wordpress & services configuration 🌐]
	10.3 [Aditional service ➕]
11. [Correction sheet ✅](https://github.com/gemartin99/Born2beroot-Tutorial/blob/main/README_EN.md#9--correction-
	11.1 [Evaluation answers 💯]
    11.2 [Evaluation commands ⌨️] 

##  Download Virtual Machine💿

If you haven't installed VirtualBox yet, you can download it from the official [VirtualBox website](https://www.virtualbox.org).

VirtualBox is essential for setting up and running the virtual machine that will host the operating system we will be working with.

  

##  Choosing The Operating System 💻

  

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

  

##  Download The Operating System 💻

  

###  Download Debian:

  

-  **Official Website:** You can download Debian from [Debian's official download page](https://www.debian.org/download).

  

###  Download Rocky

-  **Official Website:** You can download Rocky from [Rocky's official download page](https://rockylinux.org/download).

And choose Boot ISO

  

##  Virtual Machine Installation

1 ◦ Open Oracle VirtualBox

2 ◦ Click on the New command on the top

<img  width  ="836"  src="<img  width="836"  alt="Screenshot from 2024-07-16 16-53-38"  src="https://github.com/Vikingu-del/Born2beRoot/raw/main/photos/installation/newVm.png">">

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

  
##  Installing Debian🌀

  

-  **Hey there! Your eyesight is important. 👀 Enlarge the window for a better view:**

1 ◦ It will have the view like below. To have a larger view for your eyes, right click with your mouse, choose the option Virtual Screen 1 and scale it to 200%. After choose the install option since we will use it without Graphical Interface.

<img  width="836"  src="https://user-images.githubusercontent.com/66915274/178788620-61064b58-0c0c-4f48-815e-60b4a8eaecae.png">

2 ◦ The language selection for the machine during installation, including the default setting, is now your choice. Please choose `English` or any other preferred language.
<img  width="836"  src="https://user-images.githubusercontent.com/66915274/178789949-4fe83ac8-23b8-4f82-a034-a6d5e81d4f17.png">

3 ◦ It's time to select the country. If your is not on the present list go to `Other`.
<img  width="836"  src="https://github.com/Vikingu-del/Born2beRoot/raw/main/photos/installation/Country.png
">

4 ◦ Time to select continent. In our case we will select `Europe` 🇪🇺.
<img  width="836"  src="https://github.com/Vikingu-del/Born2beRoot/raw/main/photos/installation/europe.png">

5 ◦  Now we select the country. In my case is Germany 🇩🇪
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

16 ◦ Select Guied - use entire disk and set up encrypted LVM. ⚠️❗️ If you want to do the bonus select Manual and then click here ❗️⚠️
<img  width="836"  src="https://user-images.githubusercontent.com/66915274/178795367-b82018de-edc8-47d3-8cd6-b90c5e3be2fa.png">

17 ◦ Select the disk where you want to create the partition (only one disk should be displayed).
<img  width="836"  src="https://user-images.githubusercontent.com/66915274/178796481-29ef7ebc-0518-40f0-9429-3f43316b35d3.png">

18 ◦ After choosing the disk, proceed to create the partition as described in the subject. To do this correctly, select the second option `Separate /home partition`.
<img  width="836"  src="https://imgur.com/cwY7P0j.png">

19 ◦ We choose option `Yes` so the changes will be writen in the disk and so we can set the logical volume manager (LVM).
<img  width="836"  src="https://user-images.githubusercontent.com/66915274/178797258-8c34bc31-16a7-4aef-8406-cecc21fdf028.png">

19 ◦ We click on `Cancel` the erasing of the data is not required.
<img  width="836"  src="https://user-images.githubusercontent.com/66915274/178797666-78cdf892-1a83-4c68-8f85-0d5440cd4854.png">

20 ◦ Once again, select a password for encrypting the `LVM`. As mentioned earlier, you'll need to repeat this process, so it's advisable to write it down. You can use the same password as before.
<img  width="836"  src="https://imgur.com/DSWYNrL.png">

21 ◦ Repeat  the password we just set.
<img  width="836"  src="https://imgur.com/VXGHUeh.png">

22 ◦In this step, we must input the required amount of volume group to use during the guided partitioning. We can enter `max` or the total available memory, which in this case is `12.4 GB`.
<img  width="836"  src="https://user-images.githubusercontent.com/66915274/178799165-c6b05fd2-86ad-45b7-a026-9ee169eda5d5.png">

23 ◦ To wrap the partitioning and write the changes in the disk we choose the option `Finish partitioning and write changes to disk`.
<img  width="836"  src="https://imgur.com/ThEB4H7.png">

24 ◦ We choose the option `Yes` and then we confirm that we do not want more changes.
<img  width="836"  src="https://imgur.com/ho1HF2V.png">

25 ◦ We select the option `No` since additional packages are not required and we don't need them.
<img  width="836"  src="https://user-images.githubusercontent.com/66915274/178801099-2dda24f5-0d46-4184-8c44-a8fe0bf46527.png">

26 ◦ We choose our Country.
<img  width="836"  src="https://imgur.com/xVZHPcR.png">

27 ◦ We choose `deb.debian.org` as is the recommended by Debian itself.
<img  width="836"  src="https://imgur.com/w7Uc3Ch.png">

28 ◦ We will left this option blank and we click on `Continue`.
<img  width="836"  src="https://user-images.githubusercontent.com/66915274/178803208-2969acae-3fa7-423e-8a3c-bb7c76eff824.png">

29 ◦ We select the option `No` as we want to remain out of the statistics.
<img  width="836"  src="https://user-images.githubusercontent.com/66915274/178803926-a4efbc70-f3e2-4e6c-9809-9152478d8237.png">

30 ◦ We will leave all software choices blank by navigating with the `Down Arrow` key and selecting with the `Space Bar`, then click `Continue`.
<img  width="836"  src="https://user-images.githubusercontent.com/66915274/178804377-e775b89e-93d4-482f-a4d0-0ef126f47719.png">

31 ◦ We select `Yes` for install [GRUB boot](https://es.wikipedia.org/wiki/GNU_GRUB) in the hard disk.
<img  width="836"  src="https://user-images.githubusercontent.com/66915274/178804771-ba16e0b7-9f06-4c5b-9451-0bfd65efd2bb.png">

32 ◦ We will choose the device `/dev/sda (ata_VBOX_HARDDISK)` for the installation for boot loader.
<img  width="836"  src="https://user-images.githubusercontent.com/66915274/178806441-f1bf3159-4e09-4c9a-9102-b3261c9000d8.png">

<img  width="836"  src="https://user-images.githubusercontent.com/66915274/178807102-e2a9722e-791f-48a0-ae35-b05b36a37ed2.png">

## Virtual Machine Setup⚙️
