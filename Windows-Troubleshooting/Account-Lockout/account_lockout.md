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
