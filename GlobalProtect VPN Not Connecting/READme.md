# Help Desk Ticket: GlobalProtect VPN Not Connecting

Date: 2025-06-13  
Category: Remote Access / VPN / Networking  
Environment: GlobalProtect VPN Client  

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### User Information

**Reported by:** Myself (Internal Staff)  
**Role:** Member Support / Operations  
**VPN Tool:** GlobalProtect  
**OS:** macOS Ventura 13.x  

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Problem Description

While attempting to start my shift remotely, I was unable to connect to the corporate VPN using GlobalProtect. The client displayed “Connection Failed” and did not prompt for login credentials.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Initial Observations

- Internet connection was stable and tested by loading external websites.
- GlobalProtect client was stuck at “Connecting...” with no login prompt.
- Portal address (`vpn.companydomain.com`) was correct.
- Issue appeared after macOS system update.

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


