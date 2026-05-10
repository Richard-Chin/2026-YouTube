# 2026Youtube

YouTube 影片自動化工作流：原始素材丟進來，AI 接力產出剪好的影片、封面、文案、標題候選。

## 對 AI 的入口
- **Claude Code** → 讀 [`CLAUDE.md`](./CLAUDE.md)
- **OpenAI Codex** → 讀 [`AGENTS.md`](./AGENTS.md)
- **接班交接** → 讀寫 [`HANDOFF.md`](./HANDOFF.md)

## 對人的快速操作
1. 把影片素材丟進 `raw/<影片代號>/`
2. 跟 AI 說：「處理 `<影片代號>`」
3. 完成後會在 `output/` 拿到字幕檔、封面、文案、標題候選

## 共用 Skill
- `skills/smart-cut/` — 智能剪口播（auto-editor）
- `skills/audio-to-srt/` — 語音轉字幕（Groq Whisper）
- `skills/cover-image/` — 封面圖生成（gpt-image-2）

## 同步狀態
- Google Drive：`G:\我的雲端硬碟\2026Youtube\`
- GitHub：`mathruffian-dot/2026-YouTube`（私有）
- Obsidian：`2026Youtube/`
