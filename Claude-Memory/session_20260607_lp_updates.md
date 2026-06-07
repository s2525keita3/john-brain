---
name: session-20260607
description: 2026-06-07 作業ログ：営業LP各種修正・フォーム設置・画像差し替え
metadata:
  type: session-log
  date: 2026-06-07
---

## 営業LP（jnhc-sales-lp）本日の作業

### テキスト修正
- ヘッダーCTA：「無料相談申込」→「まず無料相談してみる」
- 課題3点を大文字強調リスト化（`.worry-list` CSS追加、赤バー付き太字）
- Before/Afterリード：「受講前と受講後の違いを、４つの軸で整理しました。」に変更
- フォーマットセクション：「毎月1回」→「毎月最低１回」＋共同MTG注記追加

### 画像差し替え
- `s12.webp`：投資対効果（ROI試算・なぜ割安か・3,300円）
- `s04b.webp`：3ヶ月伴走プログラムの進め方（設計→実行→自走準備）
- `s13b.webp`：各ステップの主な成果物（新規追加、s13の下に挿入）

### フォーム設置
- 全CTAボタンを `href="#form"` に変更（LINEへの遷移を廃止）
- LINEセクション削除
- 無料個別相談フォーム設置（7項目：会社名/氏名/LINE名/電話/メール/相談内容/希望日程×3）
- Web3Forms連携：access_key = `a1b76939-e4b9-425e-b267-cf6cfcab16b4`（s2525keita3@gmail.com宛）

### アナリティクス
- GA4カスタムイベント追加：
  - `cta_click`：どのボタンが押されたか（ラベル付き）
  - `form_submit`：フォーム送信完了
  - `form_view`：フォームセクション到達

### 残タスク
- s15画像差し替え（新画像待ち）
- カスタムドメイン設定（任意）

---

## 関連リンク
- 営業LP本番: https://jnhc-sales-lp.vercel.app
- 営業LP GitHub: https://github.com/s2525keita3/jnhc-sales-lp
- Web3Forms: https://app.web3forms.com
- GA4確認: レポート → エンゲージメント → イベント → cta_click / form_submit
