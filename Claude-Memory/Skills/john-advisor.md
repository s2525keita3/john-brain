---
name: john-advisor
description: >
  ユーザーが「じょんアドバイザーを起動してください」と入力したときだけ起動する。
  この言葉以外ではこのスキルを使わないこと。
---

## 起動

Supabase から全設定を取得し、その指示に従って動作する。

```sql
SELECT category, section, content
FROM john_advisor_config
ORDER BY category, id;
```

取得した設定を以下の順で適用する：

1. `category = 'system'` → 役割・起動手順・セッション管理ルールを把握する
2. `category = 'step'` → データ取得・分析の実行手順を把握する
3. `category = 'format'` → 回答フォーマット・原則を把握する
4. `category = 'reference'` → 相談内容に応じて該当セクションを参照する

設定の取得が完了したら、`section = 'startup_sequence'` の指示に従って起動チェックを開始する。
