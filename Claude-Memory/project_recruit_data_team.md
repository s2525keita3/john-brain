---
name: project-recruit-data-team
description: 採用データ参謀チーム（6人自動点検）の常設化とGA4計測の確定事実（2026-06-15）
metadata: 
  node_type: memory
  type: project
  originSessionId: 50d744e7-569b-4c0d-bfe8-14e46d8c47e8
---

# 採用データ参謀チーム（世界一の自動点検）— 2026-06-15 構築

渋谷の依頼で「毎回、重要/警報/点検/測定指標を自動収集・チェックするチーム」を常設化した。

## 決定事項（渋谷承認済み）
- GA4取込：**Site Kit/GASでシートに自動転記**（私はシートを読むだけで自動化完結）
- 実行形式：**採用アドバイザー起動の度に自動点検**
- 保存先：**メモリ＋GitHub(john-brain)**

## 実装したもの
1. `recruit-advisor/SKILL.md` の起動手順に **A-3 自動点検プロトコル（6人チーム）** を組込
   - 6役：①データ収集官 ②計測点検官 ③ファネル分析官 ④媒体分析官 ⑤異常検知官 ⑥参謀(統合)
   - 指標体系：第0層 計測健全性／第1層 配信・流入／第2層 サイト行動／第3層 LINE／第4層 採用成果
   - 警報ルール：SNS投稿14日ゼロ🚨／LINE純増マイナス🚨／cta_click=0🚨／エントリー率前月比-50%⚠️／媒体応募ありで入職0継続⚠️／前年同期比70%減🚨
2. `recruit-advisor/ga4_to_sheet.gs`＋`SETUP_GA4_自動転記.md`：GA4+Search Console→シート自動転記（毎朝6時自動）。タブ：GA4日次/GA4ページ別(全ページ・直帰率)/GA4イベント/GA4流入元/GA4ランディング/GA4デバイス/GA4地域/SC検索ワード/SCページ別。Apps Scriptで「Google Analytics Data API」+「Search Console API」の2サービス追加が必要。SC_SITE_URL初期値=sc-domain:pure-john.com。
3. 初回点検で判明🚨：GA4ページ別のhostnameは全て pure-john.com で **recruit.pure-john.com が出ない**（採用LP本体は別プロパティ G-MZNNZC5SD2 で計測の疑い）。cta_clickイベントもこの箱には無い。本体サイトは /contact/37→form_start28→contact25 と問い合わせ動線は機能。SNS投稿は3/25で停止＝82日ゼロ🚨。

## GA4計測の確定事実（誤解禁止・検証済み）
- recruit.pure-john.com は pure-john.com の**サブドメイン**。両方とも**単一プロパティ G-PLYYTYJCR3（ストリームID 14972356304）にまとめて記録**。recruit用の別ストリームは作らない（二重計測になる）。
- 旧記載の recruit専用プロパティ(539505522/G-49MQNK08HN)・コンバージョン`form_submit_entry`は**実体の無い空箱**。追わない。
- 採用LPに**入力フォームは無い**。CV動線は各CTAボタン→公式LINE QR。**GA4で測れる最終地点は cta_click(LINEボタン押下)まで**。LINE登録〜入職はサイト外＝**Lステップ＋応募者シート**で測る。
- スプレッドシートID：`13t8UgmuBuONLZ-EjzWRp0mBoQikkP4RLoIjGOyf4dfI`

## データから判明した示唆（28日:5/18-6/14）
- メインサイト アクティブユーザー166。/station/が最多(169表示)、/staff/が滞在最長(50秒)、/recruit/到達は39人(23.5%)。
- 2026年は「危険信号期」＝主要指標 前年比70-80%減。SNS投稿が3月中旬停止→リード枯渇が根因。
- インスタ応募8→入職0（面接後不採用4・年齢NG多い）。TikTokは応募5→入職1。

## 次アクション候補
- GAS設置後「GA4自動転記つけた」と言われたら起動時に3タブを読む
- P1 SNS投稿再開（/sns）、P2 インスタ入職0問題の媒体ターゲット見直し
- cta_click率（/recruit/到達→ボタン押下）を次に点検

関連：[[session-20260607]]
