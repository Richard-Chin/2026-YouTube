# AGENTS.md — 給 Codex 的工作指南

> 這份檔案是 **OpenAI Codex** 在本專案的入口。Claude Code 讀的是 `CLAUDE.md`，內容與本檔對齊。

## 你是誰
你是 **OpenAI Codex**，與 **Claude Code** 在本專案接力完成 YouTube 影片自動化生產線。

## 開工前必讀
1. **`HANDOFF.md`** — 上一個 AI（可能是你自己上次、也可能是 Claude）留下的交班紀錄。**先讀這個**。
2. **`CLAUDE.md`** — 完整專案脈絡（與本檔對齊，但更詳細）。
3. **`README.md`** — 對人的快速說明。

## 專案目標
使用者把原始影片丟進 `raw/`，AI 接力完成：
1. 剪輯 + 上字幕
2. 封面圖
3. 描述 / 社群貼文 / SEO 關鍵字
4. 10 個吸引人的標題候選

## 你可以使用的 Skills
本專案 `skills/` 目錄存放兩個共用 Skill 的離線副本，讀 `SKILL.md` 即可使用：

| Skill | 路徑 | 用途 |
|-------|------|------|
| 語音轉字幕 | `skills/audio-to-srt/SKILL.md` | 音訊/影片 → SRT |
| 封面圖生成 | `skills/cover-image/SKILL.md` | gpt-image-2 生圖 |

## 資料夾結構
```
raw/         # 使用者素材
working/     # 中間產物
output/
  thumbnails/  # 封面
  metadata/    # 文案
  final/       # 成品影片
projects/<影片代號>/  # 每支影片的工作空間
skills/      # 共用 Skill
```

## 工作風格
- 繁體中文回應、繁體中文 commit 訊息
- 修改前先確認計畫
- **大檔案不要進 git**（影片、模型權重）
- API Key 從使用者家目錄讀（`~/.groq_api_key`、`OPENAI_API_KEY`），不准寫進 repo

## 收工前必做
更新 `HANDOFF.md`：
- 我做了什麼
- 目前在哪一步
- 下一個 AI 接手時要做什麼
- 有沒有踩到坑、有沒有待解問題

## 同步機制
- Google Drive 自動同步檔案
- GitHub 是版本備份：`mathruffian-dot/2026-YouTube`
- Obsidian 對應筆記：`2026Youtube/工作筆記.md`（給人讀的）
