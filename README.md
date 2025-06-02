# cs-task4
windows firewall defender
# 🔒 Windows Firewall Port Control

This guide explains how to **block** and **unblock** specific ports using **Windows Defender Firewall** via both **GUI** and **Command Line (netsh)** tools.

---

## 🧱 Block a Port Using Windows Firewall

### ✅ Method 1: Using Windows Firewall (GUI)

1. Open `Control Panel` → `Windows Defender Firewall`.
2. Click on **Advanced Settings** (left panel).
3. Choose **Inbound Rules** → **New Rule...**
4. Select **Port** and click **Next**.
5. Choose **TCP** or **UDP**, enter the port number (e.g., `443`), and click **Next**.
6. Select **Block the connection** and proceed.
7. Apply the rule to **Domain**, **Private**, and **Public** as needed.
8. Name the rule (e.g., `Block HTTPS`) and click **Finish**.

---

### ✅ Method 2: Using Command Line (`netsh`)

**To block port 443 (HTTPS)**:

```cmd
netsh advfirewall firewall add rule name="Block Port 443" dir=in action=block protocol=TCP localport=443
To verify the rule:

cmd
netsh advfirewall firewall show rule name="Block Port 443"
🔓 Unblock a Port
🧼 Remove the rule via GUI
Open Advanced Settings in Windows Firewall.

Go to Inbound Rules.

Find your rule (Block Port 443), right-click and choose Delete or Disable.

🧼 Remove the rule via netsh:
cmd
Copy
Edit
netsh advfirewall firewall delete rule name="Block Port 443"

⚠️ Notes
Inbound rules block incoming traffic. Use Outbound Rules to block outgoing connections.

Always test rules after applying.

Administrator privileges are required for creating/deleting firewall rules.
