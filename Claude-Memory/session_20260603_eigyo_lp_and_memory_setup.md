---
name: session-20260603
description: 2026-06-03 作業ログ：営業LP復旧・本番公開・記憶システム設計
metadata:
  type: session-log
  date: 2026-06-03
---

## 営業LP（jnhc-sales-lp）

### 完了したこと
- 別AIが壊した文字化けを全修正（body全体をUTF-8正常日本語で再構築）
- s06画像差し替え（ChatGPT生成PNG → WebP変換）、テンプレート数「15点→13点」修正
- LINE公式アカウントCTAセクションを最下部に追加（ダークネイビー地）
- 全CTAボタン（6箇所）を「LINE で無料個別相談を申し込む」に統一
- LステップURL本番設定：`https://liff.line.me/1654945145-hHBq9Hq0?liff_id=1654945145-hHBq9Hq0&code=LFFGAHST`
- git init → GitHub公開（s2525keita3/jnhc-sales-lp）
- Vercel本番デプロイ：https://jnhc-sales-lp.vercel.app
- GitHub push → 自動デプロイ有効
- GA4（G-EJY6S44N0V）+ Clarity（x0t1vezjeo）設置済み・content_group「営業LP」

### 残タスク
- s12, s13, s15 画像差し替え（新画像待ち）
- カスタムドメイン設定（必要なら）

---

## 記憶・ナレッジシステム設計

### 確定したルール（CLAUDE.md §0 に記載済み）
- 保存指示 → ① Claude memory/ ② john_brain/ → git push → GitHub
- GitHub（s2525keita3/john-brain）が唯一の正本
- Obsidian は各PCで git clone → Obsidian Git プラグインで自動pull
- OneDrive 同期に頼らない

### セットアップ済み
- `john_brain` を git 初期化 → GitHub 接続
- `Claude-Memory/` フォルダ配下で記憶管理
- consult-advisor / john-advisor / recruit-advisor スキルをインストール・Obsidianにも保存

---

## 関連リンク
- 営業LP本番: https://jnhc-sales-lp.vercel.app
- 営業LP GitHub: https://github.com/s2525keita3/jnhc-sales-lp
- 記憶vault GitHub: https://github.com/s2525keita3/john-brain
