# 🛡️ ansible-server-hardening - Secure Your Server with Ease

## 🚀 Getting Started
Welcome to the ansible-server-hardening repository! This project offers a straightforward way to secure your Ubuntu or Debian servers. With automated scripts, you can enhance your server security without needing deep technical knowledge.

[![Download Latest Release](https://img.shields.io/badge/Download_Latest_Release-%20-blue)](https://github.com/Guilhermecmachado/ansible-server-hardening/releases)

## 📥 Download & Install
To get started, visit this page to download the latest release: [Download Here](https://github.com/Guilhermecmachado/ansible-server-hardening/releases). Here’s a simple guide on how to install and run the application:

1. **Visit the Releases Page**: Go to the link provided to find the latest version of the software.

2. **Choose the Right File**: Look for the file that matches your system. You will typically find versions labeled for Ubuntu or Debian. Click on the filename to start the download.

3. **Locate the Downloaded File**: After the download is complete, check your downloads folder. 

4. **Run the Script**:
   - For Ubuntu: Open your terminal, navigate to the download location, and run the script with:
     ```bash
     chmod +x ansible-server-hardening.sh
     ./ansible-server-hardening.sh
     ```
   - For Debian: Follow the same steps as above.

5. **Follow On-Screen Prompts**: The script will guide you through the setup process. It may ask for your password to proceed with the installation.

6. **Confirm Installation**: You will see confirmation messages in the terminal once the installation is successful.

## 🔍 Features
The ansible-server-hardening playbook includes several key features for enhancing server security:

- **User-Friendly Security Setup**: It eliminates complex security checks and streamlines the process.
- **UFW Configuration**: Easily manage your firewall settings with User Firewall (UFW) for better protection.
- **Fail2Ban Integration**: Protect your server from brute-force attacks automatically with Fail2Ban.
- **SSH Key-Based Authentication**: Improve your SSH security by removing password authentication and enabling key-based access.
- **Kernel ICMP Silencing**: Reduce the risk of network attacks by enabling kernel-level ICMP silencing.

## 🌐 Supported Platforms
This playbook supports:
- **Ubuntu 18.04 and later**
- **Debian 9 and later**

## 🛠️ Requirements
Before running the playbook, ensure your system meets the following requirements:

- An active Ubuntu or Debian server.
- Access to the terminal with graphical interface (optional).
- Basic knowledge of how to use the command line.

## 📃 Configuration
After installation, the playbook comes with default settings. You can adjust these to meet your specific security needs. The configuration file is located in the root directory of the installed software. Open it with any text editor.

## 👩‍💻 Usage
To use the playbook, simply run the script as described in the installation section. The script will automatically apply recommended security practices to your server. 

### Command Breakdown:

- **`./ansible-server-hardening.sh`**: Execute the playbook to begin hardening.
  
These commands streamline the security process, making your server safer with minimal effort.

## ⚙️ Troubleshooting
If you encounter issues, consider the following steps:

1. **Check Your Internet Connection**: Ensure you are connected to the internet, as the playbook may need to download some dependencies.
  
2. **Update Your System**: Ensure your operating system is up to date. You can run the following command:
   ```bash
   sudo apt update && sudo apt upgrade
   ```
  
3. **Consult Log Files**: If the playbook fails, check the log files in the `/var/log/` directory for error messages.

4. **Search for Help**: You can find common issues and solutions in the community forums or by reaching out for support.

## 📄 License
This project is licensed under the MIT License. You can use it freely, but please credit the original authors when applicable.

## 📚 Contributing
We welcome contributions to improve this project. If you have suggestions or want to report issues, feel free to open an issue or a pull request in the repository.

For detailed guidelines on contributing, please refer to the [CONTRIBUTING.md](https://github.com/Guilhermecmachado/ansible-server-hardening/blob/main/CONTRIBUTING.md) file.

## 📌 Additional Resources
- [Ansible Documentation](https://docs.ansible.com/)
- [UFW Documentation](https://help.ubuntu.com/community/UFW)
- [Fail2Ban Documentation](https://www.fail2ban.org/wiki/index.php/Main_Page)

For more information, updates, and community interaction, visit our repository frequently!

[![Visit Releases Page](https://img.shields.io/badge/Visit_Releases_%20%F0%9F%93%9A-blue)](https://github.com/Guilhermecmachado/ansible-server-hardening/releases)