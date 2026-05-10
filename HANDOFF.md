# HANDOFF — 雙 AI 接力交班檯

> **每次工作前**先讀本檔最上面的「目前狀態」。**每次工作結束前**更新「目前狀態」與「下一步」。
> 寫的時候假設下一個接手者是陌生人。

---

## 目前狀態（最新）
- **更新時間**：2026-05-10
- **最後操作者**：Claude Code（Opus 4.7）
- **進度**：專案初始化 + 工作流定稿
  - 三個 Skill 都到位：`smart-cut`（新建）、`audio-to-srt`、`cover-image`
  - CLAUDE.md / AGENTS.md / HANDOFF.md 的「標準工作流」已對齊使用者需求：
    剪口播 → 字幕 → **10 個標題候選等選擇** → 以選定標題建資料夾 → 平行產封面/描述/社群/SEO
  - 資料夾命名規則：去除 `？！：／＼?!:/\\<>|"*` 等不合法字元
- **目前沒有處理中的影片**

## 下一步（給下一個 AI）
- 等使用者把第一支影片素材丟進 `raw/<影片代號>/`
- 第一次跑要先確認環境：`pip install auto-editor`、`ffmpeg -version`、`echo $GROQ_API_KEY`、`echo $OPENAI_API_KEY`
- 依 `CLAUDE.md` §「標準工作流（每支影片）」逐步執行
- 在 step 6 **務必停下來等使用者挑標題**，不要自己挑

## 已知議題 / 待解問題
- auto-editor 還沒在這台電腦驗證過。第一次跑要確認 `pip install auto-editor` 成功

## 環境前置確認
| 項目 | 確認方式 | 備註 |
|------|---------|------|
| Groq API Key | `echo $GROQ_API_KEY` 或 `ls ~/.groq_api_key` | 給 audio-to-srt 用 |
| OpenAI API Key | `echo $OPENAI_API_KEY` | 給 cover-image 用 |
| ffmpeg | `ffmpeg -version` | 給音訊壓縮、剪輯用 |

---

## 交班歷史（新的寫在最上面）

### 2026-05-10（下午）— Claude Code 工作流定稿
- 新增第三個 Skill `smart-cut`（auto-editor 包裝）
- 改寫 CLAUDE.md / AGENTS.md 的「標準工作流」章節：剪口播 → 字幕 → 10 標題 → 選定後建資料夾 → 平行產封面/文案
- 確立 `output/<標題>/` 為單一交付資料夾的命名與打包規範

### 2026-05-10 — Claude Code 專案初始化
- 建立雙 AI 接力工作框架
- 複製兩個 Skill 進 `skills/`
- Git + GitHub + Obsidian 三處同步完成
