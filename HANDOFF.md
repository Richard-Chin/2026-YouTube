# HANDOFF — 雙 AI 接力交班檯

> **每次工作前**先讀本檔最上面的「目前狀態」。**每次工作結束前**更新「目前狀態」與「下一步」。
> 寫的時候假設下一個接手者是陌生人。

---

## 目前狀態（最新）
- **更新時間**：2026-05-10
- **最後操作者**：Claude Code（Opus 4.7）
- **進度**：專案初始化完成
  - 已建立資料夾結構（raw / working / output / projects / skills）
  - 已複製 `audio-to-srt` 與 `cover-image` 兩個 Skill 到 `skills/`
  - 已建立 CLAUDE.md / AGENTS.md / HANDOFF.md / README.md / .gitignore
  - Git 初始化、首版 commit、推上 GitHub 私有 repo `mathruffian-dot/2026-YouTube`
  - Obsidian 同名資料夾與工作筆記已建立
- **目前沒有處理中的影片**

## 下一步（給下一個 AI）
- 等使用者把第一支影片素材丟進 `raw/<影片代號>/`
- 收到後在 `projects/<影片代號>/` 開工作空間
- 依 `CLAUDE.md` 的「標準工作流」執行

## 已知議題 / 待解問題
- （無）

## 環境前置確認
| 項目 | 確認方式 | 備註 |
|------|---------|------|
| Groq API Key | `echo $GROQ_API_KEY` 或 `ls ~/.groq_api_key` | 給 audio-to-srt 用 |
| OpenAI API Key | `echo $OPENAI_API_KEY` | 給 cover-image 用 |
| ffmpeg | `ffmpeg -version` | 給音訊壓縮、剪輯用 |

---

## 交班歷史（新的寫在最上面）

### 2026-05-10 — Claude Code 專案初始化
- 建立雙 AI 接力工作框架
- 複製兩個 Skill 進 `skills/`
- Git + GitHub + Obsidian 三處同步完成
