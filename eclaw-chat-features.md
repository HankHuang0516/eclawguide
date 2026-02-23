# Eclaw 聊天頁面 (Web) - Feature 樹狀圖與詳細說明

> 來源截圖：`chet_web.jpg`

---

## 一、樹狀圖 (Feature Tree)

```
聊天頁面 (Chat Page)
│
├── 1. 頂部導覽列 (Top Navigation Bar)
│   ├── 1.1 頁面標題 (Page Title) ─── "聊天"
│   └── 1.2 方案標籤 (Plan Badge) ─── "無限制"
│
├── 2. 訊息篩選列 (Message Filter Tabs)
│   ├── 2.1 全部 (All Messages)
│   ├── 2.2 特定實體篩選 (Entity Filter) ─── e.g. "🐷 Pig (#1)"
│   └── 2.3 我的訊息 (My Messages)
│
├── 3. 訊息顯示區域 (Message Display Area)
│   ├── 3.1 使用者訊息 (User Messages)
│   │   ├── 3.1.1 訊息氣泡 (Message Bubble) ─── 紫色/右對齊
│   │   ├── 3.1.2 發送對象標示 (Recipient Label) ─── "You → 🐷 Pig (#1)"
│   │   ├── 3.1.3 時間戳記 (Timestamp) ─── e.g. "12:06 AM"
│   │   ├── 3.1.4 已讀狀態 (Read Status) ─── "已讀"
│   │   └── 3.1.5 發送類型標記 (Send Type Tag) ─── e.g. "automated_test"
│   │
│   ├── 3.2 Bot 回覆訊息 (Bot Response Messages)
│   │   ├── 3.2.1 訊息氣泡 (Message Bubble) ─── 深色/左對齊
│   │   ├── 3.2.2 實體識別標示 (Entity Identity Label) ─── "🐷 Pig (#1)"
│   │   ├── 3.2.3 AI 生成回覆內容 (AI-Generated Content)
│   │   └── 3.2.4 時間戳記 (Timestamp)
│   │
│   └── 3.3 系統/狀態訊息 (System/Status Messages)
│       ├── 3.3.1 定時狀態更新 (Scheduled Status Update)
│       ├── 3.3.2 狀態內容 (Status Content) ─── "狀態: 線上"
│       └── 3.3.3 UTC 時間戳記 (UTC Timestamp)
│
├── 4. 收件者選擇列 (Recipient Selector Bar)
│   ├── 4.1 傳送給標籤 (Send-To Label) ─── "傳送給："
│   ├── 4.2 全選/全部 (Select All) ─── "✅ 全部"
│   ├── 4.3 個別實體勾選 (Individual Entity Checkboxes)
│   │   ├── 4.3.1 Entity #0 ─── "🦞 Lobster (#0)"
│   │   ├── 4.3.2 Entity #1 ─── "🐷 Pig (#1)"
│   │   └── 4.3.3 Entity #2 ─── "🦞 Lobster (#2)"
│   └── 4.4 多選機制 (Multi-Select Mechanism) ─── 可同時勾選多個實體
│
└── 5. 訊息輸入區域 (Message Input Area)
    ├── 5.1 附加功能按鈕 (Attachment Button) ─── "+"
    ├── 5.2 編輯/指令按鈕 (Edit/Command Button) ─── "✏️"
    ├── 5.3 文字輸入框 (Text Input Field) ─── placeholder "輸入訊息..."
    └── 5.4 傳送按鈕 (Send Button) ─── "傳送" (紫色圓形)
```

---

## 二、Feature 詳細表格 (Detailed Feature Tables)

### 表 1：頂部導覽列 (Top Navigation Bar)

| # | Feature | 中文名稱 | 說明 | UI 元素 | 備註 |
|---|---------|---------|------|---------|------|
| 1.1 | Page Title | 頁面標題 | 顯示目前頁面名稱「聊天」 | 左上角文字 | 固定標題，標示目前所在功能頁面 |
| 1.2 | Plan Badge | 方案標籤 | 顯示目前帳號方案等級「無限制」 | 右上角紅色標籤 | 表示目前為無限制(Premium)方案，無每日訊息數限制 |

---

### 表 2：訊息篩選列 (Message Filter Tabs)

| # | Feature | 中文名稱 | 說明 | UI 元素 | 備註 |
|---|---------|---------|------|---------|------|
| 2.1 | All Messages Filter | 全部訊息篩選 | 顯示所有實體的聊天訊息 | 紫色高亮按鈕「全部」 | 預設選中狀態，顯示整個裝置所有對話 |
| 2.2 | Entity-Specific Filter | 特定實體篩選 | 僅顯示與特定 Bot 實體的對話紀錄 | 帶 Emoji 圖示的按鈕，e.g.「🐷 Pig (#1)」 | 每個已綁定的實體會獨立顯示為一個篩選 Tab |
| 2.3 | My Messages Filter | 我的訊息篩選 | 僅顯示使用者自己發送的訊息 | 文字按鈕「我的訊息」 | 方便快速查找自己曾發出的對話內容 |

---

### 表 3：訊息顯示區域 - 使用者訊息 (User Messages)

| # | Feature | 中文名稱 | 說明 | UI 元素 | 備註 |
|---|---------|---------|------|---------|------|
| 3.1.1 | User Message Bubble | 使用者訊息氣泡 | 顯示使用者發送的文字內容 | 紫色背景、右對齊的圓角氣泡 | 與 Bot 回覆訊息在視覺上明確區分 |
| 3.1.2 | Recipient Label | 發送對象標示 | 標示該訊息發送的目標 Bot 實體 | 氣泡上方灰色文字，格式：「You → 🐷 Pig (#1)」 | 在多實體環境下辨識訊息發送對象 |
| 3.1.3 | Timestamp | 時間戳記 | 顯示訊息發送的時間 | 氣泡下方灰色小字，e.g.「12:06 AM」 | 使用本地時間格式顯示 |
| 3.1.4 | Read Status | 已讀狀態 | 標示 Bot 是否已接收/讀取該訊息 | 時間戳記下方顯示「已讀」 | 提供訊息送達確認回饋 |
| 3.1.5 | Send Type Tag | 發送類型標記 | 標示訊息的發送來源類型 | Recipient Label 旁的標記文字，e.g.「automated_test」 | 區分手動發送、自動化測試、排程發送等不同來源 |

---

### 表 4：訊息顯示區域 - Bot 回覆訊息 (Bot Response Messages)

| # | Feature | 中文名稱 | 說明 | UI 元素 | 備註 |
|---|---------|---------|------|---------|------|
| 3.2.1 | Bot Message Bubble | Bot 訊息氣泡 | 顯示 Bot 回覆的文字內容 | 深灰色背景、左對齊的圓角氣泡 | 支援長文回覆，含完整段落格式 |
| 3.2.2 | Entity Identity Label | 實體識別標示 | 標示回覆的 Bot 實體名稱與編號 | 氣泡上方紅色文字帶 Emoji，e.g.「🐷 Pig (#1)」 | 在多實體環境中辨識回覆來源 |
| 3.2.3 | AI-Generated Content | AI 生成回覆內容 | Bot 根據使用者問題產生的 AI 智能回覆 | 氣泡內的白色文字 | 回覆內容由後端 AI 模型（MiniMax 2.1 等）生成 |
| 3.2.4 | Timestamp | 時間戳記 | 顯示 Bot 回覆的時間 | 氣泡下方灰色小字 | 使用本地時間格式顯示 |

---

### 表 5：訊息顯示區域 - 系統/狀態訊息 (System/Status Messages)

| # | Feature | 中文名稱 | 說明 | UI 元素 | 備註 |
|---|---------|---------|------|---------|------|
| 3.3.1 | Scheduled Status Update | 定時狀態更新 | Bot 定期發送的心跳/健康狀態更新 | 深色氣泡，內容前綴「定時狀態更新」 | 由系統 Heartbeat 機制自動觸發，確認 Bot 在線 |
| 3.3.2 | Status Content | 狀態內容 | 顯示 Bot 目前的運行狀態 | 氣泡內文字，e.g.「狀態: 線上」 | 狀態值包含「線上」等，用於即時監控 Bot 健康 |
| 3.3.3 | UTC Timestamp | UTC 時間戳記 | 狀態更新的精確 UTC 時間 | 訊息內嵌文字，e.g.「2026-02-22 19:56 UTC」 | 使用 UTC 標準時間，便於跨時區問題排查 |

---

### 表 6：收件者選擇列 (Recipient Selector Bar)

| # | Feature | 中文名稱 | 說明 | UI 元素 | 備註 |
|---|---------|---------|------|---------|------|
| 4.1 | Send-To Label | 傳送給標籤 | 標示收件者選擇區域的用途 | 左側文字「傳送給：」 | 提示使用者可選擇訊息發送目標 |
| 4.2 | Select All | 全選/全部 | 一鍵勾選所有可用的 Bot 實體 | 勾選框「✅ 全部」 | 勾選後所有實體同時接收訊息（廣播模式） |
| 4.3 | Individual Entity Checkbox | 個別實體勾選 | 逐一選擇要接收訊息的 Bot 實體 | 帶 Emoji + 名稱的勾選框，e.g.「✅ 🦞 Lobster (#0)」 | 支援最多 4 個實體（Slot #0 ~ #3），可任意組合 |
| 4.4 | Multi-Select Mechanism | 多選機制 | 允許同時勾選多個實體作為收件者 | Checkbox 多選互動 | 實現一對多訊息發送，支援部分或全部實體選擇 |

---

### 表 7：訊息輸入區域 (Message Input Area)

| # | Feature | 中文名稱 | 說明 | UI 元素 | 備註 |
|---|---------|---------|------|---------|------|
| 5.1 | Attachment Button | 附加功能按鈕 | 提供附加檔案或額外功能的入口 | 圓形「+」按鈕（輸入框左側） | 可能支援圖片、檔案等附件功能 |
| 5.2 | Edit/Command Button | 編輯/指令按鈕 | 提供快捷指令或編輯功能的入口 | 斜筆圖示「✏️」按鈕 | 可能用於存取快捷指令、範本或進階編輯模式 |
| 5.3 | Text Input Field | 文字輸入框 | 使用者輸入聊天訊息的主要區域 | 圓角輸入框，placeholder「輸入訊息...」 | 支援文字輸入，可能支援多行輸入 |
| 5.4 | Send Button | 傳送按鈕 | 發送已輸入的訊息給選定的 Bot 實體 | 紫色圓形按鈕，標示「傳送」 | 點擊後將訊息發送至收件者選擇列中已勾選的實體 |

---

## 三、整體功能摘要 (Overall Feature Summary)

| 分類 | Feature 數量 | 說明 |
|------|-------------|------|
| 頂部導覽列 | 2 | 頁面標題 + 方案標籤 |
| 訊息篩選列 | 3 | 全部 / 特定實體 / 我的訊息 |
| 使用者訊息 | 5 | 氣泡 / 對象標示 / 時間 / 已讀 / 發送類型 |
| Bot 回覆訊息 | 4 | 氣泡 / 實體標示 / AI 內容 / 時間 |
| 系統狀態訊息 | 3 | 定時更新 / 狀態內容 / UTC 時間 |
| 收件者選擇列 | 4 | 標籤 / 全選 / 個別勾選 / 多選機制 |
| 訊息輸入區域 | 4 | 附加 / 指令 / 輸入框 / 傳送 |
| **總計** | **25** | |
