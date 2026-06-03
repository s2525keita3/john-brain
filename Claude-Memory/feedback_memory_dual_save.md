---
name: memory-dual-save-rule
description: 「保存して」などの指示時は Claude memory と Obsidian/GitHub の両方に必ず保存する最優先ルール
metadata:
  type: feedback
---

保存指示（「覚えておいて」「記録して」「保存して」など）を受けたとき、または自律的にメモリを保存するとき、必ず以下の両方を実行する。

**Step A**: `memory/` ディレクトリへ保存 + `MEMORY.md` インデックス更新

**Step B**: `C:\Users\s2525\OneDrive\john_brain\Claude-Memory\` に同名 `.md` を作成・更新し、git add → commit → push で GitHub へ反映

**Why:** ユーザーが Obsidian（john_brain）と Claude memory を一元管理したいため。どちらか一方だけでは不完全。

**How to apply:** 保存系アクション全般に適用。省略は絶対禁止。

GitHub: https://github.com/s2525keita3/john-brain
Obsidian vault: C:\Users\s2525\OneDrive\john_brain\
Claude memory: C:\Users\s2525\.claude\projects\...\memory\
