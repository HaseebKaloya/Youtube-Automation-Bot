# 🐛 Troubleshooting Guide - KaloyaXploit YouTube Automation Suite

<div align="center">

![Troubleshooting](https://img.shields.io/badge/Support-Troubleshooting-orange?style=for-the-badge)
![Help](https://img.shields.io/badge/Need_Help-Read_This-green?style=for-the-badge)

**Quick solutions to common problems** 🛠️

[Authentication Issues](#-authentication-issues) • [Installation Problems](#-installation-problems) • [API Errors](#-api-errors) • [Performance Issues](#-performance-issues) • [Getting Help](#-getting-help)

</div>

## 🚨 Quick Emergency Fixes

### If the application won't start:
```bash
# 1. Reset authentication
rm token.json

# 2. Reinstall dependencies
pip install -r requirements.txt --force-reinstall

# 3. Try again
python src/youtube_automation_gui.py
```

### If you get API errors:
```bash
# Check your API quota
# Visit: https://console.cloud.google.com/apis/dashboard
```

---

## 🔐 Authentication Issues

### ❌ Problem: "Invalid credentials" or "Token expired"

**Symptoms:**
- Authentication fails repeatedly
- "Invalid credentials" error message
- Browser doesn't open for authentication

**Solutions:**

#### Solution 1: Reset Authentication
```bash
# Delete the token file and re-authenticate
rm token.json
python src/youtube_automation_gui.py
```

#### Solution 2: Check credentials.json
1. **Verify file location**: `credentials.json` should be in the main project folder
2. **Check file content**: Open `credentials.json` and ensure it contains valid JSON
3. **Re-download credentials**: Get a new file from [Google Cloud Console](https://console.cloud.google.com/)

#### Solution 3: Browser Issues
```bash
# If browser doesn't open, use this workaround:
# 1. Manually visit the authentication URL shown in terminal
# 2. Copy the authorization code
# 3. Paste it in the application
```

### ❌ Problem: "OAuth consent screen" warning

**Symptoms:**
- "This app isn't verified" warning
- Cannot proceed with authentication

**Solutions:**

#### Solution 1: Advanced Settings (Quick Fix)
1. On the warning screen, click **"Advanced"**
2. Click **"Go to [App Name] (unsafe)"**
3. Continue with authentication

#### Solution 2: Verify Your App (Permanent Fix)
1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Navigate to **"APIs & Services" > "OAuth consent screen"**
3. Set **"User Type"** to **"External"**
4. Add your email to **"Test users"**
5. **Publish the app**

### ❌ Problem: "Access blocked" or "Permission denied"

**Symptoms:**
- Google blocks the authentication attempt
- "Access blocked" error message

**Solutions:**

#### Solution 1: Check OAuth Scopes
1. Ensure you've enabled **YouTube Data API v3**
2. Required scopes should be automatically requested
3. Verify in Google Cloud Console under **"OAuth consent screen" > "Scopes"**

#### Solution 2: Account Permissions
1. Use a Google Account that owns a YouTube channel
2. Ensure the account has no restrictions
3. Try with a different Google Account

---

## 📦 Installation Problems

### ❌ Problem: "ModuleNotFoundError" or Import Errors

**Symptoms:**
- `ModuleNotFoundError: No module named 'customtkinter'`
- Various import errors when starting the application

**Solutions:**

#### Solution 1: Install Dependencies
```bash
# Basic installation
pip install -r requirements.txt

# If that fails, install individually:
pip install customtkinter
pip install google-auth
pip install google-auth-oauthlib
pip install google-api-python-client
pip install pillow
```

#### Solution 2: Python Version Check
```bash
# Check Python version
python --version

# If below 3.8, upgrade Python
# Download from: https://www.python.org/downloads/
```

#### Solution 3: Virtual Environment
```bash
# Create fresh virtual environment
python -m venv kaloya_env

# Activate it
# Windows:
kaloya_env\Scripts\activate
# Mac/Linux:
source kaloya_env/bin/activate

# Install requirements
pip install -r requirements.txt
```

### ❌ Problem: GUI Not Starting or Crashing

**Symptoms:**
- Application crashes immediately
- Blank window appears
- "TclError" or TKinter issues

**Solutions:**

#### Solution 1: Tkinter Installation
**Windows:**
- Tkinter is usually included with Python
- Reinstall Python from [python.org](https://python.org)

**Mac:**
```bash
# Install Python with Tkinter
brew install python-tk
# OR download from python.org (recommended)
```

**Linux:**
```bash
# Ubuntu/Debian
sudo apt update
sudo apt install python3-tk

# CentOS/RHEL
sudo yum install tkinter
```

#### Solution 2: Display Issues (Linux)
```bash
# Set display for remote sessions
export DISPLAY=:0

# For WSL (Windows Subsystem for Linux)
export DISPLAY=$(grep -m 1 nameserver /etc/resolv.conf | awk '{print $2}'):0
```

### ❌ Problem: Permission Errors

**Symptoms:**
- "Permission denied" when running scripts
- Cannot create files or directories

**Solutions:**

#### Solution 1: Run as Administrator (Windows)
1. Right-click Command Prompt
2. Select **"Run as administrator"**
3. Navigate to project and run again

#### Solution 2: Fix File Permissions (Linux/Mac)
```bash
# Make scripts executable
chmod +x src/youtube_automation_gui.py
chmod +x src/youtube_automation_cli.py

# Fix directory permissions
chmod 755 youtube-automation-suite
```

---

## 🎯 API Errors

### ❌ Problem: "quotaExceeded" Error

**Symptoms:**
- Actions stop working
- "quotaExceeded" error messages
- "The request cannot be completed because you have exceeded your quota"

**Solutions:**

#### Solution 1: Check Your Quota
1. Visit [Google Cloud Console](https://console.cloud.google.com/)
2. Go to **"APIs & Services" > "Dashboard"**
3. Look for **"YouTube Data API v3"** quota usage
4. Wait 24 hours for quota reset

#### Solution 2: Request Quota Increase
1. Go to [Google Cloud Console Quotas](https://console.cloud.google.com/iam-admin/quotas)
2. Filter for **"YouTube Data API v3"**
3. Select quotas to increase
4. Submit request (usually approved quickly)

### ❌ Problem: "API not enabled" Error

**Symptoms:**
- "The API is not enabled for this project"
- "Service not available"

**Solutions:**

#### Solution 1: Enable YouTube Data API
1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Navigate to **"APIs & Services" > "Library"**
3. Search for **"YouTube Data API v3"**
4. Click **"Enable"**

#### Solution 2: Check Project Selection
1. Ensure you're in the correct Google Cloud project
2. The project dropdown is in the top navbar
3. Select the project where you created credentials

### ❌ Problem: "forbidden" or "accessNotConfigured"

**Symptoms:**
- "The request is forbidden"
- "Access Not Configured"

**Solutions:**

#### Solution 1: OAuth Consent Screen
1. Go to **"APIs & Services" > "OAuth consent screen"**
2. Ensure app is **"Published"** (not "Testing")
3. Add required scopes
4. Add your email as test user if in testing mode

#### Solution 2: Verify Credentials
1. Ensure you're using **OAuth 2.0** credentials, not API keys
2. Credential type should be **"Desktop application"**
3. Download a new `credentials.json` file

---


### ❌ Problem: High Memory Usage

**Symptoms:**
- Application becomes slow over time
- System memory usage increases
- Eventually crashes on large datasets

**Solutions:**

#### Solution 1: Restart Application
- For long sessions, restart the application every few hours
- This clears memory and resets connections

#### Solution 2: Optimize Input Files
- Remove comments and empty lines from input files
- Use shorter URLs (video IDs instead of full URLs)
- Split large files into smaller ones

---

## 📁 File & Data Issues

### ❌ Problem: "File not found" Errors

**Symptoms:**
- "No such file or directory"
- Input files not found
- Cannot read configuration files

**Solutions:**

#### Solution 1: File Permissions
```bash
# Check file permissions
ls -la likes.txt

# Fix permissions if needed
chmod 644 likes.txt
chmod 644 comments.txt
chmod 644 channels.txt
```

#### Solution 2: File Encoding
```bash
# Ensure files are UTF-8 encoded
file -i likes.txt

# Convert if needed
iconv -f ISO-8859-1 -t UTF-8 likes.txt > likes_utf8.txt
```

### ❌ Problem: Input File Parsing Errors

**Symptoms:**
- "Invalid video ID"
- "Cannot parse input file"
- Skipped entries in logs

**Solutions:**

#### Solution 1: Validate File Format
**Correct format for likes.txt:**
```txt
https://www.youtube.com/watch?v=VIDEO_ID
https://youtu.be/VIDEO_ID
VIDEO_ID_ONLY
```

**Incorrect formats to avoid:**
```txt
# Comments should be on separate lines if supported
Video title here  # <- Don't mix URLs with text
Empty lines       # <- Remove empty lines
```

#### Solution 2: Clean Input Files
```bash
# Remove empty lines and trim spaces
sed -i '/^[[:space:]]*$/d' likes.txt
sed -i 's/^[[:space:]]*//;s/[[:space:]]*$//' likes.txt
```

#### Solution 3: Use Validation Script
```python
# Simple validation script
with open('likes.txt', 'r') as f:
    for line_num, line in enumerate(f, 1):
        line = line.strip()
        if line and not line.startswith('#'):
            # Add your validation logic here
            print(f"Line {line_num}: {line}")
```

---

## 🌐 Network Issues

### ❌ Problem: Connection Timeouts

**Symptoms:**
- "Connection timeout"
- "Network unreachable"
- Intermittent connectivity

**Solutions:**

#### Solution 1: Check Internet Connection
```bash
# Test basic connectivity
ping 8.8.8.8
ping www.googleapis.com

# Test YouTube API endpoint
curl -I https://www.googleapis.com/youtube/v3/videos
```

#### Solution 2: Proxy Configuration
```bash
# If behind corporate proxy, set environment variables
set HTTP_PROXY=http://proxy.company.com:8080
set HTTPS_PROXY=https://proxy.company.com:8080

# Or configure in application settings
```

#### Solution 3: Firewall Issues
1. Check if firewall is blocking Python
2. Add Python to firewall allowed applications
3. Temporarily disable firewall for testing

### ❌ Problem: SSL Certificate Errors

**Symptoms:**
- "SSL: CERTIFICATE_VERIFY_FAILED"
- Certificate validation errors
- Cannot establish secure connection

**Solutions:**

#### Solution 1: Update Certificates
**Mac:**
```bash
# Install certificates
/Applications/Python\ 3.*/Install\ Certificates.command
```

**Linux:**
```bash
# Update CA certificates
sudo update-ca-certificates
```

**Windows:**
- Reinstall Python from python.org (includes updated certificates)

#### Solution 2: Temporary Workaround (Not Recommended)
```python
# Only for testing - disables SSL verification
import ssl
ssl._create_default_https_context = ssl._create_unverified_context
```

---

### 📊 System Information Script

Create a diagnostic script to gather system info:

```python
# save as diagnose.py
import sys
import platform
import subprocess

print("=== System Diagnosis ===")
print(f"Python: {sys.version}")
print(f"Platform: {platform.platform()}")
print(f"Processor: {platform.processor()}")

try:
    import customtkinter
    print("✅ CustomTkinter: OK")
except ImportError as e:
    print(f"❌ CustomTkinter: {e}")

try:
    from google.auth import credentials
    print("✅ Google Auth: OK")
except ImportError as e:
    print(f"❌ Google Auth: {e}")

# Run and share output when asking for help
```

### 🔄 Reset Everything

If all else fails, complete reset:

```bash
# 1. Delete all generated files
rm -f token.json
rm -f *.log
rm -rf __pycache__
rm -rf src/__pycache__

# 2. Fresh virtual environment
python -m venv fresh_env
source fresh_env/bin/activate  # or fresh_env\Scripts\activate on Windows

# 3. Fresh install
pip install -r requirements.txt

# 4. New credentials
# Download new credentials.json from Google Cloud Console

# 5. Test
python src/youtube_automation_gui.py
```

---

## 🆘 Getting Help

### 📝 Before Asking for Help

Please gather this information:

1. **Error messages** (copy exactly)
2. **Python version** (`python --version`)
3. **Operating System** and version
4. **Steps to reproduce** the issue
5. **What you've already tried**

### 🎯 Where to Get Help

#### 1. GitHub Issues (Best for Bugs)
- [Create New Issue](../../issues/new)
- Use bug report template
- Include all requested information

#### 2. GitHub Discussions (Best for Questions)
- [Community Discussions](../../discussions)
- Search existing conversations
- Ask usage questions

#### 3. Documentation
- [Setup Guide](setup_guide.md)
- [Usage Guide](usage_guide.md)
- [API Reference](api_reference.md)

#### 4. Emergency Contact
- **Email**: kaloyaxploit@gmail.com
- **Response Time**: 24-48 hours

### 🎁 Providing Helpful Information

**Good bug report:**
```
OS: Windows 11
Python: 3.9.7
Error: "ModuleNotFoundError: No module named 'customtkinter'"
Steps:
1. pip install -r requirements.txt
2. python src/youtube_automation_gui.py
3. Got error immediately
Tried: Reinstalling, different Python version
```

**Bad bug report:**
```
"it doesn't work"
```

---

## ✅ Prevention Tips

### 🔧 Regular Maintenance
1. **Keep Python updated**
2. **Update dependencies regularly**
3. **Backup your configuration files**
4. **Monitor API quota usage**

### 🛡️ Best Practices
1. **Test with small datasets first**
2. **Use reasonable delays** (4+ seconds)
3. **Keep comments genuine and relevant**
4. **Monitor logs for warnings**
5. **Stay within API quotas**

### 📊 Monitoring
1. **Check Google Cloud Console weekly**
2. **Review application logs**
3. **Monitor success rates**
4. **Watch for pattern changes**

---

<div align="center">

## 🎉 Still Stuck?

**We're here to help!** 🤝

[**🐛 Create GitHub Issue**](../../issues/new) • [**📧 Email Support**](mailto:kaloyaxploit@gmail.com)

### ⭐ **Pro Tip**
**Star the repository** to get notified of updates and fixes!

[⬆ Back to Top](#-troubleshooting-guide---kaloyaxploit-youtube-automation-suite)

</div>

---

<div align="center">

*Last Updated: ${new Date().toLocaleDateString()}*  
*If this guide helped you, consider starring the repository! ⭐*

</div>



