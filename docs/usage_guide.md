
```markdown
# 🎯 Comprehensive Usage Guide

## Table of Contents
1. [Getting Started](#getting-started)
2. [GUI Interface Guide](#gui-interface-guide)
3. [CLI Interface Guide](#cli-interface-guide)
4. [Advanced Features](#advanced-features)
5. [Best Practices](#best-practices)
6. [Use Cases](#use-cases)

## Getting Started

### First Launch
When you first launch the application (either GUI or CLI), you'll need to:

1. **Authenticate with Google**
   - A browser window will open
   - Select your YouTube account
   - Grant the requested permissions
   - You'll be redirected back to the application

2. **Prepare Input Files**
   - Create `likes.txt`, `comments.txt`, and `channels.txt`
   - Place them in your preferred directory
   - Follow the format guidelines

3. **Configure Settings**
   - Set appropriate delays between actions
   - Configure logging preferences
   - Set action limits if needed

## GUI Interface Guide

### Main Dashboard

#### Navigation Tabs
- **🤖 Automation**: Action selection and configuration
- **📊 Statistics**: Real-time performance metrics
- **📝 Logs**: Detailed activity records
- **⚙️ Settings**: Application configuration

#### Automation Panel

**Action Selection**
- Checkboxes for Like, Comment, Subscribe
- File selection for each action type
- Target video input for comments

**Progress Monitoring**
- Real-time progress bars
- Action counters
- Success/failure rates
- Estimated time remaining

#### Statistics Panel

**Live Metrics**
- Total actions performed
- Success rates per action type
- Error counts
- Session duration

**Performance Insights**
- Average time per action
- API call success rates
- Quota usage estimates

#### Settings Panel

**Timing Configuration**
- Base delay between actions
- Random jitter variation
- Maximum retry attempts
- Retry delay multiplier

**Application Settings**
- Log level (DEBUG, INFO, WARNING, ERROR)
- Auto-save interval
- Theme preferences
- Notification settings

### Step-by-Step GUI Workflow

1. **Select Actions**
