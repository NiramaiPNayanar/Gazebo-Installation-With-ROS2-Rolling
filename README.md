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

ROS2 Rolling Release Info:  
https://docs.ros.org/en/rolling/Releases.html

Gazebo ↔ ROS2 Compatibility Matrix:  
https://gazebosim.org/docs/latest/ros_installation/

Gazebo ↔ Linux Distribution Compatibility:  
https://gazebosim.org/docs/latest/getstarted/

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

## Steps for Installing ROS2 Rolling

(Instructions will be added here.)


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

