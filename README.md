# AI IDE 聊天导出工具 (AI IDE Chat Export Tool)

一个功能强大的 AI IDE 聊天记录查看和导出工具，支持多种数据源的统一管理和导出。

![项目状态](https://img.shields.io/badge/状态-生产就绪-brightgreen)
![Docker支持](https://img.shields.io/badge/Docker-支持-blue)
![多平台](https://img.shields.io/badge/平台-Windows%20%7C%20macOS%20%7C%20Linux-lightgrey)

**🌐 语言**: **中文** | [English](README_EN.md)

## 🎯 项目简介

本项目是一个专门用于查看、管理和导出 AI IDE 聊天记录的 Web 应用程序。它能够从多个不同的 AI 助手数据源中提取对话数据，并提供统一的界面进行查看、搜索和导出。

### ✨ 主要功能

- **🔄 多数据源支持**：统一管理来自 5 种不同 AI 助手的对话记录
- **🎨 现代化界面**：基于 Material-UI 的深色主题设计，提供优秀的用户体验
- **📤 强大的导出功能**：支持 HTML、JSON、Markdown 三种格式的导出
- **🤖 智能数据提取**：自动解析和转换不同格式的聊天数据
- **📁 项目识别**：智能识别和显示对话所属的项目信息
- **⚙️ 设置管理**：提供可视化的设置页面，支持自定义数据源路径配置
- **✅ 路径验证**：智能验证配置路径的有效性，提供实时反馈
- **🔍 搜索功能**：支持对话内容的快速搜索和过滤
- **📊 统计信息**：显示对话数量、消息统计等信息

## 🔧 技术栈

### 前端技术

- **React 18** - 现代化的用户界面框架
- **Material-UI (MUI)** - 专业的 React UI 组件库
- **React Router** - 单页应用路由管理
- **Axios** - HTTP 客户端库
- **React Markdown** - Markdown 内容渲染

### 后端技术

- **Flask** - 轻量级 Python Web 框架
- **SQLite** - 数据库操作和查询
- **Flask-CORS** - 跨域资源共享支持

## 📊 支持的数据源

| 数据源 | IDE | 插件 | 数据格式 | 状态 |
|--------|-----|------|----------|------|
| **Cursor 原生** | Cursor IDE | 内置 | SQLite | ✅ 完全支持 |
| **VSCode Augment** | Visual Studio Code | Augment | SQLite | ✅ 完全支持 |
| **Cursor Augment** | Cursor IDE | Augment | SQLite | ✅ 完全支持 |
| **IDEA Augment** | IntelliJ IDEA | Augment | XML | ✅ 完全支持 |
| **PyCharm Augment** | PyCharm | Augment | XML | ✅ 完全支持 |

### 🔍 数据源详细说明

#### 1. **Cursor 原生对话**
- **📍 来源**：Cursor IDE 的原生 AI 聊天功能
- **💾 数据位置**：Cursor 的 workspaceStorage 和全局存储
- **🎯 特点**：支持完整的对话历史和项目上下文


#### 2. **VSCode Augment 对话**
- **📍 来源**：VSCode 中的 Augment AI 助手插件
- **💾 数据位置**：VSCode 的 workspaceStorage SQLite 数据库
- **🎯 特点**：专业的代码辅助对话记录


#### 3. **Cursor Augment 对话**
- **📍 来源**：Cursor IDE 中的 Augment AI 助手插件
- **💾 数据位置**：Cursor 的 workspaceStorage（与 VSCode 格式兼容）
- **🎯 特点**：结合 Cursor 环境的 Augment 对话


#### 4. **IDEA Augment 对话**
- **📍 来源**：JetBrains IntelliJ IDEA 中的 Augment AI 助手插件
- **💾 数据位置**：IDEA 的配置目录中的 XML 格式数据
- **🎯 特点**：支持 Java 开发环境的专业代码对话


#### 5. **PyCharm Augment 对话**
- **📍 来源**：JetBrains PyCharm 中的 Augment AI 助手插件
- **💾 数据位置**：PyCharm 的配置目录中的 XML 格式数据
- **🎯 特点**：专门针对 Python 开发的代码辅助对话


## 🚀 快速开始

### 🐳 推荐方式：Docker Compose（一键部署）

**📋 环境要求**：
- Docker 20.0+
- Docker Compose 2.0+

**⚡ 快速启动**：

#### 1. **克隆项目**
```bash
git clone <repository-url>
cd AI-IDE-Chat-Export-Tool
```

#### 2. **环境配置**（可选）

创建 `.env` 文件来自定义路径配置：
```bash
# 复制环境变量模板
cp .env.example .env

# 编辑配置（可选）
nano .env
```

**不同操作系统的默认路径**：

| 操作系统 | Cursor | VSCode | JetBrains |
|----------|--------|--------|-----------|
| **macOS** | `~/Library/Application Support/Cursor` | `~/Library/Application Support/Code` | `~/Library/Application Support/JetBrains` |
| **Linux** | `~/.config/Cursor` | `~/.config/Code` | `~/.config/JetBrains` |
| **Windows** | `%APPDATA%\Cursor` | `%APPDATA%\Code` | `%APPDATA%\JetBrains` |

#### 3. **一键启动**

使用便捷脚本（推荐）：
```bash
# 🚀 启动服务
./start.sh start

# 📊 查看状态
./start.sh status

# 📝 查看日志
./start.sh logs

# 🛑 停止服务
./start.sh stop

# 🔄 重启服务
./start.sh restart

# 🧹 清理环境
./start.sh clean
```

或直接使用 Docker Compose：
```bash
docker-compose up -d --build
```

#### 4. **访问应用**
🌐 打开浏览器访问：**http://localhost:3000**

> **💡 start.sh 脚本说明**：这是一个智能启动脚本，它会：
> - 自动检查 Docker 环境
> - 显示详细的启动进度
> - 提供实时状态监控
> - 支持一键清理和重置
> - 显示访问地址和使用提示

### 📦 传统方式：手动安装

**环境要求**：
- **Node.js** 16.0+
- **Python** 3.7+
- **npm** 或 **yarn**

**安装步骤**：

1. **克隆项目**
```bash
git clone <repository-url>
cd AI-IDE-Chat-Export-Tool
```

2. **安装前端依赖**
```bash
cd frontend
npm install
```

3. **构建前端生产版本**
```bash
npm run build
```

4. **安装后端依赖**
```bash
cd ../backend
pip install -r ../requirements.txt
```

**启动应用**：

1. **启动后端服务器**
```bash
cd backend
python server.py
```

2. **访问应用**
   打开浏览器访问：`http://localhost:5000`

> **注意**：请确保按照上述顺序启动，先构建前端，再启动后端服务器。应用运行在 5000 端口，而不是 3000 端口。

## 💡 使用指南

### 🔄 数据源切换

1. **选择数据源**：在页面顶部的数据源选择器中选择要查看的数据源
2. **自动加载**：系统会自动加载对应数据源的聊天记录
3. **无缝切换**：支持在 5 种数据源之间无缝切换
4. **实时统计**：显示每个数据源的对话数量统计

### 👀 查看对话

1. **浏览列表**：在聊天列表中浏览所有对话，按项目分组显示
2. **详细查看**：点击任意对话进入详细查看页面
3. **智能筛选**：支持按项目、时间、内容等信息筛选
4. **搜索功能**：使用搜索框快速查找特定对话

### 📤 导出功能

1. **选择对话**：在对话详情页面或列表页面选择要导出的对话
2. **选择格式**：支持三种导出格式：
   - **HTML**：适合浏览器查看，包含完整样式
   - **Markdown**：适合文档编辑，支持代码高亮
   - **JSON**：适合程序处理，包含完整元数据
3. **一键下载**：系统会生成包含完整对话内容的文件供下载
4. **批量导出**：支持选择多个对话进行批量导出

### ⚙️ 设置配置

1. **进入设置**：点击页面右上角的设置图标进入设置页面
2. **路径配置**：为每个数据源配置自定义路径（可选）
3. **实时验证**：系统会自动验证路径的有效性并提供实时反馈
4. **配置管理**：支持重置为默认路径或保存自定义配置
5. **状态监控**：查看每个数据源的连接状态和数据统计

## 🎨 核心特性

### 🧠 智能项目识别
- **自动提取**：从文件路径中智能提取项目名称
- **Git 支持**：支持 Git 仓库信息识别和显示
- **路径过滤**：智能过滤用户目录和系统目录
- **项目分组**：按项目自动分组显示对话记录

### 🎯 现代化 UI 设计
- **深色主题**：护眼舒适的深色主题设计
- **响应式布局**：完美适配桌面、平板、手机等设备
- **流畅动画**：丰富的过渡动画和交互效果
- **Material Design**：遵循 Google Material Design 设计规范

### ⚡ 强大的数据处理
- **多格式支持**：支持 SQLite、JSON、XML 等多种数据格式
- **智能解析**：自动识别和转换不同格式的聊天数据
- **错误恢复**：完善的错误处理和异常恢复机制
- **性能优化**：高效的数据提取和处理算法

### 🔧 高级配置管理
- **可视化设置**：直观的设置界面，支持路径自定义配置
- **实时验证**：路径有效性实时验证和状态反馈
- **配置持久化**：配置自动保存，支持一键重置
- **智能检测**：自动检测默认路径和回退机制

### 🔍 搜索和过滤
- **全文搜索**：支持对话内容的全文搜索
- **智能过滤**：按时间、项目、消息数量等条件过滤
- **实时搜索**：输入即搜索，无需等待
- **高亮显示**：搜索结果高亮显示匹配内容

## 🔄 项目演进

### 📈 相比原始项目的重大增强

本项目基于 [cursor-view](https://github.com/saharmor/cursor-view) 进行深度二次开发，实现了以下重大增强：

| 功能领域 | 原始项目 | 本项目增强 | 提升程度 |
|----------|----------|------------|----------|
| **数据源支持** | 仅 Cursor | 5 种数据源 | 🚀 500% |
| **导出格式** | 基础导出 | HTML/JSON/Markdown | 🚀 300% |
| **用户界面** | 简单界面 | Material-UI 深色主题 | 🚀 1000% |
| **数据处理** | 基础解析 | 智能多格式处理 | 🚀 500% |
| **配置管理** | 无 | 可视化设置系统 | 🚀 ∞ |
| **错误处理** | 基础 | 完善的异常处理 | 🚀 800% |

### 🎯 核心改进亮点

1. **🔄 多数据源统一**：从单一 Cursor 数据源扩展到五种主流 AI IDE 数据源
2. **📤 标准化导出**：支持多种格式的标准化导出，满足不同使用场景
3. **🎨 现代化设计**：全新的 Material-UI 设计语言和深色主题
4. **🤖 智能数据提取**：更强大的数据解析和转换能力，支持复杂数据结构
5. **📁 项目识别优化**：更准确的项目名称识别和分组算法
6. **🛡️ 错误处理增强**：完善的异常处理和用户友好的错误反馈
7. **⚙️ 设置管理系统**：可视化的配置界面和路径管理功能
8. **🔧 JetBrains 支持**：新增 IDEA 和 PyCharm Augment 数据源支持
9. **🐳 Docker 化部署**：完整的容器化解决方案，一键部署
10. **🔍 搜索和过滤**：强大的搜索和过滤功能

### 🙏 致谢

感谢 [saharmor/cursor-view](https://github.com/saharmor/cursor-view) 项目提供的基础架构和灵感。本项目在其基础上进行了大量的功能扩展和用户体验优化，致力于成为最好用的 AI IDE 聊天记录管理工具。

## 🆕 最新更新

### 📅 版本历史

#### v2.0.0 (最新版本)
- ✅ **完整的 Docker 化部署**：一键启动，支持多平台
- ✅ **智能环境变量配置**：支持 `.env` 文件自定义路径
- ✅ **增强的错误处理**：友好的错误信息和恢复机制
- ✅ **性能优化**：更快的数据加载和处理速度
- ✅ **UI/UX 改进**：更流畅的用户体验和视觉效果

#### v1.5.0
- ✅ **JetBrains IDE 支持**：新增 IDEA 和 PyCharm Augment 数据源
- ✅ **设置管理系统**：可视化的配置界面和路径管理
- ✅ **路径验证功能**：实时验证配置路径的有效性

#### v1.0.0
- ✅ **多数据源支持**：支持 5 种不同的 AI IDE 数据源
- ✅ **现代化界面**：Material-UI 深色主题设计
- ✅ **多格式导出**：HTML、JSON、Markdown 三种导出格式

### 🔮 即将推出

- 🔄 **批量操作**：支持批量导出和管理对话
- 📊 **数据分析**：对话统计和使用情况分析
- 🔍 **高级搜索**：支持正则表达式和复杂查询
- 🌐 **多语言支持**：界面国际化支持
- 📱 **移动端优化**：更好的移动设备体验

## 📁 项目架构

### 🏗️ 整体架构图

```
AI-IDE-Chat-Export-Tool/
├── 🎨 frontend/                    # React 前端应用
│   ├── src/
│   │   ├── components/             # React 组件库
│   │   │   ├── ChatDetail.js       # 📄 对话详情页面
│   │   │   ├── ChatList.js         # 📋 对话列表页面
│   │   │   ├── Header.js           # 🎯 页面头部组件
│   │   │   ├── PathConfigCard.js   # 🔧 路径配置卡片
│   │   │   └── SettingsPage.js     # ⚙️ 设置页面
│   │   ├── constants/              # 📊 配置常量
│   │   │   └── dataSourceConfig.js # 🔄 数据源配置
│   │   ├── utils/                  # 🛠️ 工具函数
│   │   └── styles/                 # 🎨 样式文件
│   ├── build/                      # 📦 构建输出目录
│   ├── public/                     # 🌐 静态资源
│   └── package.json                # 📋 前端依赖配置
├── 🐍 backend/                     # Python 后端服务
│   ├── server.py                   # 🚀 Flask 主服务器
│   ├── config_manager.py           # ⚙️ 配置管理器
│   ├── path_validator.py           # ✅ 路径验证器
│   ├── augment_extractor.py        # 🔍 Augment 数据提取器
│   ├── cursor_augment_extractor.py # 🔍 Cursor Augment 提取器
│   ├── idea_augment_extractor.py   # 🔍 IDEA Augment 提取器
│   ├── pycharm_augment_extractor.py # 🔍 PyCharm Augment 提取器
│   ├── conversation_parser.py      # 📝 对话解析器
│   ├── output_formatter.py         # 📤 输出格式化器
│   ├── cursor_chat_finder.py       # 🔍 Cursor 聊天查找器
│   └── extract_cursor_chat.py      # 📊 Cursor 聊天提取器
├── 🐳 Docker 配置
│   ├── Dockerfile                  # 🐳 Docker 镜像配置
│   ├── docker-compose.yml          # 🐳 Docker Compose 配置
│   └── nginx.conf                  # 🌐 Nginx 配置
├── 📋 配置文件
│   ├── config.json                 # ⚙️ 应用配置文件
│   ├── requirements.txt            # 🐍 Python 依赖
│   ├── .env.example               # 🔧 环境变量模板
│   └── start.sh                   # 🚀 启动脚本
└── 📚 文档
    ├── README.md                  # 📖 中文说明文档
    └── README_EN.md               # 📖 英文说明文档
```

### 🔧 技术栈详情

| 层级 | 技术 | 版本 | 用途 |
|------|------|------|------|
| **前端** | React | 18.x | 用户界面框架 |
| **UI 库** | Material-UI | 5.x | 组件库和主题 |
| **路由** | React Router | 6.x | 单页应用路由 |
| **HTTP 客户端** | Axios | 1.x | API 请求处理 |
| **后端** | Flask | 2.x | Web 服务框架 |
| **数据库** | SQLite | 3.x | 数据存储和查询 |
| **容器化** | Docker | 20.x+ | 应用容器化 |
| **Web 服务器** | Nginx | 1.x | 反向代理和静态文件服务 |

## 🤝 贡献指南

欢迎提交 Issue 和 Pull Request 来改进项目！

### 代码规范

- 前端：遵循 React 和 JavaScript 最佳实践
- 后端：遵循 PEP 8 Python 代码规范
- 提交信息：使用清晰的提交信息描述更改
- **分支管理**：请将所有代码贡献提交到 `dev` 分支，而非 `main` 分支

## 📄 许可证

本项目采用 [Apache License 2.0](LICENSE) 许可证。

## ⚙️ 环境配置

### 可选环境变量

```bash
# 启用Cursor聊天诊断模式（用于调试）
export CURSOR_CHAT_DIAGNOSTICS=1

# 自定义服务器端口（默认5000）
export PORT=5000
```

### 数据存储位置

不同操作系统下的数据存储位置：

**Windows**:

- Cursor: `%APPDATA%\Cursor\User\workspaceStorage`
- VSCode: `%APPDATA%\Code\User\workspaceStorage`
- IDEA: `%APPDATA%\JetBrains\IntelliJIdea[版本]\options`
- PyCharm: `%APPDATA%\JetBrains\PyCharm[版本]\options`

**macOS**:

- Cursor: `~/Library/Application Support/Cursor/User/workspaceStorage`
- VSCode: `~/Library/Application Support/Code/User/workspaceStorage`
- IDEA: `~/Library/Application Support/JetBrains/IntelliJIdea[版本]/options`
- PyCharm: `~/Library/Application Support/JetBrains/PyCharm[版本]/options`

**Linux**:

- Cursor: `~/.config/Cursor/User/workspaceStorage`
- VSCode: `~/.config/Code/User/workspaceStorage`
- IDEA: `~/.config/JetBrains/IntelliJIdea[版本]/options`
- PyCharm: `~/.config/JetBrains/PyCharm[版本]/options`

## 🔧 故障排除

### 🐳 Docker 相关问题

#### ❌ **Docker 容器无法启动**
**解决方案**：
1. **检查环境**：确认 Docker 和 Docker Compose 已正确安装
   ```bash
   docker --version
   docker-compose --version
   ```
2. **查看日志**：检查详细错误信息
   ```bash
   docker-compose logs ai-ide-chat
   ```
3. **端口检查**：确保端口 3000 未被占用
   ```bash
   lsof -i :3000  # macOS/Linux
   netstat -ano | findstr :3000  # Windows
   ```
4. **重新构建**：强制重新构建镜像
   ```bash
   docker-compose up -d --build --force-recreate
   ```

#### 🌐 **无法访问 localhost:3000**
**解决方案**：
1. **检查容器状态**：
   ```bash
   docker-compose ps
   docker-compose logs ai-ide-chat
   ```
2. **端口映射检查**：确认 docker-compose.yml 中的端口映射正确
3. **防火墙设置**：确保防火墙未阻止该端口
4. **端口冲突**：如果端口被占用，修改配置：
   ```yaml
   ports:
     - "3001:80"  # 改为其他端口
   ```

#### 📁 **IDE 数据目录挂载失败**
**解决方案**：
1. **检查目录存在**：
   ```bash
   # macOS
   ls -la ~/Library/Application\ Support/Cursor

   # Linux
   ls -la ~/.config/Cursor

   # Windows
   dir "%APPDATA%\Cursor"
   ```
2. **权限检查**：确保 Docker 有权限访问该目录
3. **路径调整**：根据操作系统调整挂载路径
4. **目录不存在**：如果目录不存在，可以注释掉相应的挂载配置

#### 🔄 **Docker 环境重置**
**完全重置命令**：
```bash
# 停止并删除当前项目的容器、卷、镜像
docker-compose down --rmi all --volumes --remove-orphans

# 清理构建缓存（可选；删除所有未使用的构建缓存）
docker builder prune -a

# 清理整个 Docker 系统（可选；删除所有未使用的资源，包括停止的容器和无用镜像）
docker system prune -a

# 重新构建和启动
docker-compose up -d --build
```

### 传统安装问题

**Q: 启动后无法访问 localhost:5000**
A: 请确保：

1. 后端服务器已正确启动且无错误信息
2. 端口 5000 未被其他程序占用
3. 防火墙未阻止该端口

**Q: 找不到聊天数据**
A: 请检查：

1. 对应的 IDE 是否已安装并使用过 AI 功能
2. 数据源选择是否正确
3. 相关插件是否已安装（如 Augment 插件）
4. 在设置页面检查数据源路径配置是否正确
5. 确认路径验证状态显示为有效

**Q: 导出功能不工作**
A: 请确认：

1. 浏览器允许文件下载
2. 有足够的磁盘空间
3. 对话数据不为空

**Q: 前端构建失败**
A: 尝试：

1. 删除 `node_modules`文件夹后重新 `npm install`
2. 检查 Node.js 版本是否符合要求
3. 清除 npm 缓存：`npm cache clean --force`

### 开发模式

如需进行开发，可以分别启动前后端：

```bash
# 启动前端开发服务器（端口3000）
cd frontend
npm start

# 启动后端服务器（端口5000）
cd backend
python server.py
```

## 📚 快速参考

### 🚀 常用命令

```bash
# 启动服务
./start.sh start

# 查看状态
./start.sh status

# 查看日志
./start.sh logs

# 重启服务
./start.sh restart

# 停止服务
./start.sh stop

# 清理环境
./start.sh clean
```

### 🔗 重要链接

- **🌐 应用访问**：http://localhost:3000
- **📊 设置页面**：http://localhost:3000/settings
- **📝 API 文档**：http://localhost:3000/api/settings
- **🐳 Docker Hub**：（待发布）
- **📖 在线文档**：（待发布）

### 📞 获取帮助

- **🐛 报告问题**：[GitHub Issues](https://github.com/your-repo/issues)
- **💡 功能建议**：[GitHub Discussions](https://github.com/your-repo/discussions)
- **📧 联系我们**：your-email@example.com
- **📚 文档**：查看本 README 文件

### 🏷️ 标签

`AI` `IDE` `Chat` `Export` `Cursor` `VSCode` `Augment` `JetBrains` `Docker` `React` `Flask` `Material-UI`

---

**🎉 感谢使用 AI IDE 聊天导出工具！**

如果这个项目对您有帮助，请考虑给我们一个 ⭐ Star！

