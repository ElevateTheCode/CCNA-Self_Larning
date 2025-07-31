# Banner Message Configuration

## What is a Banner?
A banner is a message displayed to users who are trying to access a Cisco device. It can be used for security purposes, such as to warn unauthorized users that access is restricted.

## Banner Types
1.  **MOTD (Message of the Day) Banner:** Displayed to all users before they log in. This is the most common banner type.
2.  **Login Banner:** Displayed after a user enters a password but before they get to the prompt.
3.  **Exec Banner:** Displayed when a user enters privileged EXEC mode.

## Configuration Example
This example shows how to configure a simple MOTD banner.

Router(config)# banner motd #
Enter TEXT message. End with the character '#'.

WARNING: Unauthorized access is prohibited *

Your activity may be monitored.   *

- `banner motd #`: The `banner motd` command starts the configuration.
- The `#` is a delimiter character. You can use any character that is not in your message. You must use the same character at the end of the message to terminate it.

## Verification
To see the banner, simply log out and log back into the device via the console or SSH. The 
