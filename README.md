# Born2beRoot
Born2beRoot is a 42School project designed to build foundational skills in cybersecurity. It covers Linux system administration, network security, firewall configuration, user and group management, and secure service setups. 
Through hands-on tasks, students learn to identify vulnerabilities, implement security measures, and ensure system integrity.

## Index
1. [Download Virtual Machine💿](#Download-Virtual-Machine-)
2. [Choosing The Operating System💻](#Choosing-the-Operating-System-)
3. [Download The Operating System💻](#Download-The-Operating-System-)
4. [Virtual Machine Installation🛠️](#Virtual-Machine-Installation)

## Download Virtual Machine ISO 💿
If you haven't installed VirtualBox yet, you can download it from the official [VirtualBox website](https://www.virtualbox.org).
VirtualBox is essential for setting up and running the virtual machine that will host the operating system we will be working with.

## Choosing The Operating System 💻

### Debian

#### Stability and Reliability:
- Known for its robust stability and reliability, ideal for server environments.
- Well-established release cycle with long-term support options.

#### Community Support:
- Large and active community with extensive documentation and resources.
- Suitable for both beginners and experienced users in system administration.

#### Ease of Use:
- User-friendly package management system (APT) simplifies software installation and updates.
- Comprehensive documentation aids in setup and troubleshooting.

#### Security Features:
- Strong focus on security with features like SELinux and AppArmor.
- Regular security updates and patches ensure system integrity.

#### Flexibility and Compatibility:
- Versatile for various applications including servers, desktops, and embedded systems.
- Wide compatibility with diverse hardware and software configurations.

### Rocky Linux

#### Enterprise Focus:
- Developed as a stable and secure distribution, aiming to replace CentOS in enterprise environments.
- Follows RHEL closely, ensuring compatibility with enterprise applications.

#### Community and Support:
- Growing community particularly among former CentOS users.
- Offers enterprise-level support options through third-party vendors.

#### Compatibility with CentOS/RHEL:
- Designed to be a drop-in replacement for CentOS, maintaining compatibility with RHEL repositories and workflows.
- Suitable for organizations requiring RHEL-like features without the associated costs.

#### Security and Stability:
- Built with enterprise-grade security features like SELinux and strict adherence to stability.
- Long-term support and predictable release cycles ensure reliability for critical systems.

#### Deployment and Scalability:
- Optimized for large-scale deployments and mission-critical applications.
- Provides tools and support for seamless scalability in enterprise environments.

## Bonus Part Consideration

If you decide to pursue the bonus part of the project, Debian provides several advantages:

- **Stable Platform:** Debian offers a stable environment, ensuring reliability for setting up additional services such as WordPress or custom services.

- **Availability of Packages:** With over 50,000 packages in its repository, Debian provides ample software choices for installing and configuring additional services to expand the project's scope.

- **Community and Documentation:** The extensive Debian community and documentation make it easier to find support and guidance when setting up and managing additional services, enhancing the project's scalability and customization.

## Download The Operating System 💻

### Download Debian:

- **Official Website:** You can download Debian from [Debian's official download page](https://www.debian.org/download).

### Download Rocky
- **Official Website:** You can download Rocky from [Rocky's official download page](https://rockylinux.org/download).
    And choose Boot ISO

## Virtual Machine Installation
1 ◦ Open Oracle VirtualBox
<img width="836" alt="Screenshot from 2024-07-16 16-53-38" src="https://i.imgur.com/5R3uOrL.png">

2 ◦ Click on the New command on the top 
![New VM](https://github.com/Vikingu-del/Born2beRoot/raw/main/photos/installation/newVm.png)

3 ◦ We must choose a name for the machine and the folder which will locate it. IMPORTANT Store the machine created inside the sgoinfre folder located in your campus server; this is important because we will run out of memory space in our session and the installation will fail. (Ask your staff if you can't find it)
