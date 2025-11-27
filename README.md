# 🎵 AI Music Platform

> An intelligent platform integrating AI music recommendation and AI English conversation learning

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Java](https://img.shields.io/badge/Java-17+-orange.svg)](https://www.oracle.com/java/)
[![Vue](https://img.shields.io/badge/Vue-3.4+-green.svg)](https://vuejs.org/)
[![Flutter](https://img.shields.io/badge/Flutter-3.0+-blue.svg)](https://flutter.dev/)

## 📖 Introduction

AI Music Platform is a cross-platform intelligent application that provides personalized music recommendations and English learning assistance through AI technology. The project adopts a front-end and back-end separation architecture, supporting Web and mobile platforms (based on Flutter, supporting iOS, Android, and HarmonyOS).

## ✨ Core Features

### 🎵 AI Music Recommendation
- **Intelligent Recommendation Engine**: Natural language understanding based on ChatGPT-4 for precise music preference matching
- **Audio Feature Analysis**: Python deep learning models to analyze music features (rhythm, mood, style, etc.)
- **Personalized Music Library**: Support for music upload, playback, and collection management
- **Real-time Conversation Recommendation**: Get music recommendations through chat interactions

### 🗣️ AI English Conversation Learning
- **Intelligent Dialogue System**: ChatGPT-based English learning conversation assistant
- **Oral Practice**: Real-time voice conversation practice with pronunciation and grammar correction
- **Personalized Courses**: Customized learning content based on user proficiency level
- **Learning Progress Tracking**: Record learning history and growth trajectory

## 🏗️ Project Architecture

This project consists of three sub-projects, each independent yet complementary:

```
ai-music-platform/
├── aimusic_backend/        # Backend Services
│   ├── backend/            # Spring Boot API Service
│   ├── audio-processor/    # Python Audio Feature Extraction
│   └── database/           # Database Scripts
│
├── aimusic_frontend/       # Web Frontend
│   └── frontend/           # Vue 3 + TypeScript
│
└── aimusic_iOS/           # Mobile App (Cross-platform)
    ├── mm/                # iOS Native Shell (Swift/Objective-C)
    └── mm_flutter/        # Flutter Core Application
```

### 1️⃣ aimusic_backend (Backend Services)

**Tech Stack**:
- **API Service**: Spring Boot 3.2 + Spring Security 6
- **Database**: MySQL 8.0
- **AI Integration**: OpenAI ChatGPT-4 API
- **Audio Processing**: Python + Librosa

**Main Features**:
- User authentication & authorization (JWT)
- Music file management and feature extraction
- AI conversation service (music recommendation + English learning)
- RESTful API endpoints

**Documentation**: [aimusic_backend/README.md](./aimusic_backend/README.md)

### 2️⃣ aimusic_frontend (Web Frontend)

**Tech Stack**:
- **Framework**: Vue 3.4 + TypeScript
- **Build Tool**: Vite 5.0
- **UI Components**: Element Plus
- **State Management**: Pinia

**Main Features**:
- Responsive user interface
- Music player
- AI chat interface (music recommendation + English learning)
- User profile center

**Access URL**: http://localhost:3000

### 3️⃣ aimusic_iOS (Mobile App - Cross-platform)

**Tech Stack**:
- **Core Framework**: Flutter 3.0+ (Dart)
- **iOS Native Shell**: Swift 5.0 + Objective-C
- **Architecture**: MVVM + Flutter Hybrid Architecture
- **Dependency Management**: CocoaPods (iOS) + pub (Flutter)

**Main Features**:
- Native music playback experience
- AI English conversation practice (voice interaction)
- Offline functionality support
- Multimedia management (audio, video, images)
- Cross-platform UI consistency

**Runtime Environment**:
- iOS 13.0+
- Android 5.0+ (In Development)
- HarmonyOS 3.0+ (Planned)

## 🚀 Quick Start

### Prerequisites

- **Java**: JDK 17+
- **Node.js**: 18+
- **MySQL**: 8.0+
- **Python**: 3.8+ (for audio processing)
- **Flutter**: 3.0+ (for mobile development)
- **Xcode**: 13.0+ (for iOS development)
- **Android Studio**: 2022.1+ (for Android development, optional)
- **CocoaPods**: 1.11+ (for iOS dependencies)

### 1. Clone the Project

```bash
git clone https://github.com/your-username/ai-music-platform.git
cd ai-music-platform
```

### 2. Start Backend Services

```bash
# Install MySQL and create database
brew install mysql
brew services start mysql
mysql -u root -p ai_music < aimusic_backend/database/init.sql

# Start Spring Boot service
cd aimusic_backend/backend
mvn spring-boot:run

# Backend API will run at http://localhost:8080
```

### 3. Start Web Frontend

```bash
cd aimusic_frontend/frontend
npm install
npm run dev

# Frontend app will run at http://localhost:3000
```

### 4. Run Mobile App (Optional)

#### iOS Platform

```bash
# Install Flutter dependencies
cd aimusic_iOS/mm_flutter
flutter pub get

# Install iOS native dependencies
cd ../mm
pod install

# Open and run in Xcode
open mm.xcworkspace
```

#### Android Platform (In Development)

```bash
cd aimusic_iOS/mm_flutter
flutter run -d android

# Or open in Android Studio and run
```

#### HarmonyOS Platform (Planned)

```bash
# Support coming soon
```

### 5. Configure AI Services

Configure in `aimusic_backend/backend/src/main/resources/application.yml`:

```yaml
openai:
  api-key: your_openai_api_key
  model: gpt-4
```

## 📱 User Guide

### Web Usage Flow

1. **Register/Login**
   - Visit http://localhost:3000
   - Create an account or login with existing credentials

2. **AI Music Recommendation**
   - Go to "Chat" page
   - Describe the type of music you want (e.g., "Recommend some light music for studying")
   - AI will recommend music based on your needs
   - Click to play the recommended music

3. **AI English Learning**
   - Switch to "English Learning" mode
   - Practice English conversation with AI
   - AI will correct grammar and provide learning suggestions
   - View learning progress and history

### Mobile App Usage Flow

1. **Install App**
   - **iOS**: Run on a real device or simulator through Xcode
   - **Android**: Install via Android Studio or flutter run command
   - **HarmonyOS**: Coming soon

2. **Login**
   - Use the same account as the Web version

3. **Voice Conversation**
   - Use voice features for English speaking practice
   - Get real-time music recommendations

4. **Cross-platform Experience**
   - Unified UI experience based on Flutter
   - Seamless data synchronization across platforms

## 📊 Feature Comparison

| Feature Module | Web | iOS | Android | HarmonyOS | Description |
|---------------|-----|-----|---------|-----------|-------------|
| User Authentication | ✅ | ✅ | ⏳ | 📋 | Unified JWT authentication |
| AI Music Recommendation | ✅ | ✅ | ⏳ | 📋 | ChatGPT intelligent recommendation |
| AI English Conversation | ✅ | ✅ | ⏳ | 📋 | English learning assistant |
| Music Player | ✅ | ✅ | ⏳ | 📋 | Online/offline playback |
| Voice Interaction | ⏳ | ✅ | ⏳ | 📋 | Native voice support |
| Audio Feature Analysis | ✅ | - | - | - | Backend Python processing |
| Offline Features | - | ✅ | ⏳ | 📋 | Local caching |
| Cross-platform UI | - | ✅ | ⏳ | 📋 | Flutter unified rendering |

> ✅ Implemented | ⏳ In Development | 📋 Planned | - Not Applicable

**Cross-platform Advantages**:
- 🎯 **Unified Codebase**: 90%+ code reuse across platforms (Flutter-based)
- 🎨 **Consistent UI Experience**: Same visual and interaction experience on all platforms
- 🚀 **Rapid Iteration**: Develop once, deploy everywhere
- 🔧 **Native Performance**: Critical features optimized with platform-specific APIs

## 🛠️ Development Guide

### Backend Development

```bash
cd aimusic_backend/backend

# Run tests
mvn test

# Build for deployment
mvn clean package

# API Documentation
# Visit http://localhost:8080/swagger-ui.html
```

### Frontend Development

```bash
cd aimusic_frontend/frontend

# Development mode
npm run dev

# Production build
npm run build

# Code linting
npm run lint
```

### Mobile Development

#### Flutter Core Development

```bash
cd aimusic_iOS/mm_flutter

# Install dependencies
flutter pub get

# Run on iOS
flutter run -d ios

# Run on Android
flutter run -d android

# Hot reload development
# Press 'r' for hot reload during runtime
# Press 'R' for hot restart
```

#### iOS Native Shell Development

```bash
cd aimusic_iOS/mm

# Install dependencies
pod install

# Update dependencies
pod update

# Open in Xcode
open mm.xcworkspace
```

#### Android Native Development (In Development)

```bash
cd aimusic_iOS/mm_flutter

# Open in Android Studio
# File -> Open -> Select mm_flutter/android directory
```

## 📖 Documentation

- [Backend API Documentation](./aimusic_backend/README.md)
- [Project Specifications](./aimusic_backend/docs/PROJECT_SPECIFICATION.md)
- [Development Guide](./aimusic_backend/docs/DEVELOPMENT_GUIDE.md)
- [MVP Upgrade Plan](./aimusic_backend/docs/MVP_POST_UPGRADE_PLAN.md)
- [iOS-Flutter Integration](./docs/ISSUE_1_iOS_Flutter_Integration.md)
- [Frontend Authentication](./docs/ISSUE_3_Frontend_Auth.md)

## 🔒 Security

- **Authentication**: JWT Token authentication
- **Password Encryption**: BCrypt encrypted storage
- **API Security**: HTTPS + CORS configuration
- **Data Privacy**: Encrypted user data storage

## 📈 Roadmap

### Completed ✅
- [x] User authentication system
- [x] AI music recommendation feature
- [x] AI English conversation feature
- [x] Web frontend interface
- [x] iOS mobile application (Flutter)

### In Development 🚧
- [ ] **Android Application** (Flutter cross-platform support)
  - Basic feature migration
  - Android-specific optimizations
  - App store release preparation

### Planned 📋
- [ ] **HarmonyOS Application** (Huawei ecosystem support)
  - Flutter HarmonyOS adaptation
  - Huawei AppGallery listing
- [ ] Social sharing features
- [ ] Collaborative music playlists
- [ ] AI real-time voice translation
- [ ] Cross-platform data synchronization optimization
- [ ] More language learning support (Japanese, Korean, etc.)
- [ ] iPad / Tablet optimization
- [ ] Wearable device support (Apple Watch, Huawei Watch, etc.)

## 🤝 Contributing

Issues and Pull Requests are welcome!

1. Fork the project
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details

## 📞 Contact

- **Issue Tracking**: [GitHub Issues](https://github.com/your-username/ai-music-platform/issues)
- **Project Home**: [GitHub Repository](https://github.com/your-username/ai-music-platform)

## 🙏 Acknowledgments

- [OpenAI](https://openai.com/) - ChatGPT API
- [Spring Boot](https://spring.io/projects/spring-boot) - Backend framework
- [Vue.js](https://vuejs.org/) - Frontend framework
- [Element Plus](https://element-plus.org/) - UI component library
- [Librosa](https://librosa.org/) - Audio analysis

---

⭐ If you find this project helpful, please give it a star!

🎵 Let AI discover music for you, 🗣️ Let AI help you learn English!




# 中文版
# 🎵 AI音乐平台 (AI Music Platform)

> 集成AI音乐推荐与AI英语对话学习的智能平台

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Java](https://img.shields.io/badge/Java-17+-orange.svg)](https://www.oracle.com/java/)
[![Vue](https://img.shields.io/badge/Vue-3.4+-green.svg)](https://vuejs.org/)
[![Flutter](https://img.shields.io/badge/Flutter-3.0+-blue.svg)](https://flutter.dev/)

## 📖 项目简介

AI音乐平台是一个跨平台智能应用，通过AI技术为用户提供个性化音乐推荐和英语学习辅导。项目采用前后端分离架构，支持Web端和移动端（基于Flutter，支持iOS、Android和HarmonyOS）。

## ✨ 核心功能

### 🎵 AI音乐推荐
- **智能推荐引擎**：基于ChatGPT-4的自然语言理解，精准匹配用户音乐偏好
- **音频特征分析**：使用Python深度学习模型分析音乐特征（节奏、情绪、风格等）
- **个性化音乐库**：支持音乐上传、播放和收藏管理
- **实时对话推荐**：通过聊天交互方式获取音乐推荐

### 🗣️ AI英语对话学习
- **智能对话系统**：基于ChatGPT的英语学习对话助手
- **口语练习**：实时语音对话练习，纠正发音和语法
- **个性化课程**：根据用户水平定制学习内容
- **学习进度跟踪**：记录学习历史和成长轨迹

## 🏗️ 项目架构

本项目包含三个子项目，各自独立又相互配合：

```
ai-music-platform/
├── aimusic_backend/        # 后端服务
│   ├── backend/            # Spring Boot API服务
│   ├── audio-processor/    # Python音频特征提取
│   └── database/           # 数据库脚本
│
├── aimusic_frontend/       # Web前端
│   └── frontend/           # Vue 3 + TypeScript
│
└── aimusic_iOS/           # 移动端（跨平台）
    ├── mm/                # iOS原生壳（Swift/Objective-C）
    └── mm_flutter/        # Flutter核心应用
```

### 1️⃣ aimusic_backend (后端服务)

**技术栈**：
- **API服务**：Spring Boot 3.2 + Spring Security 6
- **数据库**：MySQL 8.0
- **AI集成**：OpenAI ChatGPT-4 API
- **音频处理**：Python + Librosa

**主要功能**：
- 用户认证与授权（JWT）
- 音乐文件管理和特征提取
- AI对话服务（音乐推荐 + 英语学习）
- RESTful API接口

**详细文档**：[aimusic_backend/README.md](./aimusic_backend/README.md)

### 2️⃣ aimusic_frontend (Web前端)

**技术栈**：
- **框架**：Vue 3.4 + TypeScript
- **构建工具**：Vite 5.0
- **UI组件**：Element Plus
- **状态管理**：Pinia

**主要功能**：
- 响应式用户界面
- 音乐播放器
- AI对话聊天界面（音乐推荐 + 英语学习）
- 用户个人中心

**访问地址**：http://localhost:3000

### 3️⃣ aimusic_iOS (移动端 - 跨平台)

**技术栈**：
- **核心框架**：Flutter 3.0+（Dart）
- **iOS原生壳**：Swift 5.0 + Objective-C
- **架构**：MVVM + Flutter混合架构
- **依赖管理**：CocoaPods（iOS）+ pub（Flutter）

**主要功能**：
- 原生音乐播放体验
- AI英语对话练习（语音交互）
- 离线功能支持
- 多媒体管理（音频、视频、图片）
- 跨平台UI一致性

**运行环境**：
- iOS 13.0+
- Android 5.0+（开发中）
- HarmonyOS 3.0+（计划中）

## 🚀 快速开始

### 环境要求

- **Java**：JDK 17+
- **Node.js**：18+
- **MySQL**：8.0+
- **Python**：3.8+（音频处理）
- **Flutter**：3.0+（移动端开发）
- **Xcode**：13.0+（iOS开发）
- **Android Studio**：2022.1+（Android开发，可选）
- **CocoaPods**：1.11+（iOS依赖）

### 1. 克隆项目

```bash
git clone https://github.com/your-username/ai-music-platform.git
cd ai-music-platform
```

### 2. 启动后端服务

```bash
# 安装MySQL并创建数据库
brew install mysql
brew services start mysql
mysql -u root -p ai_music < aimusic_backend/database/init.sql

# 启动Spring Boot服务
cd aimusic_backend/backend
mvn spring-boot:run

# 后端API将运行在 http://localhost:8080
```

### 3. 启动Web前端

```bash
cd aimusic_frontend/frontend
npm install
npm run dev

# 前端应用将运行在 http://localhost:3000
```

### 4. 运行移动应用（可选）

#### iOS平台

```bash
# 安装Flutter依赖
cd aimusic_iOS/mm_flutter
flutter pub get

# 安装iOS原生依赖
cd ../mm
pod install

# 在Xcode中打开并运行
open mm.xcworkspace
```

#### Android平台（开发中）

```bash
cd aimusic_iOS/mm_flutter
flutter run -d android

# 或在Android Studio中打开项目并运行
```

#### HarmonyOS平台（计划中）

```bash
# 支持即将推出
```

### 5. 配置AI服务

在 `aimusic_backend/backend/src/main/resources/application.yml` 中配置：

```yaml
openai:
  api-key: your_openai_api_key
  model: gpt-4
```

## 📱 使用指南

### Web端使用流程

1. **注册/登录**
   - 访问 http://localhost:3000
   - 创建账户或使用现有账户登录

2. **AI音乐推荐**
   - 进入"聊天"页面
   - 描述你想听的音乐类型（例如："推荐一些适合学习的轻音乐"）
   - AI会根据你的需求推荐音乐
   - 点击播放推荐的音乐

3. **AI英语学习**
   - 切换到"英语学习"模式
   - 与AI进行英语对话练习
   - AI会纠正语法、提供学习建议
   - 查看学习进度和历史记录

### 移动端使用流程

1. **安装应用**
   - **iOS**：通过Xcode运行到真机或模拟器
   - **Android**：通过Android Studio或flutter run命令安装
   - **HarmonyOS**：即将支持

2. **登录账户**
   - 使用Web端相同的账户登录

3. **语音对话**
   - 使用语音功能进行英语口语练习
   - 获取实时音乐推荐

4. **跨平台体验**
   - 基于Flutter的统一UI体验
   - 数据在不同平台间无缝同步

## 📊 功能特色

| 功能模块 | Web端 | iOS | Android | HarmonyOS | 说明 |
|---------|------|-----|---------|-----------|------|
| 用户认证 | ✅ | ✅ | ⏳ | 📋 | JWT统一认证 |
| AI音乐推荐 | ✅ | ✅ | ⏳ | 📋 | ChatGPT智能推荐 |
| AI英语对话 | ✅ | ✅ | ⏳ | 📋 | 英语学习助手 |
| 音乐播放器 | ✅ | ✅ | ⏳ | 📋 | 在线/离线播放 |
| 语音交互 | ⏳ | ✅ | ⏳ | 📋 | 原生语音支持 |
| 音频特征分析 | ✅ | - | - | - | 后端Python处理 |
| 离线功能 | - | ✅ | ⏳ | 📋 | 本地缓存 |
| 跨平台UI | - | ✅ | ⏳ | 📋 | Flutter统一渲染 |

> ✅ 已实现 | ⏳ 开发中 | 📋 计划中 | - 不适用

**跨平台优势**：
- 🎯 **统一代码库**：90%以上代码跨平台复用（基于Flutter）
- 🎨 **一致UI体验**：所有平台保持相同的视觉和交互体验
- 🚀 **快速迭代**：一次开发，多端发布
- 🔧 **原生性能**：关键功能使用平台原生API优化

## 🛠️ 开发指南

### 后端开发

```bash
cd aimusic_backend/backend

# 运行测试
mvn test

# 打包部署
mvn clean package

# API文档
# 访问 http://localhost:8080/swagger-ui.html
```

### 前端开发

```bash
cd aimusic_frontend/frontend

# 开发模式
npm run dev

# 生产构建
npm run build

# 代码检查
npm run lint
```

### 移动端开发

#### Flutter核心开发

```bash
cd aimusic_iOS/mm_flutter

# 安装依赖
flutter pub get

# 运行iOS
flutter run -d ios

# 运行Android
flutter run -d android

# 热重载开发
# 在运行时按 'r' 进行热重载
# 按 'R' 进行热重启
```

#### iOS原生壳开发

```bash
cd aimusic_iOS/mm

# 安装依赖
pod install

# 更新依赖
pod update

# 在Xcode中打开
open mm.xcworkspace
```

#### Android原生开发（开发中）

```bash
cd aimusic_iOS/mm_flutter

# 在Android Studio中打开
# File -> Open -> 选择 mm_flutter/android 目录
```

## 📖 详细文档

- [后端API文档](./aimusic_backend/README.md)
- [项目规范](./aimusic_backend/docs/PROJECT_SPECIFICATION.md)
- [开发指南](./aimusic_backend/docs/DEVELOPMENT_GUIDE.md)
- [MVP升级计划](./aimusic_backend/docs/MVP_POST_UPGRADE_PLAN.md)
- [iOS-Flutter集成](./docs/ISSUE_1_iOS_Flutter_Integration.md)
- [前端认证方案](./docs/ISSUE_3_Frontend_Auth.md)

## 🔒 安全说明

- **认证机制**：JWT Token认证
- **密码加密**：BCrypt加密存储
- **API安全**：HTTPS + CORS配置
- **数据隐私**：用户数据加密存储

## 📈 路线图

### 已完成 ✅
- [x] 用户认证系统
- [x] AI音乐推荐功能
- [x] AI英语对话功能
- [x] Web前端界面
- [x] iOS移动应用（Flutter）

### 开发中 🚧
- [ ] **Android应用**（Flutter跨平台支持）
  - 基础功能移植
  - Android特定优化
  - 应用商店发布准备

### 计划中 📋
- [ ] **HarmonyOS应用**（鸿蒙系统支持）
  - Flutter鸿蒙适配
  - 华为应用市场上架
- [ ] 社交分享功能
- [ ] 音乐播放列表协作
- [ ] AI语音实时翻译
- [ ] 跨平台数据同步优化
- [ ] 更多语言学习支持（日语、韩语等）
- [ ] iPad / 平板优化
- [ ] 智能穿戴设备支持（Apple Watch、华为手表等）

## 🤝 贡献

欢迎提交Issue和Pull Request！

1. Fork本项目
2. 创建特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 开启Pull Request

## 📄 许可证

本项目采用 MIT 许可证 - 查看 [LICENSE](LICENSE) 文件了解详情

## 📞 联系方式

- **问题反馈**：[GitHub Issues](https://github.com/your-username/ai-music-platform/issues)
- **项目主页**：[GitHub Repository](https://github.com/your-username/ai-music-platform)

## 🙏 致谢

- [OpenAI](https://openai.com/) - ChatGPT API
- [Spring Boot](https://spring.io/projects/spring-boot) - 后端框架
- [Vue.js](https://vuejs.org/) - 前端框架
- [Element Plus](https://element-plus.org/) - UI组件库
- [Librosa](https://librosa.org/) - 音频分析

---

⭐ 如果觉得这个项目有帮助，请给它一个星标！

🎵 让AI为你发现音乐，🗣️ 让AI帮你学习英语！

