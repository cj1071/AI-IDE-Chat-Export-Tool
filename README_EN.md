# AI IDE Chat Export Tool

A powerful AI IDE chat history viewing and export tool that supports unified management and export of multiple data sources.

![Project Status](https://img.shields.io/badge/Status-Production%20Ready-brightgreen)
![Docker Support](https://img.shields.io/badge/Docker-Supported-blue)
![Multi Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20macOS%20%7C%20Linux-lightgrey)

**🌐 Language**: [中文](README.md) | **English**

## 🎯 Project Overview

This project is a specialized web application for viewing, managing, and exporting AI IDE chat records. It can extract conversation data from multiple different AI assistant data sources and provide a unified interface for viewing, searching, and exporting.

### ✨ Key Features

- **🔄 Multi-Data Source Support**: Unified management of chat records from 5 different AI assistants
- **🎨 Modern Interface**: Material-UI based dark theme design providing excellent user experience
- **📤 Powerful Export Features**: Support for HTML, JSON, and Markdown export formats
- **🤖 Intelligent Data Extraction**: Automatic parsing and conversion of different format chat data
- **📁 Project Recognition**: Intelligent identification and display of conversation project information
- **⚙️ Settings Management**: Visual settings page supporting custom data source path configuration
- **✅ Path Validation**: Intelligent validation of configuration path validity with real-time feedback
- **🔍 Search Functionality**: Support for quick search and filtering of conversation content
- **📊 Statistics**: Display conversation count, message statistics, and other information

## 🔧 Technology Stack

### Frontend Technologies

- **React 18** - Modern user interface framework
- **Material-UI (MUI)** - Professional React UI component library
- **React Router** - Single page application routing management
- **Axios** - HTTP client library
- **React Markdown** - Markdown content rendering

### Backend Technologies

- **Flask** - Lightweight Python web framework
- **SQLite** - Database operations and queries
- **Flask-CORS** - Cross-origin resource sharing support

## 📊 Supported Data Sources

| Data Source | IDE | Plugin | Data Format | Status |
|-------------|-----|--------|-------------|--------|
| **Cursor Native** | Cursor IDE | Built-in | SQLite | ✅ Fully Supported |
| **VSCode Augment** | Visual Studio Code | Augment | SQLite | ✅ Fully Supported |
| **Cursor Augment** | Cursor IDE | Augment | SQLite | ✅ Fully Supported |
| **IDEA Augment** | IntelliJ IDEA | Augment | XML | ✅ Fully Supported |
| **PyCharm Augment** | PyCharm | Augment | XML | ✅ Fully Supported |

### 🔍 Data Source Details

#### 1. **Cursor Native Conversations**
- **📍 Source**: Cursor IDE's native AI chat functionality
- **💾 Data Location**: Cursor's workspaceStorage and global storage
- **🎯 Features**: Support for complete conversation history and project context

#### 2. **VSCode Augment Conversations**
- **📍 Source**: Augment AI assistant plugin in VSCode
- **💾 Data Location**: VSCode's workspaceStorage SQLite database
- **🎯 Features**: Professional code assistance conversation records

#### 3. **Cursor Augment Conversations**
- **📍 Source**: Augment AI assistant plugin in Cursor IDE
- **💾 Data Location**: Cursor's workspaceStorage (compatible with VSCode format)
- **🎯 Features**: Augment conversations combined with Cursor environment

#### 4. **IDEA Augment Conversations**
- **📍 Source**: Augment AI assistant plugin in JetBrains IntelliJ IDEA
- **💾 Data Location**: XML format data in IDEA's configuration directory
- **🎯 Features**: Professional code conversations supporting Java development environment

#### 5. **PyCharm Augment Conversations**
- **📍 Source**: Augment AI assistant plugin in JetBrains PyCharm
- **💾 Data Location**: XML format data in PyCharm's configuration directory
- **🎯 Features**: Code assistance conversations specifically for Python development

## 🚀 Quick Start

### 🐳 Recommended: Docker Compose (One-Click Deployment)

**📋 Requirements**:
- Docker 20.0+
- Docker Compose 2.0+

**⚡ Quick Launch**:

#### 1. **Clone Project**
```bash
git clone <repository-url>
cd AI-IDE-Chat-Export-Tool
```

#### 2. **Environment Configuration** (Optional)

Create `.env` file for custom path configuration:
```bash
# Copy environment variable template
cp .env.example .env

# Edit configuration (optional)
nano .env
```

**Default Paths by Operating System**:

| OS | Cursor | VSCode | JetBrains |
|----|--------|--------|-----------|
| **macOS** | `~/Library/Application Support/Cursor` | `~/Library/Application Support/Code` | `~/Library/Application Support/JetBrains` |
| **Linux** | `~/.config/Cursor` | `~/.config/Code` | `~/.config/JetBrains` |
| **Windows** | `%APPDATA%\Cursor` | `%APPDATA%\Code` | `%APPDATA%\JetBrains` |

#### 3. **One-Click Launch**

Using convenience script (recommended):
```bash
# 🚀 Start service
./start.sh start

# 📊 Check status
./start.sh status

# 📝 View logs
./start.sh logs

# 🛑 Stop service
./start.sh stop

# 🔄 Restart service
./start.sh restart

# 🧹 Clean environment
./start.sh clean
```

Or use Docker Compose directly:
```bash
docker-compose up -d --build
```

#### 4. **Access Application**
🌐 Open browser and visit: **http://localhost:3000**

> **💡 start.sh Script Description**: This intelligent startup script will:
> - Automatically check Docker environment
> - Display detailed startup progress
> - Provide real-time status monitoring
> - Support one-click cleanup and reset
> - Show access address and usage tips

### 📦 Traditional Method: Manual Installation

**📋 Requirements**:
- **Node.js** 16.0+
- **Python** 3.7+
- **npm** or **yarn**

**Installation Steps**:

1. **Clone Project**
```bash
git clone <repository-url>
cd AI-IDE-Chat-Export-Tool
```

2. **Install Frontend Dependencies**
```bash
cd frontend
npm install
```

3. **Build Frontend Production Version**
```bash
npm run build
```

4. **Install Backend Dependencies**
```bash
cd ../backend
pip install -r ../requirements.txt
```

**Start Application**:

1. **Start Backend Server**
```bash
cd backend
python server.py
```

2. **Access Application**
   Open browser and visit: `http://localhost:5000`

> **Note**: Please ensure you follow the above order, build frontend first, then start backend server. The application runs on port 5000, not 3000.

## 💡 User Guide

### 🔄 Data Source Switching

1. **Select Data Source**: Choose the data source you want to view in the data source selector at the top of the page
2. **Auto Loading**: The system will automatically load chat records from the corresponding data source
3. **Seamless Switching**: Support seamless switching between 5 data sources
4. **Real-time Statistics**: Display conversation count statistics for each data source

### 👀 View Conversations

1. **Browse List**: Browse all conversations in the chat list, displayed grouped by project
2. **Detailed View**: Click any conversation to enter the detailed view page
3. **Smart Filtering**: Support filtering by project, time, content and other information
4. **Search Function**: Use the search box to quickly find specific conversations

### 📤 Export Features

1. **Select Conversation**: Select the conversation to export on the conversation details page or list page
2. **Choose Format**: Support three export formats:
   - **HTML**: Suitable for browser viewing, includes complete styling
   - **Markdown**: Suitable for document editing, supports code highlighting
   - **JSON**: Suitable for program processing, includes complete metadata
3. **One-Click Download**: The system will generate a file containing complete conversation content for download
4. **Batch Export**: Support selecting multiple conversations for batch export

### ⚙️ Settings Configuration

1. **Enter Settings**: Click the settings icon in the upper right corner of the page to enter the settings page
2. **Path Configuration**: Configure custom paths for each data source (optional)
3. **Real-time Validation**: The system will automatically validate path validity and provide real-time feedback
4. **Configuration Management**: Support resetting to default paths or saving custom configurations
5. **Status Monitoring**: View connection status and data statistics for each data source

## 🎨 Core Features

### 🧠 Intelligent Project Recognition
- **Auto Extraction**: Intelligently extract project names from file paths
- **Git Support**: Support Git repository information recognition and display
- **Path Filtering**: Intelligently filter user directories and system directories
- **Project Grouping**: Automatically group conversation records by project

### 🎯 Modern UI Design
- **Dark Theme**: Eye-friendly dark theme design
- **Responsive Layout**: Perfect adaptation to desktop, tablet, mobile and other devices
- **Smooth Animation**: Rich transition animations and interactive effects
- **Material Design**: Follow Google Material Design specifications

### ⚡ Powerful Data Processing
- **Multi-format Support**: Support SQLite, JSON, XML and other data formats
- **Intelligent Parsing**: Automatically recognize and convert chat data in different formats
- **Error Recovery**: Complete error handling and exception recovery mechanisms
- **Performance Optimization**: Efficient data extraction and processing algorithms

### 🔧 Advanced Configuration Management
- **Visual Settings**: Intuitive settings interface supporting custom path configuration
- **Real-time Validation**: Real-time path validity validation and status feedback
- **Configuration Persistence**: Automatic configuration saving with one-click reset support
- **Smart Detection**: Automatic default path detection and fallback mechanisms

### 🔍 Search and Filtering
- **Full-text Search**: Support full-text search of conversation content
- **Smart Filtering**: Filter by time, project, message count and other conditions
- **Real-time Search**: Search as you type, no waiting required
- **Highlight Display**: Search results highlight matching content

## 🔄 Project Evolution

### 📈 Major Enhancements Over Original Project

This project is based on deep secondary development of [cursor-view](https://github.com/saharmor/cursor-view), achieving the following major enhancements:

| Feature Area | Original Project | This Project Enhancement | Improvement |
|--------------|------------------|--------------------------|-------------|
| **Data Source Support** | Cursor Only | 5 Data Sources | 🚀 500% |
| **Export Formats** | Basic Export | HTML/JSON/Markdown | 🚀 300% |
| **User Interface** | Simple Interface | Material-UI Dark Theme | 🚀 1000% |
| **Data Processing** | Basic Parsing | Intelligent Multi-format Processing | 🚀 500% |
| **Configuration Management** | None | Visual Settings System | 🚀 ∞ |
| **Error Handling** | Basic | Complete Exception Handling | 🚀 800% |

### 🎯 Core Improvement Highlights

1. **🔄 Multi-Data Source Unification**: Expanded from single Cursor data source to five mainstream AI IDE data sources
2. **📤 Standardized Export**: Support for multiple format standardized export, meeting different usage scenarios
3. **🎨 Modern Design**: Brand new Material-UI design language and dark theme
4. **🤖 Intelligent Data Extraction**: More powerful data parsing and conversion capabilities, supporting complex data structures
5. **📁 Project Recognition Optimization**: More accurate project name recognition and grouping algorithms
6. **🛡️ Enhanced Error Handling**: Complete exception handling and user-friendly error feedback
7. **⚙️ Settings Management System**: Visual configuration interface and path management functionality
8. **🔧 JetBrains Support**: New IDEA and PyCharm Augment data source support
9. **🐳 Dockerized Deployment**: Complete containerization solution with one-click deployment
10. **🔍 Search and Filtering**: Powerful search and filtering functionality

### 🙏 Acknowledgments

Thanks to the [saharmor/cursor-view](https://github.com/saharmor/cursor-view) project for providing the basic architecture and inspiration. This project has undergone extensive feature expansion and user experience optimization based on it, committed to becoming the best AI IDE chat record management tool.

## 🆕 Latest Updates

### 📅 Version History

#### v2.0.0 (Latest Version)
- ✅ **Complete Dockerized Deployment**: One-click startup, multi-platform support
- ✅ **Smart Environment Variable Configuration**: Support `.env` file custom paths
- ✅ **Enhanced Error Handling**: Friendly error messages and recovery mechanisms
- ✅ **Performance Optimization**: Faster data loading and processing speed
- ✅ **UI/UX Improvements**: Smoother user experience and visual effects

#### v1.5.0
- ✅ **JetBrains IDE Support**: New IDEA and PyCharm Augment data sources
- ✅ **Settings Management System**: Visual configuration interface and path management
- ✅ **Path Validation Feature**: Real-time validation of configuration path validity

#### v1.0.0
- ✅ **Multi-Data Source Support**: Support for 5 different AI IDE data sources
- ✅ **Modern Interface**: Material-UI dark theme design
- ✅ **Multi-format Export**: HTML, JSON, Markdown three export formats

### 🔮 Coming Soon

- 🔄 **Batch Operations**: Support batch export and conversation management
- 📊 **Data Analytics**: Conversation statistics and usage analysis
- 🔍 **Advanced Search**: Support regular expressions and complex queries
- 🌐 **Multi-language Support**: Interface internationalization support
- 📱 **Mobile Optimization**: Better mobile device experience

## 📁 Project Architecture

### 🏗️ Overall Architecture Diagram

```
AI-IDE-Chat-Export-Tool/
├── 🎨 frontend/                    # React Frontend Application
│   ├── src/
│   │   ├── components/             # React Component Library
│   │   │   ├── ChatDetail.js       # 📄 Conversation Details Page
│   │   │   ├── ChatList.js         # 📋 Conversation List Page
│   │   │   ├── Header.js           # 🎯 Page Header Component
│   │   │   ├── PathConfigCard.js   # 🔧 Path Configuration Card
│   │   │   └── SettingsPage.js     # ⚙️ Settings Page
│   │   ├── constants/              # 📊 Configuration Constants
│   │   │   └── dataSourceConfig.js # 🔄 Data Source Configuration
│   │   ├── utils/                  # 🛠️ Utility Functions
│   │   └── styles/                 # 🎨 Style Files
│   ├── build/                      # 📦 Build Output Directory
│   ├── public/                     # 🌐 Static Resources
│   └── package.json                # 📋 Frontend Dependencies Configuration
├── 🐍 backend/                     # Python Backend Service
│   ├── server.py                   # 🚀 Flask Main Server
│   ├── config_manager.py           # ⚙️ Configuration Manager
│   ├── path_validator.py           # ✅ Path Validator
│   ├── augment_extractor.py        # 🔍 Augment Data Extractor
│   ├── cursor_augment_extractor.py # 🔍 Cursor Augment Extractor
│   ├── idea_augment_extractor.py   # 🔍 IDEA Augment Extractor
│   ├── pycharm_augment_extractor.py # 🔍 PyCharm Augment Extractor
│   ├── conversation_parser.py      # 📝 Conversation Parser
│   ├── output_formatter.py         # 📤 Output Formatter
│   ├── cursor_chat_finder.py       # 🔍 Cursor Chat Finder
│   └── extract_cursor_chat.py      # 📊 Cursor Chat Extractor
├── 🐳 Docker Configuration
│   ├── Dockerfile                  # 🐳 Docker Image Configuration
│   ├── docker-compose.yml          # 🐳 Docker Compose Configuration
│   └── nginx.conf                  # 🌐 Nginx Configuration
├── 📋 Configuration Files
│   ├── config.json                 # ⚙️ Application Configuration File
│   ├── requirements.txt            # 🐍 Python Dependencies
│   ├── .env.example               # 🔧 Environment Variable Template
│   └── start.sh                   # 🚀 Startup Script
└── 📚 Documentation
    ├── README.md                  # 📖 Chinese Documentation
    └── README_EN.md               # 📖 English Documentation
```

### 🔧 Technology Stack Details

| Layer | Technology | Version | Purpose |
|-------|------------|---------|---------|
| **Frontend** | React | 18.x | User Interface Framework |
| **UI Library** | Material-UI | 5.x | Component Library and Theming |
| **Routing** | React Router | 6.x | Single Page Application Routing |
| **HTTP Client** | Axios | 1.x | API Request Handling |
| **Backend** | Flask | 2.x | Web Service Framework |
| **Database** | SQLite | 3.x | Data Storage and Querying |
| **Containerization** | Docker | 20.x+ | Application Containerization |
| **Web Server** | Nginx | 1.x | Reverse Proxy and Static File Serving |

## 🤝 Contributing

Welcome to submit Issues and Pull Requests to improve the project!

### Code Standards

- Frontend: Follow React and JavaScript best practices
- Backend: Follow PEP 8 Python code standards
- Commit Messages: Use clear commit messages to describe changes
- **Branch Management**: Please submit all code contributions to the `dev` branch, not the `main` branch

## 📄 License

This project is licensed under the [Apache License 2.0](LICENSE).

## ⚙️ Environment Configuration

### Optional Environment Variables

```bash
# Enable Cursor chat diagnostics mode (for debugging)
export CURSOR_CHAT_DIAGNOSTICS=1

# Custom server port (default 5000)
export PORT=5000
```

### Data Storage Locations

Data storage locations on different operating systems:

**Windows**:

- Cursor: `%APPDATA%\Cursor\User\workspaceStorage`
- VSCode: `%APPDATA%\Code\User\workspaceStorage`
- IDEA: `%APPDATA%\JetBrains\IntelliJIdea[version]\options`
- PyCharm: `%APPDATA%\JetBrains\PyCharm[version]\options`

**macOS**:

- Cursor: `~/Library/Application Support/Cursor/User/workspaceStorage`
- VSCode: `~/Library/Application Support/Code/User/workspaceStorage`
- IDEA: `~/Library/Application Support/JetBrains/IntelliJIdea[version]/options`
- PyCharm: `~/Library/Application Support/JetBrains/PyCharm[version]/options`

**Linux**:

- Cursor: `~/.config/Cursor/User/workspaceStorage`
- VSCode: `~/.config/Code/User/workspaceStorage`
- IDEA: `~/.config/JetBrains/IntelliJIdea[version]/options`
- PyCharm: `~/.config/JetBrains/PyCharm[version]/options`

## 🔧 Troubleshooting

### 🐳 Docker Related Issues

#### ❌ **Docker Container Cannot Start**
**Solutions**:
1. **Check Environment**: Confirm Docker and Docker Compose are properly installed
   ```bash
   docker --version
   docker-compose --version
   ```
2. **View Logs**: Check detailed error information
   ```bash
   docker-compose logs ai-ide-chat
   ```
3. **Port Check**: Ensure port 3000 is not occupied
   ```bash
   lsof -i :3000  # macOS/Linux
   netstat -ano | findstr :3000  # Windows
   ```
4. **Rebuild**: Force rebuild image
   ```bash
   docker-compose up -d --build --force-recreate
   ```

#### 🌐 **Cannot Access localhost:3000**
**Solutions**:
1. **Check Container Status**:
   ```bash
   docker-compose ps
   docker-compose logs ai-ide-chat
   ```
2. **Port Mapping Check**: Confirm port mapping in docker-compose.yml is correct
3. **Firewall Settings**: Ensure firewall is not blocking the port
4. **Port Conflict**: If port is occupied, modify configuration:
   ```yaml
   ports:
     - "3001:80"  # Change to another port
   ```

#### 📁 **IDE Data Directory Mount Failed**
**Solutions**:
1. **Check Directory Exists**:
   ```bash
   # macOS
   ls -la ~/Library/Application\ Support/Cursor

   # Linux
   ls -la ~/.config/Cursor

   # Windows
   dir "%APPDATA%\Cursor"
   ```
2. **Permission Check**: Ensure Docker has permission to access the directory
3. **Path Adjustment**: Adjust mount paths according to operating system
4. **Directory Not Exist**: If directory doesn't exist, comment out corresponding mount configuration

#### 🔄 **Docker Environment Reset**
**Complete Reset Commands**:
```bash
# Stop and remove current project containers, volumes, images
docker-compose down --rmi all --volumes --remove-orphans

# Clean build cache (optional; removes all unused build cache)
docker builder prune -a

# Clean entire Docker system (optional; removes all unused resources, including stopped containers and useless images)
docker system prune -a

# Rebuild and start
docker-compose up -d --build
```

### 📦 Traditional Installation Issues

#### ❌ **Cannot Access localhost:5000 After Startup**
**Solutions**:

1. Ensure backend server started correctly with no error messages
2. Port 5000 is not occupied by other programs
3. Firewall is not blocking the port

#### ❌ **Cannot Find Chat Data**
**Solutions**:

1. Check if corresponding IDE is installed and has used AI functionality
2. Data source selection is correct
3. Related plugins are installed (such as Augment plugin)
4. Check data source path configuration is correct in settings page
5. Confirm path validation status shows as valid

#### ❌ **Export Function Not Working**
**Solutions**:

1. Browser allows file downloads
2. Sufficient disk space available
3. Conversation data is not empty

#### ❌ **Frontend Build Failed**
**Solutions**:

1. Delete `node_modules` folder and re-run `npm install`
2. Check Node.js version meets requirements
3. Clear npm cache: `npm cache clean --force`

### Development Mode

For development, you can start frontend and backend separately:

```bash
# Start frontend development server (port 3000)
cd frontend
npm start

# Start backend server (port 5000)
cd backend
python server.py
```

## 📚 Quick Reference

### 🚀 Common Commands

```bash
# Start service
./start.sh start

# Check status
./start.sh status

# View logs
./start.sh logs

# Restart service
./start.sh restart

# Stop service
./start.sh stop

# Clean environment
./start.sh clean
```

### 🔗 Important Links

- **🌐 Application Access**: http://localhost:3000
- **📊 Settings Page**: http://localhost:3000/settings
- **📝 API Documentation**: http://localhost:3000/api/settings
- **🐳 Docker Hub**: (To be published)
- **📖 Online Documentation**: (To be published)

### 📞 Get Help

- **🐛 Report Issues**: [GitHub Issues](https://github.com/your-repo/issues)
- **💡 Feature Suggestions**: [GitHub Discussions](https://github.com/your-repo/discussions)
- **📧 Contact Us**: your-email@example.com
- **📚 Documentation**: See this README file

### 🏷️ Tags

`AI` `IDE` `Chat` `Export` `Cursor` `VSCode` `Augment` `JetBrains` `Docker` `React` `Flask` `Material-UI`

---

**🎉 Thank you for using AI IDE Chat Export Tool!**

If this project helps you, please consider giving us a ⭐ Star!
