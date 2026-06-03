---
name: obsidian-github-setup
description: 他PCでObsidianをGitHub(john-brain)と同期するセットアップ手順
metadata:
  type: reference
---

GitHub が唯一の正本。新しいPCでObsidianを使い始めるときは以下の手順で初期設定する。

## 初回セットアップ（1回だけ）

1. GitHub から vault をクローン
   ```
   git clone https://github.com/s2525keita3/john-brain
   ```
2. Obsidian でそのフォルダを vault として開く
3. Obsidian の設定 → コミュニティプラグイン → **Obsidian Git** をインストール・有効化
4. Obsidian Git の設定：Auto pull を有効化（起動時・定期実行）

## 日常の同期フロー

```
Claude が保存
  ↓
① Claude memory/ に .md 保存
② john_brain/ に .md 保存 → git push → GitHub (正本)
  ↓
各PCの Obsidian Git が自動 pull → 最新に同期
```

## 関連リポジトリ

- GitHub: https://github.com/s2525keita3/john-brain
- このPCの vault: C:\Users\s2525\OneDrive\john_brain\

**Why:** OneDrive 同期に頼らない。PCごとに vault の状態が異なる可能性があるため、GitHub を経由することで全PC統一できる。

[[memory-dual-save-rule]]
