# 🛠️ Complete Setup Guide - KaloyaXploit YouTube Automation Suite

<div align="center">

![Setup Guide](https://img.shields.io/badge/Guide-Step--by--Step-blue?style=for-the-badge)
![Time Required](https://img.shields.io/badge/Time-15--20_Minutes-green?style=for-the-badge)

**From zero to automation in under 20 minutes** ⏱️

[Quick Setup](#-quick-setup-5-minutes) • [Detailed Setup](#-detailed-setup-15-minutes) • [Troubleshooting](#-troubleshooting) • [Next Steps](#-next-steps)

</div>

## 🎯 Overview

This guide will walk you through setting up the KaloyaXploit YouTube Automation Suite from scratch. Whether you're a beginner or experienced user, follow these steps to get started quickly.

### 📋 What You'll Need

| Requirement | Details |
|-------------|---------|
| **Computer** | Windows, Mac, or Linux |
| **Python** | Version 3.8 or higher |
| **Internet** | For installation and API access |
| **Google Account** | With YouTube channel access |
| **Time** | 15-20 minutes |

---

## ⚡ Quick Setup (5 Minutes)

### For experienced users who want to get started fast:

```bash
# 1. Download and extract the software
# 2. Open terminal/command prompt in the folder
cd youtube-automation-suite

# 3. Install dependencies
pip install -r requirements.txt

# 4. Get Google API credentials (see next section)
# 5. Run the application
python src/youtube_automation_gui.py
That's it! If you're familiar with Python and APIs, you're ready to go.

🐢 Detailed Setup (15 Minutes)
Step 1: Download the Software
Option A: Using Git (Recommended)
bash
# Open terminal/command prompt and run:
git clone https://github.com/KaloyaXploit/youtube-automation-suite.git
cd youtube-automation-suite
Option B: Download ZIP
Go to the GitHub repository

Click the green "Code" button

Select "Download ZIP"

Extract the ZIP file to your preferred location

Open terminal/command prompt in the extracted folder

Step 2: Install Python
Check if Python is Already Installed
bash
python --version
# OR
python3 --version
If you see Python 3.8 or higher, you're good! If not:

Windows Installation
Visit python.org

Download Python 3.8 or higher

Important: During installation, check "Add Python to PATH"

Run the installer

Verify installation: Open new Command Prompt and type python --version

Mac Installation
bash
# Using Homebrew (recommended)
brew install python

# Or download from python.org
Linux Installation
bash
# Ubuntu/Debian
sudo apt update
sudo apt install python3 python3-pip

# CentOS/RHEL
sudo yum install python3 python3-pip
Step 3: Install Dependencies
Basic Installation
bash
# From the project folder, run:
pip install -r requirements.txt
If You Encounter Issues
bash
# Install packages individually:
pip install customtkinter
pip install google-auth
pip install google-auth-oauthlib
pip install google-api-python-client
pip install pillow
pip install requests
Using Virtual Environment (Recommended)
bash
# Create virtual environment
python -m venv kaloya_env

# Activate it
# Windows:
kaloya_env\Scripts\activate
# Mac/Linux:
source kaloya_env/bin/activate

# Install requirements
pip install -r requirements.txt
Step 4: Google API Setup 🔐
This is the most important step! Follow carefully:

1. Create Google Cloud Project
Go to Google Cloud Console

Click the project dropdown (top left)

Click "New Project"

Name it: YouTube-Automation-Suite

Click "Create"

https://img.shields.io/badge/Step-1_Create_Project-blue

2. Enable YouTube Data API
In your new project, go to "APIs & Services" > "Library"

Search for "YouTube Data API v3"

Click on the result

Click "Enable"

https://img.shields.io/badge/Step-2_Enable_API-green

3. Create OAuth 2.0 Credentials
Go to "APIs & Services" > "Credentials"

Click "Create Credentials" > "OAuth 2.0 Client ID"

Application type: "Desktop Application"

Name: KaloyaXploit Automation

Click "Create"

https://img.shields.io/badge/Step-3_Create_Credentials-orange

4. Download Credentials File
Click the download button (looks like a down arrow) next to your new OAuth client

Save the file as credentials.json

Place this file in your project root folder

https://img.shields.io/badge/Step-4_Download_File-red

5. Configure OAuth Consent Screen
Go to "APIs & Services" > "OAuth consent screen"

User Type: "External"

Fill in required app information:

App name: KaloyaXploit YouTube Automation

User support email: Your email

Developer contact information: Your email

Add scopes: ".../auth/youtube.force-ssl" (should be auto-added)

Add test users: Add your email address

Click "Save and Continue" through all steps

Publish the app

Step 5: First Run & Authentication
Launch the Application
bash
# GUI Version (Recommended for beginners)
python src/youtube_automation_gui.py

# CLI Version (For advanced users)
python src/youtube_automation_cli.py --help
First-Time Authentication
The application will open a browser window

Sign in with your Google account (the one with YouTube access)

You'll see a permissions screen - click "Continue"

You might see "This app isn't verified" - click "Advanced" > "Go to [App Name] (unsafe)"

Click "Allow" to grant permissions

You'll be redirected to a success page

Return to the application

🎉 Congratulations! You should now see the main interface.

Step 6: Prepare Your Data Files
Create these files in your project folder:

❤️ likes.txt - Videos to Like
txt
# Add YouTube URLs or video IDs (one per line)
https://www.youtube.com/watch?v=dQw4w9WgXcQ
https://youtu.be/9bZkp7q19f0
3JZ_D3ELwOQ
💬 comments.txt - Comments to Post
txt
# Add comments (one per line)
Great video! Really enjoyed the content.
Very informative, learned a lot from this.
Amazing work, keep up the great content!
📢 channels.txt - Channels to Subscribe
txt
# Add channel URLs, IDs, or @handles
https://www.youtube.com/channel/UC_x5XG1OV2P6uZZ5FSM9Ttw
@YouTube
https://www.youtube.com/c/Google
⚙️ Configuration
Recommended Settings for Beginners
Setting	Value	Why
Base Delay	4.0 seconds	Safe interval between actions
Jitter	2.0 seconds	Makes behavior more natural
Max Retries	3 attempts	Handles temporary failures
Log Level	INFO	Good balance of detail
Through GUI
Open the application

Go to Settings tab

Adjust the sliders and options

Changes save automatically

Through CLI
bash
python src/youtube_automation_cli.py --action like --file likes.txt --delay 4.0 --jitter 2.0
🧪 Testing Your Setup
Quick Test
bash
# Test with a small batch
python src/youtube_automation_cli.py --action like --file examples/likes.txt --limit 3 --dry-run
Verification Steps
✅ Application opens without errors

✅ Authentication works and creates token.json

✅ Can load input files without errors

✅ Settings can be configured

✅ Dry run works (tests without actual actions)

🐛 Troubleshooting
Common Setup Issues
"ModuleNotFoundError: No module named 'customtkinter'"
bash
# Reinstall dependencies
pip install -r requirements.txt --force-reinstall

# Or install individually
pip install customtkinter
Authentication Browser Doesn't Open
Manually visit the URL shown in terminal

Complete authentication in browser

Copy the authorization code back to terminal

"Invalid credentials" Error
Delete token.json file

Verify credentials.json is in project root

Re-authenticate

API Quota Issues
Visit Google Cloud Console Quotas

Check YouTube Data API v3 usage

Wait 24 hours or request increase

Getting Help
📖 Troubleshooting Guide

💬 GitHub Discussions

🐛 Create Issue

🚀 Next Steps
After Successful Setup
Read the Usage Guide

Start with small batches (10-20 actions)

Monitor your first automation session

Check YouTube Studio to verify actions

Adjust settings based on results

Best Practices for Success
🕐 Start slow: Use 4-6 second delays initially

📊 Monitor quotas: Check Google Cloud Console regularly

💾 Backup files: Save your configuration and input files

🔄 Test frequently: Use dry-run mode for testing

📝 Keep logs: Review logs for any issues

Advanced Setup Options
Scheduled Automation
bash
# Using cron (Linux/Mac) or Task Scheduler (Windows)
# Run automation at specific times
0 9 * * * cd /path/to/youtube-automation-suite && python src/youtube_automation_cli.py --action like --file likes.txt
Multiple Accounts
Use different credentials.json files

Switch between them by renaming

Or modify the code to support multiple configurations

<div align="center">
🎉 Setup Complete!
You're ready to start automating! 🚀

What to Do Next:
Read the Usage Guide for detailed instructions

Start with a small test using the example files

Join our community for support and tips

Need Help?
🐛 Create Issue • 💬 Ask Community • 📚 Usage Guide

Happy Automating! 🤖

⬆ Back to Top

</div>
<div align="center">
Last Updated: ${new Date().toLocaleDateString()}
If this guide helped you, consider starring the repository! ⭐

</div> ```
