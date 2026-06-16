---
name: reference-recruit-analysis-generic-playbook
description: 採用データ分析を他社/新規クライアントで行うときの汎用プレイブックと標準集計スクリプトの所在
metadata: 
  node_type: memory
  type: reference
  originSessionId: ec4efa06-5bfc-4ab4-8da3-9faeb1b9f4f4
---

# 採用データ分析 汎用プレイブック（他社展開用）

採用データの点検・分析は今後**他のクライアント会社でも繰り返す**ため、ぴゅあ事例から「分析の型」を抽出して会社非依存の形で別途用意した。新規クライアントの採用分析依頼が来たら、まずこれを開く。

## 所在
- 方法論：`docs/playbooks/recruit_data_analysis_generic.md`（§1のクライアント設定を埋めるだけで適用可）
- 標準集計スクリプト：`docs/playbooks/recruit_analyzer.py`
  - 使い方：`python docs/playbooks/recruit_analyzer.py <download_file_contentのJSON or xlsx>`
  - 出力：全タブ棚卸し／媒体×タイプ×カテゴリ集計／月次トレンド／リンククリック（導線）／列入力率監査／媒体別ファネル
  - 列はヘッダ名で照合するので**会社ごとに列位置が違っても動く**。

## 型のキモ（再発防止込み）
- 読込は必ず **xlsxダウンロード→openpyxl(data_only)→全タブ棚卸し**。`read_file_content`は大シートを途中で切る（誤検知の原因）。
- ダッシュボードタブは壊れて全0のことがある→**生データから再集計**。
- 個人情報タブは**集計のみ**（氏名等は出さない／CLAUDE.md RED）。
- 崩落の**起点月**を時系列で必ず確認（「今年から」と思い込まない）。
- 最頻の伸びしろ＝**リーチが大きい媒体とCVを生む媒体のズレ（導線の断絶）**。
- 列追加は**最右端のみ**（中間挿入はダッシュボード数式を壊す）。

## 棲み分け
- **会社固有の確定値・設定** → そのクライアントのプロジェクトメモリ＋GitHub。
- **方法論の改善** → 上記プレイブックを更新し `docs/playbooks/CHANGELOG.md` に内省。
- ぴゅあの常設自動運用は `recruit-advisor` スキル。

関連：[[project-recruit-data-team]] [[session-20260616-sns-analysis-and-metrics]]
