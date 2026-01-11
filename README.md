# AI小说创作助手 (NovelAI)

一个功能完整的Android应用，用于AI辅助小说创作。支持自定义AI服务提供商、小说管理、章节编辑、知识库集成和AI辅助写作功能。

## 功能特性

### 核心功能
- **小说管理**: 创建、编辑、删除小说，支持添加简介和分类
- **章节管理**: 创建、排序、编辑章节
- **AI辅助写作**:
  - AI润色: 优化文笔，多种风格选择
  - AI续写: 基于上下文智能续写
  - 结合知识库内容进行创作
- **知识库**: 存储人物设定、世界观、剧情等信息，写作时随时调用
- **多AI服务商支持**:
  - OpenAI (GPT-4, GPT-3.5)
  - 智谱AI (GLM-4)
  - DeepSeek
  - Ollama (本地模型)

### 技术架构
- **Clean Architecture**: 分层架构 (Data-Domain-Presentation)
- **MVVM**: ViewModel + StateFlow 状态管理
- **Jetpack Compose**: 现代声明式UI
- **Hilt**: 依赖注入
- **Room**: 本地数据库
- **Retrofit**: 网络请求

## 项目结构

```
app/src/main/java/com/novelai/app/
├── data/                      # 数据层
│   ├── local/                # 本地数据
│   │   ├── dao/              # 数据访问对象
│   │   ├── entity/           # 数据库实体
│   │   └── preferences/      # DataStore配置
│   ├── remote/               # 远程数据
│   │   └── api/              # API接口
│   ├── repository/           # Repository实现
│   └── model/                # 数据模型
├── domain/                   # 领域层
│   ├── model/                # 领域模型
│   ├── repository/           # Repository接口
│   └── usecase/              # 业务用例
├── presentation/             # 表现层
│   ├── novel/                # 小说模块
│   ├── writing/              # 写作模块
│   ├── knowledge/            # 知识库模块
│   ├── settings/             # 设置模块
│   ├── components/           # 通用组件
│   └── theme/                # UI主题
├── core/                     # 核心模块
│   ├── ai/                   # AI服务封装
│   └── utils/                # 工具类
└── di/                       # 依赖注入
```

## 环境要求

- Android Studio Hedgehog | 2023.1.1 或更高版本
- JDK 17
- Android SDK API 24+ (Android 7.0)
- Kotlin 1.9.20

## 开发指南

### 1. 克隆项目
```bash
git clone <repository-url>
cd NovelAI
```

### 2. 在Android Studio中打开
- 打开 Android Studio
- 选择 `File > Open`
- 选择项目目录

### 3. 配置AI服务
在应用中添加你的AI服务API密钥：
1. 打开应用
2. 进入设置页面
3. 添加AI服务提供商
4. 输入API密钥

### 4. 构建项目
```bash
./gradlew build
```

### 5. 运行应用
```bash
./gradlew installDebug
```

## 主要依赖

```kotlin
// Compose
implementation("androidx.compose.ui:ui")
implementation("androidx.compose.material3:material3")

// Navigation
implementation("androidx.navigation:navigation-compose")

// Hilt
implementation("com.google.dagger:hilt-android")

// Room
implementation("androidx.room:room-runtime")

// Networking
implementation("com.squareup.retrofit2:retrofit:2.9.0")
```

## 开发路线图

- [x] 项目基础架构
- [x] 数据库设计 (Room)
- [x] AI服务抽象层
- [x] 小说管理功能
- [x] 章节编辑功能
- [x] AI润色/续写功能
- [x] 知识库基础功能
- [ ] 小说拆解/分析
- [ ] 导出功能 (Word/PDF)
- [ ] 数据云同步
- [ ] 写作统计

## 贡献指南

欢迎贡献代码、报告问题或提出新功能建议！

## 许可证

MIT License

## 作者

NovelAI Liuyao
