# Account Lockout — Troubleshooting Lab

## Scenario
A user reports being unable to log in after repeated “Incorrect password” attempts.  
Eventually, the account becomes locked.

## Symptoms
- User unable to log in  
- “Incorrect password” errors  
- “Account is locked out” in user properties  
- Event Viewer showing failed logon attempts  

## Tools Used
- Event Viewer
- lusrmgr.msc (Local Users and Groups)
- Command Prompt
- Windows login screen

## Root Cause
Too many incorrect password attempts triggered the account lockout threshold.

## Resolution Steps

### 1. Reproduced the Issue
- Attempted incorrect passwords to intentionally trigger lockout.
- Confirmed the “Account is locked out” status.

### 2. Checked Event Viewer
- Opened Event Viewer (`eventvwr.msc`).
- Navigated to **Windows Logs → Security**.
- Located repeated failed logon events for the test user.

### 3. Checked User Account Status
- Opened **Local Users and Groups** (`lusrmgr.msc`).
- Found test user under *Users*.
- User properties showed **“Account is locked out.”**

### 4. Reset Password
Used Command Prompt (Admin):

```cmd
net user TestUser1 TempPass123
```

### 5. Unlocked the Account
- Unchecked “Account is locked out.”
- Saved changes.

### 6. Tested Login
- Logged in using the new password.
- Verified successful login.

## What I Learned
- How Windows handles account lockouts
- How Event Viewer logs failed sign-in attempts
- How to reset a password using GUI and command line
- How to unlock local accounts in lusrmgr
- Good practice for real help desk scenarios

## Screenshots (Will Be Added)
- Lockout screen
- Event Viewer logs showing failed attempts
- User properties with lockout enabled
- net user password reset command
- Successful login screen
