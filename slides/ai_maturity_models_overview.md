---
marp: true
paginate: true
size: 16:9
theme: default
header: 'AI活用成熟度モデル 横断比較分析 & AI CoE設計フレームワーク'
footer: '作成日: 2026年5月1日 | 出典: 26モデル横断調査'
style: |
  section {
    font-family: "Yu Gothic UI", "Meiryo", sans-serif;
    font-size: 22px;
    padding: 40px 60px;
  }
  section.title {
    background: linear-gradient(135deg, #0f3460 0%, #16537e 100%);
    color: #fff;
    text-align: center;
    justify-content: center;
  }
  section.title h1 { color: #fff; font-size: 44px; }
  section.title h2 { color: #d8e8f5; font-size: 26px; font-weight: normal; }
  section.section-divider {
    background: #16537e;
    color: #fff;
    text-align: center;
    justify-content: center;
  }
  section.section-divider h1 { color: #fff; font-size: 56px; }
  h1 { color: #0f3460; border-bottom: 3px solid #16537e; padding-bottom: 8px; }
  h2 { color: #16537e; }
  table { font-size: 16px; border-collapse: collapse; margin: 8px 0; }
  th { background: #16537e; color: #fff; padding: 6px 10px; }
  td { padding: 5px 10px; border: 1px solid #ddd; }
  tr:nth-child(even) { background: #f4f7fb; }
  blockquote { border-left: 4px solid #16537e; padding-left: 12px; color: #555; }
  strong { color: #c0392b; }
  ul, ol { line-height: 1.55; }
---

<!-- _class: title -->

# AI活用成熟度モデル<br>横断比較分析 & AI CoE設計フレームワーク

## 国内外26モデルの比較から導く実装的指針

2026年5月1日

---

# アジェンダ

1. **背景と目的** — なぜ今、AI成熟度モデルか
2. **第1部 全体像** — 26モデルのランドスケープ
3. **第2部 横断比較** — レベル定義/評価軸/実務適用性
4. **第3部 推奨モデル** — MA-ATRIX を中心に
5. **第4部 統合5段階モデル** — 業界非依存の判定軸
6. **第5部 AI CoE実装ガイド** — 必須4軸・レベル別設計
7. **第6部 アンチパターン & 次のアクション**

---

<!-- _class: section-divider -->

# 背景と目的

---

# なぜ今 「AI成熟度モデル」 が必要か

| 背景 | 事実 |
|---|---|
| **PoC疲れの常態化** | 88%の生成AI PoCが本番化に失敗 (AWS) |
| **過大評価リスク** | 55%の組織が自社のRAI成熟度を過大評価 (BCG) |
| **定着の壁** | 国内企業の生成AI日常活用従業員はわずか **8.4%** (JUAS 2025) |
| **モデル乱立** | 国内外で **26モデル以上**、「成熟」の定義は最低6種類 |

> 自社が **何を「成熟」と定義するか** を最初に決めない限り、モデル選定もロードマップも決まらない。

---

# 本資料のゴール

- 国内外で公開されている **AI成熟度モデル26件** を構造化して比較
- 「どのモデルを、どの場面で使うべきか」 を **判断可能** にする
- AI CoE設計時に **必ず含めるべき4つの評価軸** を導出
- 業界・規模を問わず適用可能な **統合5段階モデル** を提示
- AI CoE のレベル別ミッション・規模・成果物を整理

**ターゲット**: AI CoE 設計担当 / DX推進責任者 / 経営層への説明資料を準備する方

---

# 結論サマリー (5点)

1. **「成熟」の定義は6種類** に分かれる ─ 戦略統合 / 業務埋め込み / 自律エージェント / 責任ある実践 / 人材文化 / 継続改善
2. **日本企業の AI CoE には MA-ATRIX (日立×Gen-AX) が最有力ベースライン** ─ 7軸×7段階で国内事情に最適化
3. **必須評価軸は 4 つ** ─ 組織・ガバナンス / 業務統合度 / データ・基盤 / 人材・文化
4. **レベルは 5〜7 段階、CMMI 混合命名** が現場合意しやすい
5. **自己評価は必ず外部指標または定量データで補正** ─ 自己過大評価が最大のリスク

---

<!-- _class: section-divider -->

# 第1部 全体像

---

# 調査対象モデル (26件) ─ カテゴリ別

| 区分 | モデル数 | 代表例 |
|---|---|---|
| 海外 Tech | 7 | Microsoft (3種) / IBM / AWS / Google Cloud / Salesforce / ServiceNow |
| 海外 コンサル | 6 | Gartner / IDC / Accenture / Deloitte / PwC / McKinsey / BCG / KPMG |
| 海外 NPO/政府 | 2 | MITRE / GSA |
| 学術論文 | 3 | Saari et al. / Hudaib et al. / HCAI-MM |
| ガバナンス特化 | 2 | Microsoft RAI MM / Credo AI |
| **国内** | **6** | **MA-ATRIX (日立×Gen-AX)** / NRI / NTTデータ / フォーティエンス / 経団連 / renue / リスキリングナビ |

> 参照のみ: IPA「DX推進指標」、経産省・総務省「AI事業者ガイドライン」

---

# レベル定義の 5 パターン

| パターン | 基本軸 | 強み | 弱み | 該当モデル数 |
|---|---|---|---|---|
| **A. 段階進化型** | ビジネス変革度 (Awareness→Transformational) | 経営説明力・共通言語 | 遷移基準が曖昧 | 7 |
| **B. プロセス成熟度型** | CMMI継承 (Initial→Optimized) | エンジニア親和性・再現性 | ビジネス価値が見えにくい | 6 |
| **C. 機能展開型** | データライフサイクル | 「何をやるか」が明確 | 組織軸が弱い | 1 |
| **D. 多次元×段階型** | 能力次元×段階 (2Dマトリクス) | 診断解像度・施策優先度 | 評価コスト高 | 5 |
| **E. 分類型** | 業績ベンチマーク (上位X%) | 投資判断材料 | ロードマップ別途必要 | 5 |

---

# 「成熟」 の 6 つのゴール像

| 派閥 | 成熟の本質 | 代表モデル |
|---|---|---|
| **戦略統合派** | AIが経営戦略の中核 | Gartner / Microsoft / Deloitte / PwC / McKinsey |
| **業務埋め込み派** | 業務プロセスへの統合度合い | IBM / **MA-ATRIX** / フォーティエンス |
| **自律エージェント派** | AIが自律的に動く状態 | Microsoft Agentic / Salesforce / IDC最新版 / **MA-ATRIX L6** |
| **責任ある実践派** | ガバナンス・倫理・公平性 | Microsoft RAI / BCG RAI / MITRE / Credo AI |
| **人材・文化派** | 全従業員のリテラシー・組織文化 | 経団連 / Accenture / renue成熟期 |
| **継続改善派** | プロセスの定量管理と継続改善 | IDC Optimized / CMMI 系統 |

---

<!-- _class: section-divider -->

# 第2部 横断比較

---

# 評価軸の網羅マトリクス (主要モデル抜粋)

◎=中核 / ○=あり / △=限定 / ×=なし

| モデル | 戦略 | データ | 組織 | プロセス | ガバナンス | 業務統合 | 自動化 |
|---|---|---|---|---|---|---|---|
| Gartner | ◎ | ○ | ◎ | ○ | ○ | ◎ | ○ |
| IDC MaturityScape | ○ | ○ | ◎ | ◎ | ○ | ◎ | ◎ |
| Microsoft Agentic | ◎ | ○ | ◎ | ◎ | ◎ | ◎ | ◎ |
| MITRE | ◎ | ○ | ○ | ○ | ◎ | ○ | △ |
| **MA-ATRIX** | ○ | ◎ | ◎ | ◎ | ◎ | ◎ | ◎ |
| NTTデータ | ◎ | ○ | ◎ | ◎ | ○ | ◎ | ○ |
| 経団連 (2019) | ○ | ○ | ◎ | △ | △ | ○ | △ |

> **MA-ATRIX は 10軸中 9 軸で ○ 以上** ─ 国内モデルとして網羅性が最も高い

---

# 業界別 重視されるポイント

| 業界 | 重視される側面 | 代表モデル |
|---|---|---|
| **金融** | ガバナンス・コンプライアンス・説明可能性 | PwC / MITRE / GSA |
| **製造業** | フィジカルAI・現場OT統合・予兆保全 | MA-ATRIX / Hitachi Lumada / BCG |
| **公共・政府** | 倫理・公平性・市民への説明責任 | MITRE / GSA AI CMM |
| **ヘルスケア** | データプライバシー・規制対応 | PwC / MITRE |
| **小売・CX** | 顧客体験変革・パーソナライゼーション | Salesforce / Accenture |
| **IT/SI** | エンジニアリング能力・MLOps/GenAIOps | MS GenAIOps / KPMG / IBM |
| **コンサル** | 知識労働者の協働、ナレッジ統合 | Asana×Anthropic / NRI / McKinsey |

---

# レベル数 × 軸数のトレードオフ

| レベル数 | 軸数 | 該当モデル | 適用場面 |
|---|---|---|---|
| 4 | 1次元 | IBM AI Ladder / MS AI MM / Salesforce | シンプル説明 (経営層初期啓発) |
| 4 | 多軸 | BCG / Accenture / renue | ベンチマーキング |
| 5 | 1次元 | Gartner / PwC / Deloitte / McKinsey | 標準的な経営説明 |
| 5 | 5–7軸 | Element AI / Microsoft Agentic | **中規模企業の自己診断** |
| 5 | 20+軸 | Microsoft RAI / MITRE | 大規模組織の精緻診断 |
| **7** | **7軸** | **MA-ATRIX** | **エージェンティック時代の精緻診断** |

> 実務指針: **5×5 (25セル) がワークショップで合意形成しやすい上限**。20軸以上は精緻だが合意困難

---

# 実務適用性ランキング (抜粋)

A: 経営説明 / B: 診断具体性 / C: ロードマップ落とし込み

| モデル | A | B | C | 総合 |
|---|---|---|---|---|
| **日立 MA-ATRIX** | ★★★★ | ★★★★★ | ★★★★★ | ★★★★★ |
| **BCG Deploy–Reshape–Invent** | ★★★★★ | ★★★★ | ★★★★★ | ★★★★★ |
| **Gartner** | ★★★★★ | ★★★★ | ★★★★ | ★★★★★ |
| **Asana × Anthropic 5C** | ★★★★★ | ★★★★ | ★★★★ | ★★★★★ |
| Accenture AI Achievers | ★★★★★ | ★★★ | ★★★ | ★★★★ |
| Microsoft Agentic | ★★★ | ★★★★ | ★★★★ | ★★★★ |
| MITRE | ★★ | ★★★★★ | ★★★★ | ★★★★ |

---

# 三軸分類 ─ どの軸を主に置くか

| 軸 | 代表モデル | 特徴 |
|---|---|---|
| **① 個人→部署→全社→変革** (組織展開軸) | 経団連 / リスキリングナビ / renue / フォーティエンス | 「誰が使っているか」を主軸。経営層の合意形成に有利 |
| **② PoC→実運用→変革** (価値実装軸) | Gartner / Element AI / Deloitte 3分類 / AWS | 短期→中期→長期の時間軸。投資配分判断と整合 |
| **③ 分析→予測→自動化→自律** (技術深化軸) | IBM AI Ladder / MS Agentic / Salesforce / **MA-ATRIX L6** | エンジニア組織・技術投資判断に有用 |

**3軸を統合的にカバーするモデル**: MA-ATRIX / Microsoft Agentic / MITRE

---

<!-- _class: section-divider -->

# 第3部 推奨モデル

---

# 推奨1位: MA-ATRIX (日立×Gen-AX)

**公開**: 2025年10月22日 / Creative Commons / GitHub: github.com/ma-atrix

| 観点 | 内容 |
|---|---|
| **構造** | 7段階 × 7軸 (組織 / コンプライアンス / 業務プロセス / 制度・仕組み / データMgmt / 生成AI活用 / 業務プロセスへの生成AI統合) |
| **レベル** | L0 不完全な → L1 実施された → L2 管理された → L3 定義された → L4 定量管理 → L5 最適化 → **L6 AI自律最適化** |
| **強み** | ① 国内事情に最適化 ② エージェント時代まで連続カバー ③ ゴール×プラクティス が軸×レベルで明示 ④ 1,000件超のユースケース実績 ⑤ 商用利用可 |
| **注意点** | 公開から半年、実装事例の蓄積はこれから |

> **AI CoE設計の標準ベースラインとして最有力**

---

# 推奨2位: Microsoft Agentic AI Adoption Maturity Model

**公開**: 2026年最新版 / Copilot Studio Guidance

| 観点 | 内容 |
|---|---|
| **構造** | 5段階 (CMMI型: Level 100→500) × 5本柱 |
| **5本柱** | ① AI戦略・体験 / ② ビジネス戦略 (人-エージェント協働再設計) / ③ AIガバナンス・セキュリティ / ④ テクノロジー・データ / ⑤ 組織・文化 |
| **強み** | ① エージェンティック時代を最も意識 ② Strategy on a Page (Vision/Objectives/Capabilities/Initiatives) 併設 ③ Decision Gates 設計思想 ④ ガバナンス・運用視点が分厚い |
| **注意点** | Copilot/Foundry前提の記述が多く、汎用化に翻訳が必要 |

---

# 用途別 推奨モデル組合せ

| 用途 | 推奨組合せ |
|---|---|
| **CoE全体設計のベースライン** | MA-ATRIX (評価軸) + Microsoft Agentic (ロードマップ思想) |
| **経営層への説明・予算獲得** | Gartner (共通言語) + NTTデータ「AIリーダー15%」(緊急性) + Accenture (4分類ベンチマーク) |
| **ガバナンス・倫理整備** | Microsoft RAI MM (24次元) + BCG RAI 7次元 + Credo AI |
| **データ整備優先フェーズ** | IBM AI Ladder (4 rungs) + Element AI (5次元) |
| **エージェンティック移行** | Microsoft Agentic + MA-ATRIX (L5→L6遷移) + Salesforce |
| **人材・カルチャー整備** | 経団連 (4対象別) + Accenture (組合せ能力) + MITRE (人材次元) |
| **中堅・中小企業向け** | リスキリングナビ4段階 + renue AI CoE 4レベル |

---

<!-- _class: section-divider -->

# 第4部 統合5段階モデル

---

# 統合モデルの設計方針

26モデルから本質的要素のみを抽出し、業界・規模を問わず適用可能な統合フレームワークを提示。

1. **5段階レベル** (経営層に説明しやすい) × **5評価軸** (多次元診断)
2. 各軸×レベルごとに **KPI を明確化** (実測可能)
3. **冗長性を排除**し、26モデルから本質的要素のみ抽出
4. **生成AI/エージェントAI時代** を前提とした設計 (古い ML 中心モデルではない)

> 拡張オプション: MA-ATRIX 流に L0「未着手」と L6「自律最適化」を加える 7段階版も用意可能

---

# 5段階レベルの定義

| Lv | 名称 | 一言定義 | 典型企業の状態 |
|---|---|---|---|
| **L1** | Awareness (認識) | AIへの関心はあるが、組織として活用なし | 経営が議題に上げるが実装活動なし |
| **L2** | Pilot (試行) | 個人・部署単位の試行・PoC実施 | ChatGPT Enterprise配布、個別実験 |
| **L3** | Operational (運用) | 一部業務でAIが本番運用、効果計測あり | 業務組込ユースケースが複数稼働 |
| **L4** | Scaled (全社展開) | 全社レベルでAIが業務不可欠、ガバナンス確立 | AI CoE機能、横展開が標準化 |
| **L5** | Transformational (変革) | AI起点の事業変革、エコシステム連携 | 新規ビジネスモデル、顧客接点の根本変革 |

---

# 5評価軸 × 5レベル マトリクス (1/2)

### ① 業務プロセス統合度
| Lv | 状態 |
|---|---|
| L1 | 業務とは無関係。試用のみ |
| L2 | 個人作業の補助 (要約・文案等) |
| L3 | 1–3業務プロセスに組込み、KPI 計測 |
| L4 | 主要業務の過半数に AI 組込 |
| L5 | AI起点で業務再設計、AI前提の新業務誕生 |

### ② 組織展開度
| Lv | 状態 |
|---|---|
| L1 | 一部のエンスージアストのみ |
| L2 | パイロット部門・個別チーム |
| L3 | 複数部署で運用、CoE 立ち上げ |
| L4 | 全社員 50%以上が日常活用 |
| L5 | 全社員 80%以上 + エコシステム連携 |

---

# 5評価軸 × 5レベル マトリクス (2/2)

### ③ 自動化レベル
| Lv | 状態 |
|---|---|
| L1 | 自動化なし |
| L2 | 個人作業を支援 (人間が必ず判断) |
| L3 | 部分自動化 (人間が承認) |
| L4 | 条件付き自律実行 (重要判断のみ人間) |
| L5 | マルチエージェント自律実行 |

### ④ データ活用度 / ⑤ ガバナンス成熟度
| Lv | データ | ガバナンス |
|---|---|---|
| L1 | サイロ化、品質保証なし | ルールなし、シャドーAI |
| L2 | パイロット用整備、限定アクセス | ガイドライン文書化、教育開始 |
| L3 | 業務単位統合、データカタログ | AIガバナンス委員会、リスクアセスメント |
| L4 | 全社プラットフォーム、リアルタイム | RAIフレーム全社実装、第三者監査可 |
| L5 | Living Data Backbone、競争優位 | 自律監視、業界標準化への寄与 |

---

# レベル判定 KPI 例 (L2→L3 移行)

3軸以上で該当レベルを満たすことを判定基準とする。

| 軸 | KPI | 閾値 |
|---|---|---|
| 業務統合 | 本番運用中の AI ユースケース数 | **3以上** |
| 業務統合 | 業務時間削減実績 | 計測されている (例: 月100時間削減) |
| 組織展開 | AI 利用社員比率 | **30%以上** |
| 組織展開 | AI CoE 有無 | あり (兼任でも可) |
| 自動化 | 業務プロセスへの自動化組込数 | 2以上 |
| データ | データカタログ整備率 | 主要業務データの 50% 以上 |
| ガバナンス | AI リスクアセスメント実施 | 全 AI ユースケースに対して実施 |
| ROI | AI 投資回収率 | 計測体制あり、初期 ROI 算出済 |

---

<!-- _class: section-divider -->

# 第5部 AI CoE 実装ガイド

---

# AI CoE設計の必須 4 軸

26モデル横串分析からの結論

| 必須軸 | 含まれる要素 | カバー率 |
|---|---|---|
| **1. 組織・ガバナンス** | 中央集権 vs アドバイザリー / 意思決定プロセス / リスク評価フレーム | **24中21モデル** ◎○ |
| **2. 業務統合度** | 業務へのAI組込み深度 / プロセス再設計 / 業務プロセスへの生成AI統合 | 24中19モデル ◎○ |
| **3. データ・基盤** | データガバナンス・品質 / 共通プラットフォーム (LLMゲートウェイ・MLOps・AgentOps・Observability) | 24中18モデル ◎○ |
| **4. 人材・文化** | リテラシー教育 / 専門人材確保 / AIネイティブ文化醸成 | 24中19モデル ◎○ |

**任意で追加すべき軸**: 自動化レベル (エージェント前提) / コンプライアンス (規制業界) / 業績インパクト (ROI重視)

---

# レベル別 AI CoE のミッションと規模

| 段階 | ミッション | 主要機能 | 規模 |
|---|---|---|---|
| **L1–L2** Awareness/Pilot 期 | 経営合意形成 + 試行支援 | 戦略策定 / ユースケース発掘 / パイロット支援 / ガイドライン草案 | **兼任 3–5名** |
| **L2–L3** Pilot/Operational 期 | PoC→本番化スループット向上 + ガバナンス整備 | 共通基盤整備 (LLM API/RAG/Vector DB) / MLOps・GenAIOps / Responsible AI 委員会 | **専任 5–15名** |
| **L3–L4** Operational/Scaled 期 | 全社展開の標準化 + 効果最大化 | ハブ&スポーク運営 / 全社共通AI基盤 / 標準化 / 横展開支援 / ROI 計測 | **専任 20–50名 + 各事業部分散** |
| **L4–L5** Scaled/Transformational 期 | 事業変革ドライバー + 業界標準寄与 | AI起点の新事業創造 / エコシステム構築 / プラットフォーム外販 (NRI/日立モデル) | **戦略中核組織、事業化で数百名** |

---

# AI CoE が L2→L3 で整備すべき 7 成果物

3–6ヶ月で整備することを推奨

1. **AI 利用ガイドライン** (情報セキュリティ・著作権・社外共有制限)
2. **AI ユースケース管理台帳** (ステータス・KPI・ROI 付き)
3. **AI リスクアセスメントシート** (DPIA類似、3–5段階リスクスコア)
4. **AI 効果測定指標 (KPI) テンプレート** (業務時間削減・品質改善・新規収益)
5. **AI 教育プログラム** (全社員リテラシー / 業務担当者活用 / エンジニア実装)
6. **AI 共通基盤アーキテクチャ図** (LLM API / Vector DB / RAG / 認証認可 / ログ監査)
7. **AI ガバナンス組織設計** (CoE / リスク委員会 / 各事業部のローカルチャンピオン)

---

# 各成熟度レベルでよく陥る罠と対策

| Lv | よくある罠 | 対策 |
|---|---|---|
| **L1** | 経営層が「AIで何ができるか」を理解せず永遠に L1 | 経営研修 / 他社事例見学 / 外部コンサル招聘 |
| **L2** | **PoC疲れ (88%が本番化失敗)** / 一部の熱心な人だけ | KPIセット (PoC→本番移行率) / ユースケース選定プロセス標準化 |
| **L3** | 部分最適 / サイロ化 / **シャドーAI** | AI CoE のハブ機能強化 / 共通基盤統合 / ガバナンス確立 |
| **L4** | 「全社展開したつもり」だが利用率が伸びない / 効果計測されない | 利用率 KPI / 効果 KPI / **ローカルチャンピオン制度** |
| **L5** | エコシステム連携の規制リスク / データ利用倫理問題 | 規制動向の先取り / 業界標準化への参画 / 第三者監査 |

---

<!-- _class: section-divider -->

# 第6部 アンチパターン & 次のアクション

---

# 5 つのアンチパターン

横断分析から見えた 「これをやると失敗する」 落とし穴

1. **経団連 AI-Ready ガイドラインだけで設計** ─ 2019年策定、生成AI/エージェント時代に未対応
2. **Gartner の「Operational」だけで自己評価して安心** ─ 自己申告 40% vs 定量評価では 10社に1社未満。BCG: 55% が過大評価
3. **ガバナンス整備だけで「成熟」とみなす** ─ Credo AI: 多くの企業が L3 (紙のポリシー) と L1 (シャドウAI) が混在
4. **PoC 数を成熟度の代理指標にする** ─ フォーティエンス: 「PoC数ではなく定着度が競争力の差」
5. **全軸均等に L5 を目指す** ─ 投資効率が悪く合意困難。MITRE 流に **柱別目標設定**

> 共通対策: **自己診断は必ず外部評価または定量指標で補正**

---

# AI CoE 設計の実装的ステップ

| Step | アクション | 参照モデル |
|---|---|---|
| 1 | 「成熟」の定義を経営層と握る (6種類から自社優先順位を決定) | 6つのゴール像 |
| 2 | 評価軸を 4必須+任意で確定 (自社版マトリクス作成) | MA-ATRIX 7軸 + 必須4軸 |
| 3 | レベル定義を作成 (CMMI混合命名で5–7段階) | MA-ATRIX 7段階準拠 |
| 4 | ゴールとプラクティスを評価軸×レベルで定義 | MA-ATRIX / MITRE |
| 5 | 自社現状を診断 (軸ごとに現在地と目標レベル設定) | MS Agentic Strategy on a Page |
| 6 | ロードマップ作成 (軸別優先度・四半期マイルストーン) | McKinsey Decision Gates |
| 7 | 四半期定点観測 (Evidence Pack 化) | McKinsey 5層測定 |

---

# 主要な一次資料 (リンク)

**国内発モデル (推奨)**
- 日立×Gen-AX MA-ATRIX: github.com/ma-atrix / hitachi.co.jp/New/cnews/month/2025/10/1022.html
- NRI AI CoE / AIガバナンス10要素: nri.com/jp/media/journal/20250818.html
- フォーティエンス 生成AI定着成熟度: fortience.com/insight/column/260107/
- renue AI CoE 完全ガイド 2026: renue.co.jp/posts/ai-coe-center-of-excellence-organization-enterprise-guide-2026

**海外主要モデル**
- Microsoft Agentic AI Adoption: learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/maturity-model-overview
- Gartner AI Maturity Model: gartner.com/en/chief-information-officer/research/ai-maturity-model-toolkit
- MITRE AI Maturity Model: aimaturitymodel.mitre.org
- IBM GenAI Adoption: ibm.com/architectures/hybrid/genai-adoption-maturity-model
- Accenture Art of AI Maturity: accenture.com/jp-ja/insights/artificial-intelligence/ai-maturity-and-transformation

---

<!-- _class: title -->

# Thank You

## ご質問・議論はこちらまで

AI CoE 設計プロジェクトチーム
2026年5月1日
