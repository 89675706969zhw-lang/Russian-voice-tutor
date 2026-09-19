# NEGA AI

基于 Next.js 与 ElevenLabs Conversational AI 的实时语音对话网页。用户允许麦克风权限后，即可与已配置的 ElevenLabs Agent 开始或结束一段语音会话。

## 功能

- 实时语音对话与麦克风权限请求
- Agent 说话时显示实时文本和声波动画
- 会话连接、启动和结束状态反馈
- 使用服务端接口获取短期签名 URL，避免将 ElevenLabs API Key 暴露给浏览器

## 技术栈

- Next.js 15 / React 19
- TypeScript
- Tailwind CSS
- ElevenLabs Conversational AI React SDK

## 本地运行

1. 安装依赖：

   ```bash
   npm install
   ```

2. 在项目根目录创建 `.env.local`，填入 ElevenLabs 的配置：

   ```env
   AGENT_ID=your_elevenlabs_agent_id
   XI_API_KEY=your_elevenlabs_api_key
   ```

3. 启动开发服务：

   ```bash
   npm run dev
   ```

4. 在浏览器访问 `http://localhost:3000`，并在提示时允许使用麦克风。

## 可用命令

```bash
npm run dev    # 开发模式
npm run build  # 生产构建
npm run start  # 启动生产服务
```

## 项目结构

```text
app/
  api/signed-url/     # 向 ElevenLabs 请求会话签名 URL 的服务端接口
  page.tsx            # 首页
components/
  ConvAI.tsx          # 语音会话界面和交互逻辑
  ui/                 # 通用界面组件
public/
  avatar.png          # Agent 头像
  American.mp3         # 内置语音配置示例
doc/                  # 图文教程
```

## 配置说明

- `AGENT_ID`：ElevenLabs Conversational AI Agent 的 ID。
- `XI_API_KEY`：用于服务端创建签名 URL 的 ElevenLabs API Key。请仅保存在本地环境变量或部署平台的密钥配置中，切勿提交到仓库。

更多 ElevenLabs 配置说明请参阅 [Conversational AI 文档](https://elevenlabs.io/docs/product/introduction) 和 [React SDK 文档](https://elevenlabs.io/docs/libraries/conversational-ai-sdk-js)。
