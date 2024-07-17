
#  Born2beRoot

Born2beRoot is a 42School project designed to build foundational skills in cybersecurity. It covers Linux system administration, network security, firewall configuration, user and group management, and secure service setups.

Through hands-on tasks, students learn to identify vulnerabilities, implement security measures, and ensure system integrity.

  

##  Index

1.  [Download Virtual Machine💿](#Download-Virtual-Machine-)

2.  [Choosing The Operating System💻](#Choosing-the-Operating-System-)

3.  [Download The Operating System💻](#Download-The-Operating-System-)

4.  [Virtual Machine Installation🛠️](#Virtual-Machine-Installation)

5.  [Installing Debian🌀](#Installing-Debian)

  

##  Download Virtual Machine ISO 💿

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

<img  width="836"  alt="Screenshot from 2024-07-16 16-53-38"  src="https://imgur.com/5R3uOrL.png">

2 ◦ Click on the New command on the top

<img  width  ="836"  src="https://github.com/Vikingu-del/Born2beRoot/raw/main/photos/installation/newVm.png">

3 ◦ We must choose a name for the machine and the folder which will locate it. IMPORTANT Store the machine created inside the sgoinfre folder located in your campus server; this is important because we will run out of memory space in our session and the installation will fail. (Ask your staff if you can't find it)

<img  width="836"  alt="Screenshot from 2024-07-16 16-50-55"  src="https://imgur.com/mnuOSLW.png">

4 ◦ Now we have to set up the memory size we want to use for our VM. You are free to choose How much memory you want to use from your computer but I would suggest that 1024MB is enough for this project.

<img  width="836"  alt="Screenshot from 2024-07-16 16-51-34"  src="https://imgur.com/qf8XQhX.png">  

5 ◦ Now the next prompts are asking to set up a virtual Hard disk. In the VirtualBox setup process, ensure to select 'Dynamically allocated' for storage on the physical hard disk. This option allows the virtual hard disk file to grow in size as needed, optimizing disk space usage. Avoid checking the option to pre-allocate the full size, as it may lead to unnecessary disk space allocation."

<img  width="836"  alt="Screenshot from 2024-07-16 16-51-44"  src="https://imgur.com/bYD3HUj.png">

6 ◦ Now click Finish.

<img  width="836"  alt="Screenshot from 2024-07-16 16-51-50"  src="https://imgur.com/t5pZMVq.png">

7 ◦ It might seem that we have already finish the installation , but there's still some steps to do. Click on Settings.

<img  width="836"  alt="Screenshot from 2024-07-16 16-51-50"  src="https://imgur.com/x1m7OYH.png">  

8 ◦ Then click on Storage.

<img  width="836"  alt="Screenshot from 2024-07-16 16-51-50"  src="https://imgur.com/K79b0UK.png">

9 ◦ Click on the blue disk icon, then select 'Choose a disk file', and finally, select the Debian ISO file that you downloaded.

<img  width="836"  alt="Screenshot from 2024-07-16 16-51-50"  src="https://imgur.com/WU5YJhb.png">
  
10 ◦ After that Click OK.

<img  width="836"  alt="Screenshot from 2024-07-16 16-51-50"  src="https://imgur.com/4IMXgcJ.png">

11 ◦ After completing all the steps, click the 'Start' button to launch your new virtual machine.

<img  width="836"  alt="Screenshot from 2024-07-16 16-51-50"  src="https://imgur.com/K72dUEL.png">

12 ◦ If it show this error.

<img  width="836"  alt="Screenshot from 2024-07-16 16-51-50"  src="https://imgur.com/e0eXvOy.png">

13 ◦ Navigate to Settings, then General, and ensure that the Version is specified as Other/Unknown 64-bit.

<img  width="836"  alt="Screenshot from 2024-07-16 16-51-50"  src="https://imgur.com/Grt79wF.png">

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
