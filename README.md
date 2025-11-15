# Gazebo Installation With ROS2 Rolling (Ubuntu 24.04)

This repository documents the setup process for running **Gazebo (Jetty)** with **ROS2 Rolling** on Ubuntu 24.04.3 (Noble).  
Since ROS2 Rolling and Gazebo Jetty are both in active development, compatibility depends heavily on distribution versions, end-of-life timelines, and system GPU capabilities.

## Important Notes

- Gazebo often does not run reliably inside VMware or VirtualBox virtual machines due to the need for dedicated GPU acceleration.  
  While it is possible to force-render using the CPU, performance is unstable and not recommended.
- This setup was validated on a system with **NVIDIA GeForce RTX 4060** using native installation (dual boot).  
  Dual-booting may affect system warranty depending on manufacturer policies.  
  Proceed with caution; I am not liable for any warranty loss or system issues arising from dual booting.
- Always verify the compatibility between:  
  - ROS2 distribution  
  - Gazebo version  
  - Ubuntu release  
  - GPU drivers  
- For Ubuntu 24.04.3 (Noble), **Gazebo Jetty** and **ROS2 Rolling** were used (as of 15 Nov 2025).

## Reference Documentation

ROS2 Rolling Release Info: https://docs.ros.org/en/rolling/Releases.html

Gazebo ↔ ROS2 Compatibility Matrix: https://gazebosim.org/docs/latest/ros_installation/

Gazebo ↔ Linux Distribution Compatibility: https://gazebosim.org/docs/latest/getstarted/

Ensure that your selected versions match the compatibility tables in the above documentation.

---

## System Information

- **OS:** Ubuntu 24.04.3 LTS (Noble)  
- **GPU:** NVIDIA GeForce RTX 4060  
- **ROS2 Version:** Rolling (development branch)  
- **Gazebo Version:** Jetty  
- **Tested as of:** 15 November 2025  
- **Installation Environment:** Native dual-boot (not a virtual machine)

---
# ROS2 Rolling Installation Guide (Ubuntu 24.04)

This document provides the complete setup steps for installing **ROS2 Rolling** on Ubuntu 24.04 (Noble).  
Reference: https://docs.ros.org/en/rolling/Installation/Ubuntu-Install-Debs.html

---

## 1. Set Locale

Ensure your system is using a UTF-8–supported locale.

Check current locale:
```
locale  # check for UTF-8
```
Install and configure UTF-8 locale:

```
sudo apt update && sudo apt install locales
sudo locale-gen en_US en_US.UTF-8
sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
export LANG=en_US.UTF-8
```
Verify the updated locale:

```
locale  # verify settings
```


---

## 2. Enable Required Repositories

ROS2 packages are distributed through custom APT repositories.

Enable the **Ubuntu Universe** repository:

```
sudo apt install software-properties-common
sudo add-apt-repository universe
```

Add the **ROS2 apt source**:
```
sudo apt update && sudo apt install curl -y
export ROS_APT_SOURCE_VERSION=$(curl -s https://api.github.com/repos/ros-infrastructure/ros-apt-source/releases/latest | grep -F "tag_name" | awk -F\" '{print $4}')
curl -L -o /tmp/ros2-apt-source.deb "https://github.com/ros-infrastructure/ros-apt-source/releases/download/${ROS_APT_SOURCE_VERSION}/ros2-apt-source_${ROS_APT_SOURCE_VERSION}.$(. /etc/os-release && echo ${UBUNTU_CODENAME:-${VERSION_CODENAME}})_all.deb"
sudo dpkg -i /tmp/ros2-apt-source.deb
```

This configures ROS repositories and keeps them updated automatically.

---

## 3. Install Development Tools (Optional)

If you plan to build packages or perform development work:
```
sudo apt update && sudo apt install ros-dev-tools
```

---

## 4. Install ROS2 Rolling

Update your package index:
```
sudo apt update
```

Upgrade your system to avoid dependency issues:
```
sudo apt upgrade
```

### Desktop Install (Recommended)

Includes RViz, tutorials, demos, and core ROS features:

```
sudo apt install ros-rolling-desktop #recommended for all around useage
```

### ROS-Base Install (Minimal)

Communication libraries and CLI tools. No GUI:

```
sudo apt install ros-rolling-ros-base
```

---

## 5. Setup Environment

Navigate to ROS installation:
```
cd /opt/ros
```
You can see the ros that you have on your device


Return to home:
```
cd #to go back 
```

Add ROS2 Rolling to your `.bashrc`:

```
gedit ~/.bashrc
```

Append the following line at the bottom:

```
source /opt/ros/rolling/setup.bash
```


Save and close.

### Multiple ROS Versions Note

If you have multiple ROS distributions installed:

- Comment out the source line for versions you do not want to use  
- Uncomment the one you want active  

Only one ROS environment should be sourced at a time.

---

## ROS2 is now installed

Open a new terminal or run:

```
source ~/.bashrc
```

You can verify your installation:

```
ros2 --version
```



---

## Steps for Installing Gazebo Jetty

(Instructions will be added here.)


---

## Purpose of This Repository

This repository serves as a reference for:

- Setting up ROS2 Rolling on Ubuntu 24.04  
- Installing Gazebo Jetty with proper compatibility  
- Documenting common pitfalls and environment requirements  
- Providing a reproducible template for others using similar configurations

The exact installation commands are intentionally left blank so they can be customized or updated as needed.

---

## Disclaimer

This guide reflects a personal setup process during a development period.  
Compatibility, installation commands, and system requirements may change over time.  
Use this document as a reference only.  
I am not responsible for system modifications, warranty loss, or compatibility issues arising from following this guide.

