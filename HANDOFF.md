# HANDOFF — 雙 AI 接力交班檯

> **每次工作前**先讀本檔最上面的「目前狀態」。**每次工作結束前**更新「目前狀態」與「下一步」。
> 寫的時候假設下一個接手者是陌生人。

---

## 目前狀態（最新）
- **更新時間**：2026-07-12
- **最後操作者**：Claude Code（環境建置）
- **進度**：剛 fork 此 repo 並完成環境建置，**無進行中的影片**。
  - ✅ 依賴已裝：auto-editor、groq、openai（Python 套件）；系統已有 Python 3.14、ffmpeg 8.1、git
  - ✅ Groq API Key 已設定並驗證（`.env` 與 `~/.groq_api_key`）
  - ⏳ OpenAI API Key：尚未設定（封面走 Claude Code 生圖，之後需補 `~/.openai.env`）
  - ⏳ 個人化未完成：人物形象照、頻道封面風格、字幕詞彙表尚待換成自己的

## 下一步
- 補 OpenAI API Key（生封面用）
- 完成個人化清單：換人物形象照、`assets/style/cover-style.md`、`skills/audio-to-srt/references/vocabulary.md`、頻道名稱
- 丟第一支影片到 `raw/<影片代號>/`，用 `claude-youtube-video-workflow` 或 `codex-youtube-video-workflow` 開跑

## 備註
- 本 repo fork 自 `mathruffian-dot/2026-YouTube`；`output/` 內保留原作者範例成品供參考。
