## Help Desk Ticket: GlobalProtect VPN Not Connecting

Date: 2025-05-29 
Category: Remote Access / VPN / Networking  
Environment: GlobalProtect VPN Client  

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### User Information

**Reported by:** Myself (Internal Staff)  
**Role:** Operations  
**VPN Tool:** GlobalProtect  
**OS:** macOS Ventura 13.x  

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Problem Description

While attempting to start my shift remotely, I was unable to connect to the corporate VPN using GlobalProtect. The client displayed “Connection Failed” and did not prompt for login credentials.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Initial Observations

1. Internet connection was stable and tested by loading external websites.
2. GlobalProtect client was stuck at “Connecting...” with no login prompt.
3. Portal address (`vpn.**redacted**.com`) was correct.
4. Issue appeared after macOS system update.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Troubleshooting Steps

1. **Restarted GlobalProtect** client and attempted reconnection.
2. Verified VPN portal was entered correctly in the client.
3. Checked Wi-Fi and firewall settings to ensure the connection wasn’t blocked.
4. Cleared saved credentials and quit the app.
5. Opened Terminal and restarted the GlobalProtect service manually:
   ```bash
   sudo launchctl unload /Library/LaunchAgents/com.paloaltonetworks.gp.pangps.plist
   sudo launchctl load /Library/LaunchAgents/com.paloaltonetworks.gp.pangps.plist

   ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Resolution

   After clearing cached credentials and manually restarting the GlobalProtect background service using Terminal, the login prompt reappeared. I successfully authenticated and connected to the VPN. Verified that I could access company systems and internal tools.

 ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
#### Tools/Systems Used
GlobalProtect VPN Client

**macOS Terminal**: launchctl unload / load commands

System Preferences (Network & Firewall settings)

 ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Lessons Learned
1. Cached credentials or a stuck background process can silently prevent GlobalProtect from loading the login screen.
2. Restarting the pangps service via Terminal can resolve connection failures without requiring a reinstall.
3. Keeping a simple bash script for restarting GlobalProtect can save time in future cases.
4. Always confirm portal address and external network connectivity first.




