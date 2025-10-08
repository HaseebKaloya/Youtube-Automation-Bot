# 🔰 KaloyaXploit - YouTube Automation Suite

<div align="center">

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python)
![CustomTkinter](https://img.shields.io/badge/GUI-CustomTkinter-green)
![YouTube API](https://img.shields.io/badge/API-YouTube%20Data%20v3-red?logo=youtube)
![License](https://img.shields.io/badge/License-MIT-yellow)
![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Linux%20%7C%20macOS-lightgrey)

**Professional YouTube Automation Tool with Advanced GUI**  
*Think Secure. Act Smart.*

[Features](#-features) • [Installation](#-installation) • [Usage](#-usage) • [Screenshots](#-screenshots) • [Configuration](#-configuration) • [Disclaimer](#-important-disclaimer) • [Support](#-support)

</div>

## 📖 Overview

**KaloyaXploit YouTube Automation Suite** is a professional-grade desktop application designed for legitimate YouTube channel management and growth. Built with modern Python and CustomTkinter, it provides an intuitive interface for automating common YouTube interactions while maintaining compliance with platform policies.

> ⚠️ **Important**: This tool is intended for managing accounts you own. Always respect YouTube's Terms of Service.

## 🚀 Features

### 🎯 Core Automation Capabilities
- **💖 Smart Liking**: Auto-like videos from predefined lists
- **💬 Intelligent Commenting**: Post contextual comments with customizable templates
- **📢 Targeted Subscriptions**: Subscribe to channels based on your niche
- **🔄 Process Tracking**: Avoid duplicate actions with persistent state management

### 🎨 Professional GUI Interface
- **🌙 Dark Theme**: Modern, eye-friendly dark interface
- **📊 Real-time Analytics**: Live statistics and progress tracking
- **📝 Enhanced Logging**: Color-coded, emoji-rich activity logs
- **⚙️ Centralized Controls**: Intuitive dashboard for all operations

### 🔧 Advanced Technical Features
- **🛡️ Exponential Backoff**: Intelligent retry mechanism for API limits
- **📈 Progress Tracking**: Real-time progress bars and status updates
- **💾 State Persistence**: Resume operations after interruptions
- **🔐 Secure Authentication**: OAuth 2.0 with token management

## 📸 Screenshots

*(Add your screenshots here)*
```
Main Dashboard | Automation Progress | Statistics Panel | Log Viewer
```

## 🛠️ Installation

### Prerequisites
- **Python 3.8 or higher**
- **Google Account** with YouTube channel
- **YouTube Data API v3** enabled

### Step 1: Clone Repository
```bash
git clone https://github.com/yourusername/kaloyaxploit-youtube-automation.git
cd kaloyaxploit-youtube-automation
```

### Step 2: Install Dependencies
```bash
pip install -r requirements.txt
```

### Step 3: Google API Setup

1. **Visit [Google Cloud Console](https://console.cloud.google.com/)**
2. **Create a new project** or select existing one
3. **Enable YouTube Data API v3**
   - Navigate to "APIs & Services" > "Library"
   - Search "YouTube Data API v3"
   - Click "Enable"
4. **Create OAuth 2.0 Credentials**
   - Go to "APIs & Services" > "Credentials"
   - Click "Create Credentials" > "OAuth 2.0 Client ID"
   - Choose "Desktop Application"
   - Download the credentials file
5. **Rename downloaded file to `credentials.json`** and place in project root

### Step 4: Run Application
```bash
python youtube_automation_gui.py
```

## 🎮 Usage

### Initial Setup
1. **Launch the application**
2. **Configure Google API credentials** in Settings
3. **Authenticate** with your Google account
4. **Select desired automation actions**

### File Preparation

#### 📁 Likes.txt
```txt
https://www.youtube.com/watch?v=VIDEO_ID_1
https://youtu.be/VIDEO_ID_2
VIDEO_ID_3
```

#### 💬 Comments.txt
```txt
Great content! Really enjoyed this video.
Very informative, thanks for sharing!
Amazing work, keep it up!
```

#### 📢 Channels.txt
```txt
https://www.youtube.com/channel/UC_X_ID_1
@Username
https://www.youtube.com/c/ChannelName
```

### Automation Workflow
1. **Select Actions**: Choose which operations to perform
2. **Load Files**: Import your prepared text files
3. **Configure Settings**: Adjust delays and parameters
4. **Start Automation**: Monitor real-time progress
5. **Review Results**: Check statistics and logs

## ⚙️ Configuration

### Settings Overview
- **⏱️ Base Delay**: 4.0 seconds (recommended)
- **🎲 Jitter**: 2.0 seconds (randomization)
- **🔄 Max Retries**: 6 attempts
- **📊 Log Level**: INFO (adjustable)

### Best Practices
- **Start small** with 10-20 actions to test
- **Use reasonable delays** to avoid detection
- **Monitor API quotas** in Google Cloud Console
- **Keep comments genuine** and relevant
- **Respect YouTube's daily limits**

## 🏗️ Project Structure

```
kaloyaxploit-youtube-automation/
├── 📁 src/
│   ├── youtube_automation_gui.py    # Main application
│   ├── requirements.txt             # Dependencies
│   └── README.md                    # This file
├── 📁 docs/
│   ├── setup_guide.md              # Detailed setup instructions
│   └── troubleshooting.md          # Common issues and solutions
├── 📁 examples/
│   ├── likes.txt                   # Sample likes file
│   ├── comments.txt                # Sample comments file
│   └── channels.txt                # Sample channels file
└── 📁 assets/
    ├── screenshots/                # Application screenshots
    └── icons/                      # Application icons
```

## 🔧 Technical Details

### Built With
- **Python 3.8+** - Core programming language
- **CustomTkinter** - Modern GUI framework
- **Google API Client** - YouTube Data API integration
- **OAuth 2.0** - Secure authentication

### Architecture
- **MVC Pattern** - Model-View-Controller architecture
- **Multi-threading** - Non-blocking UI operations
- **Modular Design** - Easy maintenance and extensions
- **Error Handling** - Robust exception management

## 🚨 Important Disclaimer

### ⚠️ Legal and Ethical Usage
This software is designed for:
- ✅ Managing your own YouTube channels
- ✅ Legitimate social media management
- ✅ Educational and research purposes

### ❌ Strictly Prohibited
- 🚫 Automated interactions without explicit permission
- 🚫 Spam or malicious activities
- 🚫 Violation of YouTube Terms of Service
- 🚫 Any illegal or unethical use

**The developers are not responsible for any misuse of this software. Users are solely responsible for complying with all applicable laws and platform policies.**

## 🐛 Troubleshooting

### Common Issues

#### 🔐 Authentication Problems
```bash
# Clear existing tokens
rm token.json
# Re-authenticate on next launch
```

#### 📦 Dependency Issues
```bash
# Update pip and reinstall
python -m pip install --upgrade pip
pip install -r requirements.txt --force-reinstall
```

#### 🎯 API Quota Exceeded
- Check your quota in Google Cloud Console
- Reduce automation frequency
- Spread actions across multiple days

### Error Messages
- **"Invalid credentials"**: Re-download credentials.json
- **"API not enabled"**: Enable YouTube Data API v3
- **"Quota exceeded"**: Wait for quota reset or request increase

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guidelines](CONTRIBUTING.md) for details.

### Development Setup
```bash
# Fork and clone repository
git clone https://github.com/yourusername/kaloyaxploit-youtube-automation.git

# Create virtual environment
python -m venv venv
source venv/bin/activate  # Linux/macOS
venv\Scripts\activate    # Windows

# Install development dependencies
pip install -r requirements.txt
```

### Feature Requests & Bug Reports
Please use the [GitHub Issues](https://github.com/yourusername/kaloyaxploit-youtube-automation/issues) page to report bugs or request features.

## 📊 Statistics & Analytics

The application provides comprehensive analytics:
- **Real-time action counters**
- **Success/failure rates**
- **Session duration tracking**
- **Exportable log files**

## 🔒 Security & Privacy

- **Local token storage** - Credentials never leave your machine
- **No data collection** - We don't track your usage
- **Open source** - Transparent codebase
- **Regular updates** - Security patches and improvements

## 🌟 Support

### 📞 Contact Information
- **📧 Email**: your-email@example.com
- **📱 WhatsApp**: https://wa.me/yournumber
- **✈️ Telegram**: https://t.me/yourchannel
- **🎥 YouTube**: https://youtube.com/yourchannel

### 📚 Documentation
- [Full Documentation](docs/) - Detailed usage guides
- [API Reference](docs/api.md) - Technical API documentation
- [Video Tutorials](https://youtube.com/yourchannel) - Step-by-step videos

### 🐛 Bug Reports
Found a bug? Please [create an issue](https://github.com/yourusername/kaloyaxploit-youtube-automation/issues) with:
- Detailed description
- Steps to reproduce
- Screenshots (if applicable)
- Error logs

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🎉 Acknowledgments

- **Google** for YouTube Data API
- **CustomTkinter** community for the amazing GUI framework
- **Python community** for excellent libraries
- **Contributors** who help improve this project

---

<div align="center">

### ⭐ If you find this project helpful, please give it a star!

**Made with ❤️ by Haseeb Kaloya | KaloyaXploit**

*Think Secure. Act Smart.*

[⬆ Back to Top](#-kaloyaxploit---youtube-automation-suite)

</div>
