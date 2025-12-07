[快速开始-Atlas800部署.md](https://github.com/user-attachments/files/24010504/-Atlas800.md)
# 🚀 Atlas 800 - Java教学知识库RAG系统 快速开始

---

## 📦 第一步: 下载部署包

### 方式1: 直接下载(推荐)
点击下载 → **[Java教学知识库部署包](https://www.genspark.ai/api/files/s/1ygFbpec?token=Z0FBQUFBQnBOUFVzMnRKVTVWdncxTlM5TDBjeTNfVlZZeGl4aFFTal9QR2ZGWHhCcktjdUpLbGF5TnF1Z1N1OVlvWUV5SHlTeW1QWGQ2Wkx5OXNzRE5GaFNicTBFamFBMFU5WGVQeWROV05ld2stb01nUWpMMFZocDhiYXZPdFhIM0k2SGxIa0EzQW5EYi1keXlxUUtjaHR1WllMbVc2eHBhalNIVDRZalVkNzd6aE5VWk9BZG1mOHBvM0k0VU02WW5jbk04X0NjdHlWdDkyZ1c2QzQyRlJENkV1ejJkOHdLYVlwOVlmSV94NFRIemdweno3a25qc2tUVEpfNmd3OXpRQlB0MmYxS1pTUGRGdXBfaGoxaFZnSFNiVkZick9ZQ0E9PQ)**

**文件信息**:
- **文件名**: `java_kb_atlas800.tar.gz`
- **大小**: 24 KB
- **包含内容**:
  - ✅ Java知识库RAG检索API服务
  - ✅ 25个结构化Java教学知识点
  - ✅ 向量化知识库(25×1024维)
  - ✅ 一键部署脚本
  - ✅ 服务管理工具

### 方式2: 使用wget命令(需先登录服务器)
```bash
cd ~
wget -O java_kb_atlas800.tar.gz "https://www.genspark.ai/api/files/s/1ygFbpec?token=Z0FBQUFBQnBOUFVzMnRKVTVWdncxTlM5TDBjeTNfVlZZeGl4aFFTal9QR2ZGWHhCcktjdUpLbGF5TnF1Z1N1OVlvWUV5SHlTeW1QWGQ2Wkx5OXNzRE5GaFNicTBFamFBMFU5WGVQeWROV05ld2stb01nUWpMMFZocDhiYXZPdFhIM0k2SGxIa0EzQW5EYi1keXlxUUtjaHR1WllMbVc2eHBhalNIVDRZalVkNzd6aE5VWk9BZG1mOHBvM0k0VU02WW5jbk04X0NjdHlWdDkyZ1c2QzQyRlJENkV1ejJkOHdLYVlwOVlmSV94NFRIemdweno3a25qc2tUVEpfNmd3OXpRQlB0MmYxS1pTUGRGdXBfaGoxaFZnSFNiVkZick9ZQ0E9PQ"
```

---

## 🖥️ 第二步: 连接到Atlas 800服务器

### 使用XShell连接
1. 打开**XShell**
2. 新建会话:
   - **主机**: `192.168.3.127`
   - **用户名**: 您的用户名
   - **端口**: 22
3. 连接并登录

### 使用XFTP上传文件(推荐)
1. 打开**XFTP**(或在XShell中按Alt+F)
2. 连接到`192.168.3.127`
3. 将下载的`java_kb_atlas800.tar.gz`上传到:
   ```
   /home/您的用户名/
   ```

---

## 🎯 第三步: 一键部署

### 在Atlas 800服务器上执行:

```bash
# 1. 创建工作目录
mkdir -p ~/dify_java_kb
cd ~/dify_java_kb

# 2. 解压部署包
tar -xzf ~/java_kb_atlas800.tar.gz

# 3. 进入目录
cd java_teaching_kb

# 4. 查看文件结构
ls -lh

# 5. 运行一键部署脚本
bash atlas800_deploy.sh
```

### 部署脚本会自动完成:
```
🚀 Atlas 800 - Java教学知识库RAG系统部署
============================================================

步骤1: 创建工作目录
✅ 工作目录创建完成

步骤2: 检查Python环境
✅ Python版本: Python 3.x.x

步骤3: 安装依赖包
✅ 依赖安装完成 (flask, flask-cors, numpy)

步骤4: 检查DeepSeek-32B服务
✅ DeepSeek-32B服务运行正常 (端口1025)

步骤5: 启动知识库API服务
============================================================
🚀 Java教学知识库RAG检索API服务
============================================================
📖 加载知识库...
✅ 向量加载完成: (25, 1024)
✅ 元数据加载完成: 25 个知识点

✅ 知识库加载成功!
📊 知识点总数: 25
📐 向量维度: (25, 1024)

============================================================
🌐 API端点:
  GET  /health                  - 健康检查
  POST /api/search              - RAG检索(Dify调用)
  GET  /api/knowledge/list      - 列出所有知识点
  GET  /api/knowledge/stats     - 统计信息
============================================================

🚀 启动API服务...
📍 监听地址: http://0.0.0.0:5000
💡 Dify配置URL: http://192.168.3.127:5000/api/search

按Ctrl+C停止服务
```

---

## ✅ 第四步: 验证部署

### 在Atlas 800服务器上测试

**打开新的SSH连接**(保持服务运行),然后执行:

```bash
cd ~/dify_java_kb/java_teaching_kb

# 使用管理脚本测试
./manage_atlas.sh test
```

**期望输出**:
```
🧪 测试Java教学知识库API服务
============================================================

1️⃣ 测试健康检查接口...
✅ 健康检查通过
响应: {"status":"ok","knowledge_count":25,"vector_shape":[25,1024]}

2️⃣ 测试RAG检索接口...
✅ RAG检索测试通过

3️⃣ 测试统计接口...
✅ 统计接口测试通过
```

### 从Dify服务器(192.168.3.129)测试连通性

```bash
# SSH连接到Dify服务器
ssh user@192.168.3.129

# 测试Atlas 800的知识库API
curl http://192.168.3.127:5000/health

# 测试DeepSeek-32B
curl http://192.168.3.127:1025/v1/models

# 测试RAG检索
curl -X POST http://192.168.3.127:5000/api/search \
  -H "Content-Type: application/json" \
  -d '{"query": "如何定义Java方法", "top_k": 3}'
```

---

## 🔧 第五步: 配置Dify工作流

### 访问Dify工作流编辑器
打开浏览器访问: **http://58.22.63.140:9191**

### 配置节点

#### 1️⃣ 开始节点
```yaml
添加输入变量:
  名称: query
  类型: 文本
```

#### 2️⃣ HTTP请求节点 - 知识库检索
```yaml
方法: POST
URL: http://192.168.3.127:5000/api/search

Headers:
  Content-Type: application/json

Body (JSON格式):
{
  "query": "{{start.query}}",
  "top_k": 3
}

⚠️ 重要: 
- 必须使用 {{start.query}} (双花括号)
- 不要使用 {query} 或 {start.query} (单花括号)
```

#### 3️⃣ LLM节点 - 教案生成
```yaml
提供商: OpenAI (选择OpenAI兼容)
API Endpoint: http://192.168.3.127:1025/v1
模型名称: deepseek-32b
API Key: sk-dummy (任意字符串)

System Prompt:
你是一名资深Java编程教师,擅长编写结构化的教学教案。

User Message:
用户问题: {{start.query}}

相关知识点:
{{http_request.body}}

请根据以上知识点,生成一份完整的Java教学教案,包含:
1. 教学目标(知识、能力、素质目标)
2. 教学重点与难点
3. 教学方法与策略
4. 详细的教学过程设计(180-240分钟)
5. 实践任务设计
```

#### 4️⃣ 回复节点
```yaml
内容: {{llm.text}}
```

#### 连接顺序
```
开始 → HTTP请求 → LLM → 回复
```

---

## 🎬 第六步: 测试Dify工作流

### 在Dify工作流编辑器中:
1. 点击右上角**"测试运行"**按钮
2. 输入测试查询:
   ```
   请生成一份关于Java方法定义的教案
   ```
3. 观察各节点输出:
   - **HTTP请求节点**: 检索到3个相关知识点 ✅
   - **LLM节点**: 生成完整的教案内容 ✅
   - **回复节点**: 显示最终教案 ✅

---

## 🛠️ 服务管理

### 后台运行服务(推荐)

如果您需要关闭SSH连接但保持服务运行:

```bash
cd ~/dify_java_kb/java_teaching_kb

# 停止前台服务(如果正在运行)
# 按 Ctrl+C

# 启动后台服务
./manage_atlas.sh start

# 查看状态
./manage_atlas.sh status

# 查看日志
./manage_atlas.sh logs

# 停止服务
./manage_atlas.sh stop

# 重启服务
./manage_atlas.sh restart
```

### 查看实时日志
```bash
tail -f ~/dify_java_kb/java_teaching_kb/api_service.log
```

---

## 🐛 常见问题快速解决

### ❌ 问题1: 端口5000被占用
```bash
# 查看占用进程
netstat -tuln | grep 5000
lsof -i :5000

# 停止冲突服务
./manage_atlas.sh stop

# 或手动杀死进程
kill -9 <PID>

# 重新启动
./manage_atlas.sh start
```

### ❌ 问题2: Dify无法访问Atlas 800
```bash
# 在Atlas 800上检查防火墙
sudo firewall-cmd --state

# 开放端口5000和1025
sudo firewall-cmd --permanent --add-port=5000/tcp
sudo firewall-cmd --permanent --add-port=1025/tcp
sudo firewall-cmd --reload

# 检查服务状态
./manage_atlas.sh status
netstat -tuln | grep -E "5000|1025"
```

### ❌ 问题3: 依赖安装失败
```bash
# 使用国内镜像源
pip3 install -i https://pypi.tuna.tsinghua.edu.cn/simple \
  flask flask-cors numpy

# 或用户级安装
pip3 install --user flask flask-cors numpy
```

---

## 📊 知识库内容概览

### 当前包含的教学知识点

| 课程 | 知识点数量 | 主要内容 |
|------|----------|---------|
| **Java开发入门** | 4个 | JDK安装、HelloWorld、基本数据类型、运算符 |
| **方法与数组** | 6个 | 方法定义、参数传递、重载、一维数组、二维数组 |
| **面向对象-封装与继承** | 7个 | 类与对象、封装、构造方法、继承、方法重写、super |
| **面向对象-抽象类与接口** | 8个 | 抽象类、接口、多态、instanceof、接口应用 |

**总计**: 25个结构化Java教学知识点

---

## 📚 下一步扩展

### 如何添加更多教学数据?

当您准备好真实的教学数据后:

1. **准备教案文档**(.docx格式)
2. **修改提取脚本**(`extract_teaching_plans.py`)
3. **重新构建知识库**:
   ```bash
   cd ~/dify_java_kb/java_teaching_kb
   
   # 提取知识点
   python3 extract_teaching_plans.py
   
   # 构建向量库
   python3 build_vector_kb.py
   
   # 重启服务
   ./manage_atlas.sh restart
   ```

---

## 🎉 完成!

**恭喜!您已成功部署Java教学知识库RAG系统!**

### 系统能力概览
✅ **25个Java教学知识点** 向量化存储  
✅ **RAG检索API服务** 端口5000  
✅ **DeepSeek-32B集成** OpenAI兼容接口  
✅ **Dify工作流** 完整配置  
✅ **自动化管理脚本** 一键启动/停止/测试  

### 接下来可以:
1. 在Dify工作流中测试教案生成
2. 根据实际需求调整System Prompt
3. 添加更多真实教学数据
4. 优化知识库检索效果

---

## 📞 需要帮助?

**如遇到问题,请提供**:
1. 错误日志: `./manage_atlas.sh logs`
2. 服务状态: `./manage_atlas.sh status`
3. 测试结果: `./manage_atlas.sh test`

**详细部署指南**: [点击查看完整文档](https://www.genspark.ai/api/files/s/waPNRGse?token=...)

---

**祝您使用愉快!** 🚀
