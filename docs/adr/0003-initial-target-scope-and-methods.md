# 0003. 初期対象スコープと設計手法の方針 / Initial target scope and design methods

- **状態 / Status:** Accepted
- **日付 / Date:** 2026-07-04
- **解決した Issue / Resolves Issue:** #3（親 / parent）, #4, #5, #6, #7

## 背景 / Context

対象機能スコープ（3D モデリング / 法適合性照合 / 消費エネルギー計算 / 構造計算）と、
その優先順位・粒度が未確定だった（#3 とその子 Issue #4〜#7）。あらゆる建物を将来的に
カバーする構想だが、最初の実装対象を絞り込まなければ設計・実装を具体化できない。

The feature scope (3D modeling / legal compliance / energy / structural) and its priority and
granularity were undecided (#3 and its sub-issues #4–#7). The long-term vision covers all
building types, but the first implementation target must be narrowed to make design and
implementation concrete.

判断の前提として次の方針が示された。

- 段階的にあらゆる建物へ拡張するが、**まずは小規模建築物**から始める。
- 差し当たりの到達目標は、**確認申請が比較的容易な延べ面積 300㎡以下の木造軸組構法
  2 階建て**を一通り設計できること。
- 改正建築基準法（2025 年 4 月施行）では木造 2 階建ては **新 2 号建築物**に相当し、
  確認申請で構造・省エネの図書も審査対象となる。

## 決定 / Decision

### 対象機能スコープ / Feature scope

現行の 4 領域（3D モデリング / 法適合性照合 / 消費エネルギー計算 / 構造計算）を
**維持**する。統合・削除・追加は行わない。

Keep the four areas (3D modeling / legal compliance / energy / structural); no merges,
removals, or additions.

### 初期対象（MVP）/ Initial target (MVP)

最初の実装対象を次に限定する。

- 用途・構造: 専用住宅、**木造軸組構法**
- 規模: 地上 **2 階建て**、延べ面積 **300㎡以下**
- 法的位置づけ: 新 2 号建築物（確認申請で構造・省エネ図書も審査対象）
- 到達目標: この範囲の建物の確認申請が通せるレベルの設計を一通り行える

### 設計手法の方針 / Method policy

- **構造設計法はルート 1（許容応力度計算）を基本**とする。壁量計算などの仕様規定に
  依存した設計は基盤としない。
  - 理由: 今後の法改正で仕様規定は縮小が見込まれること、および他構造の建築物と
    できるだけ共有できる手法を用いたいこと。
- **省エネ計算は性能計算（外皮性能 UA・ηAC ＋ 一次エネルギー消費量計算）を基本**と
  する。仕様基準・誘導仕様基準には依存しない。
  - 理由: 構造と同様、仕様規定に頼らず性能を計算する方針で統一するため。
- 法適合性照合は、**採光・換気（シックハウス含む）・集団規定**を中心に、単体規定の
  基礎項目を対象とする。

### 領域別スコープと拡張ロードマップ / Per-area scope and roadmap

各領域の差し当たり実装分と将来分は、対応するドメイン文書
（`docs/domains/*.md`）に記載する。全体ロードマップは次の段階とする。

- **A（MVP）**: 木造軸組 2 階建て・300㎡以下。確認申請が通せるレベル。
- **B**: 小規模木造の幅出し（平屋・3 階建て、基礎・屋根形状の多様化、確認申請図書一式の
  出力、条例・地区計画）。
- **C**: 他構造・中規模へ（S 造・RC 造、構造ルート 2/3、混構造）。
- **D**: 大規模・高度化（省エネ適合性判定、BIM/IFC 連携、詳細解析、法令データ更新基盤）。

構造は許容応力度計算、省エネは性能計算を共通基盤に置くことで、A→C の構造・規模拡張時に
手法を積み増しやすくする。

## 影響 / Consequences

- 最初に作るべき機能が具体化し、共有ドメインモデル → 3D モデリング（入力）→ 構造・
  法令・省エネ、という実装順序の目安が定まる。
- The first features become concrete, with an implementation order: shared domain model →
  3D modeling (input) → structural / legal / energy.
- ルート 1・性能計算を基盤に選ぶことで、将来の仕様規定縮小や他構造への拡張に耐えやすい
  反面、MVP 時点の実装は仕様規定（壁量計算等）より計算量が多くなる。
- Choosing Route 1 and performance-based energy is robust to future deregulation and to
  other structures, but the MVP requires more computation than spec-based checks.
- 本スコープはプラットフォーム（#1）・技術スタック（#2）の選択とは独立に成立するが、
  これらの判断材料（計算負荷・データ量など）を提供する。
- This scope is independent of the platform (#1) and stack (#2) choices but informs them.
- 対象外（他構造・中大規模・平屋等）は当面スコープ外とし、必要時に新規 Issue で追跡する。
- Out-of-scope items are deferred and tracked via new Issues when needed.
