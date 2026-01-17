# 🛡️ Hardening Server Automation (Ansible)

This project is designed for essential security hardening of Ubuntu/Debian-based servers. The script creates a new administrative user, sets up SSH key-based authentication, configures the UFW Firewall, and protects the server from brute-force attacks using Fail2Ban.

---

## 📋 Parameters Setup

For the script to work, you need to configure your **`inventory.json`**. This file contains both connection details and the configuration variables for the hardening process.

### 1. Configure `inventory.json`

The inventory file uses the following structure to manage host-specific settings:

| Parameter | Description |
| --- | --- |
| **`ansible_host`** | Public IP address of your server. |
| **`ansible_user`** | Initial user for connection (usually `root`). |
| **`ansible_password`** | Password for the initial user (needed for first-time access and sudo). |
| **`allow_ports`** | Array of ports to open in the Firewall (e.g., `[22, 5432, 4000]`). |
| **`target_user`** | The name of the new secure user to be created (e.g., `ArturOG`). |
| **`target_user_password_hash`** | **Critical:** The SHA-512 encrypted hash of the new user's password. |
| **`user_ssh_public_key`** | Your public SSH key (must be a single string starting with `ssh-rsa` or `ssh-ed25519`). |

**Example `inventory.json`:**

```json
{
  "all": {
    "hosts": {
      "production_server": {
        "ansible_host": "91.210.171.41",
        "ansible_user": "root",
        "ansible_password": "YourRootPassword123",
        "ansible_become_password": "YourRootPassword123",
        "allow_ports": [22, 5432, 4000],
        "target_user": "ArturOG",
        "target_user_password_hash": "$6$rounds=656000$...",
        "user_ssh_public_key": "ssh-rsa AAAAB3Nza..."
      }
    }
  }
}

```

> ⚠️ **Password Security**: Never use plain text for the `target_user_password_hash`.
> Generate a hash using: `python3 -c 'import crypt; print(crypt.crypt("your_password", crypt.mksalt(crypt.METHOD_SHA512)))'`.

---

## 🚀 Deployment

1. **Verify Connectivity:**
Check if Ansible can reach your server:
```bash
ansible all -i inventory.json -m ping

```


2. **Run the Hardening Playbook:**
Execute the security script:
```bash
ansible-playbook -i inventory.json security.yml

```



---

## 🛡️ What does this script do?

1. **User Management**: Creates a new administrator (`target_user`) and adds them to the `sudo` group.
2. **SSH Hardening**: Deploys your public key and **disables password authentication**. Root login is also disabled for security.
3. **Kernel-Level Security**: Disables ICMP (Ping) responses at the kernel level to hide the server from basic scanners.
4. **Fail2Ban**: Automatically bans IP addresses that show malicious signs (like repeated failed login attempts).
5. **UFW Firewall**: Implements a "Default Deny" policy. Only SSH and your specified `allow_ports` will be accessible.

---

## ⚠️ Warning!

Before running the playbook, double-check your **`user_ssh_public_key`**. Since the script disables password-based login, an incorrect SSH key will result in you being **permanently locked out** of your server. It is recommended to keep your current terminal session open until you verify the new login works in a separate window.

