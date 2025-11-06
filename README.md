AI Agent with Long-Term Memory & Notes

Your personal AI that remembers everything — forever.

> "I prefer dark mode" → Remembers
> "Remind me to call Mom on Friday" → Saves as note  
> "What did I say last week?" → Recalls exactly

![Memory](https://img.shields.io/badge/%F0%9F%A7%A0%20Long--Term%20Memory-FF6B6B?style=for-the-badge) ![Notes](https://img.shields.io/badge/%F0%9F%93%9D%20Notes%20in%20Docs-4285F4?style=for-the-badge) ![AI](https://img.shields.io/badge/%F0%9F%A4%96%20GPT--4o--mini-00D26A?style=for-the-badge)



 Features

| Check | Feature |
|-------|--------|
| Check | Long-Term Memory — Stores personal facts |
| Check | Notes in Google Docs — Saves reminders, tasks |
| Check | 50-message window — Short-term recall |
| Check | Dual LLMs — GPT-4o-mini + DeepSeek-V3 |
| Check | Telegram Ready — Chat anywhere |
| Check | No database — Just Google Docs |


 How to Use

 1. Import Workflow
→ Click [ai-agent-long-term-memory.json](ai-agent-long-term-memory.json) → Copy all  
→ In n8n: New → Import from Clipboard (or drag file)

 2. Fix Red Warnings (Credentials)

| Credential | Name |
|----------|------|
| OpenAI | `OpenAi account` |
| DeepSeek | `deepseek` |
| Google Docs | `Google Docs account` |
| Telegram | `Telegram account` |

Setup:

Google Docs (Memory & Notes)
1. Create 2 Google Docs:
   - `Memory Doc` → Share with your Google account
   - `Notes Doc` → Same
2. Copy Doc IDs from URLs
3. In n8n → Replace `[Google Doc ID]` in:
   - `Retrieve Long Term Memories`
   - `Save Long Term Memories`
   - `Retrieve Notes`
   - `Save Notes`

 OpenAI / DeepSeek
1. Get API keys from [OpenAI](https://platform.openai.com/api-keys) & [DeepSeek](https://deepseek.com)
2. Add to n8n credentials

 Telegram (Optional)
1. Talk to [@BotFather](https://t.me/BotFather) → Get token
2. Set `chatId` in `Telegram Response` to your ID

 3. Test It

1. Click "Execute Workflow"
2. Open chat URL or Telegram
3. Say:
   > `I love coffee in the morning`

Bot saves to memory + replies naturally

> `Remind me to buy milk`

Bot saves to Notes Doc


 Live Chat Demo

After activation:  
`http://YOUR-N8N-URL/webhook/8ba8fa53-2c24-47a8-b4dd-67b88c106e3d`

> Replace `YOUR-N8N-URL`

 How It Works

```mermaid
graph TD
    A[User Message] --> B[Chat Trigger]
    B --> C[Load Memory + Notes]
    C --> D[AI Agent]
    D --> E{Save Memory?}
    E -->|Yes| F[Google Docs]
    D --> G{Save Note?}
    G -->|Yes| H[Google Docs]

   D --> I[Reply]
