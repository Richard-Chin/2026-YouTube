# 2026Youtube — YouTube 影片自動化工作流

## 專案簡介
本專案是一條 **YouTube 影片自動化生產線**。使用者把原始影片素材丟進 `raw/`，AI 代理人接力完成：
1. **剪輯 + 上字幕**（語音轉字幕 → 清字 → 燒入或外掛）
2. **封面圖生成**（gpt-image-2）
3. **影片描述 + 社群貼文 + SEO 關鍵字**
4. **10 個吸引人的標題候選**（供使用者挑選）

最終交付：剪好的影片、封面圖、文案包、標題清單。

## 雙 AI 接力工作機制
本專案會由兩個 AI 代理人協作，**Claude Code** 與 **OpenAI Codex** 接力工作。

- **Claude Code** 讀 `CLAUDE.md`（本檔）
- **Codex** 讀 `AGENTS.md`（與本檔內容對齊，給 Codex 看的版本）
- **共同交班檯**：`HANDOFF.md` —— 每次工作結束前必須更新「目前狀態 / 下一步」，下一個 AI 接手時先讀此檔

> 規則：**不要假設另一個 AI 知道你做了什麼。** 寫得像給陌生人看。

## 關鍵時程
- 無固定截止日期，依實際素材到位節奏推進

## 語言與風格
- 所有回應、文件、commit 訊息皆使用**繁體中文**
- 修改前先確認計畫，優先保留原有資料結構

## 資料夾結構
```
2026Youtube/
├── CLAUDE.md           # 本檔（Claude Code 讀）
├── AGENTS.md           # Codex 讀（與本檔對齊）
├── HANDOFF.md          # 雙 AI 共同交班檯
├── README.md           # 對人的快速說明
├── .gitignore
├── raw/                # 使用者上傳的原始影片素材
├── working/            # 中間產物（SRT、剪輯草稿）
├── output/
│   ├── thumbnails/     # 封面圖
│   ├── metadata/       # 描述 / 社群貼文 / SEO / 標題候選
│   └── final/          # 最終交付的成品影片
├── projects/           # 一支影片開一個子資料夾，便於管理
└── skills/             # 共用 Skill（Claude / Codex 皆可讀取）
    ├── audio-to-srt/   # 語音轉字幕（Groq Whisper-large-v3-turbo）
    └── cover-image/    # 封面圖生成（OpenAI gpt-image-2）
```

## Skills 使用須知
`skills/` 內的兩個 Skill 是**從全域 Skill 複製過來的本地副本**，目的是讓 Codex 也能在同一專案內讀到它們的 `SKILL.md` 與腳本。

| Skill | 路徑 | 觸發時機 |
|-------|------|---------|
| 語音轉字幕 | `skills/audio-to-srt/SKILL.md` | 影片有人聲、需要 SRT |
| 封面圖生成 | `skills/cover-image/SKILL.md` | 需要 YouTube 封面、社群圖 |

> Claude Code 端：仍以全域 `~/.claude/skills/` 為主，本資料夾的副本是給 Codex 讀的「離線版」。若全域 Skill 有更新，請同步更新本資料夾的副本。

## 標準工作流（每支影片）

1. 使用者把素材丟進 `raw/<影片代號>/`
2. 在 `projects/<影片代號>/` 建子資料夾，作為這支影片的工作空間
3. 觸發 `audio-to-srt` Skill → 產出 SRT，存到 `projects/<影片代號>/subs/`
4. 剪輯（依 SRT 標記決定保留/刪除片段）→ 輸出到 `output/final/`
5. 觸發 `cover-image` Skill → 產出封面圖到 `output/thumbnails/`
6. 撰寫描述 / 社群貼文 / SEO / 10 個標題 → 存到 `output/metadata/<影片代號>.md`
7. 更新 `HANDOFF.md`，標註本支影片狀態（草稿 / 待審 / 完成）

## Obsidian 關聯資料
- `2026Youtube/工作筆記.md` — 第二大腦中的對應筆記，存進度與點子

## 三處同步指引
| 平台 | 路徑 / 位置 | 用途 |
|------|-------------|------|
| Google Drive | `G:\我的雲端硬碟\2026Youtube\` | 主要工作目錄，Claude Code / Codex 直接讀寫 |
| Obsidian | `2026Youtube/` | 第二大腦，存創意點子與工作筆記 |
| GitHub | `mathruffian-dot/2026-YouTube` | 版本控制與備份（私有） |

## 工作注意事項
- 此資料夾位於 Google 雲端硬碟，跨裝置自動同步
- 影片原始檔可能很大，預設**不**進 git（見 `.gitignore`）
- 每次工作前後都要更新 `HANDOFF.md`
- API Key（Groq、OpenAI）放在使用者家目錄，**不**進 repo

## 最近更動紀錄
| 日期 | 變更摘要 | GDrive | Obsidian | GitHub |
|------|----------|--------|----------|--------|
| 2026-05-10 | 專案初始化、建立雙 AI 接力框架、複製兩個 Skill | ✅ | ✅ | ✅ |
