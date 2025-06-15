## Help Desk Ticket: Two-Factor Authentication Not Working

Date:2025-06-10 
Category: Account Access / MFA 
Environment:Office365 (Microsoft Authenticator) 

#### Problem Description

Customer contacted support stating they were unable to complete two-factor authentication (2FA) when trying to log in to their account. They were receiving a timeout error or no notification on their mobile device.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Initial Observations

1. Confirmed that the user was entering the correct username and password.
2.  Verified that the user had 2FA enabled and was using Microsoft Authenticator.
3.  Asked the user if they had recently changed devices or reinstalled the app (they had).

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Troubleshooting Steps

1. Checked the user’s 2FA settings in the admin portal.
2. Noticed the device associated with their account was inactive.
3. Removed the old device from their authentication methods.
4. Sent a new MFA enrollment prompt.
5. Walked the user through re-registering their phone in Microsoft Authenticator.
6. Verified successful push notification and login.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Resolution

User successfully re-registered their device with the Authenticator app and completed the 2FA login without issues. Confirmed they could log in multiple times afterward.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Tools/Systems Used

1. Microsoft 365 Admin Center
2. Microsoft Authenticator App
3.  Phone call + screen walkthrough

 -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Lessons Learned

1. Many 2FA issues occur after phone changes or app reinstallations.
2. It's helpful to proactively ask about device changes before troubleshooting deeper.
3. Having a backup 2FA method (e.g., SMS or backup codes) could have prevented the lockout.

