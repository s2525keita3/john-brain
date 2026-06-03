---
name: memory-dual-save-rule
description: 保存指示時は Claude memory + GitHub push（john-brain）の両方を必ず実行する最優先ルール
metadata:
  type: feedback
---

保存指示（「覚えておいて」「記録して」「保存して」など）を受けたとき、または自律的にメモリを保存するとき、必ず以下の両方を実行する。

**Step A**: `memory/` ディレクトリへ保存 + `MEMORY.md` インデックス更新

**Step B**: `C:\Users\s2525\OneDrive\john_brain\Claude-Memory\` に同名 `.md` を作成・更新し、git add → commit → push で GitHub へ反映

**Why:** GitHub が唯一の正本。Obsidian は各PCで GitHub から pull して同期する。OneDrive 同期には頼らない（PCごとに vault の状態が異なる可能性があるため）。push が完了して初めて「保存完了」。

**How to apply:** 保存系アクション全般に適用。GitHub push の省略は絶対禁止。

GitHub: https://github.com/s2525keita3/john-brain
Obsidian vault (このPC): C:\Users\s2525\OneDrive\john_brain\
Claude memory: C:\Users\s2525\.claude\projects\...\memory\
