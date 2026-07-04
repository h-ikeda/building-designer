# 消費エネルギー計算 / Energy Calculation

> ⚠️ 初期対象スコープと計算方針は [ADR-0003](../adr/0003-initial-target-scope-and-methods.md)
> で確定しています。細部の未決論点は [GitHub Issues](https://github.com/h-ikeda/building-designer/issues)（`domain:energy`）で管理します。
>
> ⚠️ The initial scope and method are fixed in [ADR-0003](../adr/0003-initial-target-scope-and-methods.md).
> Remaining open questions are tracked in [GitHub Issues](https://github.com/h-ikeda/building-designer/issues) under `domain:energy`.

## 目的 / Purpose

省エネ基準等に基づき、建物の消費エネルギーを計算・評価する。

Calculate and evaluate a building's energy consumption based on energy-conservation standards.

## 対象スコープ / Scope

**差し当たり（MVP）/ Initial target** — 木造軸組構法 2 階建て・延べ面積 300㎡以下
（住宅）を対象に、**性能計算を基本**とする。仕様基準・誘導仕様基準には依存しない
（[ADR-0003](../adr/0003-initial-target-scope-and-methods.md)）。

- **外皮性能**: 外皮平均熱貫流率 UA・平均日射熱取得率 ηAC の算定（部位別の熱貫流率・
  日射熱取得の集計）。
- **一次エネルギー消費量計算**: 暖冷房・換気・給湯・照明の設計一次エネルギー消費量と
  基準値、BEI の算定。

**将来 / Later** — 非住宅用途への拡張、省エネ適合性判定への対応（C/D）。

方針: 構造のルート 1 と同様、仕様規定に頼らず性能を計算する方針で統一する。

## 対象法令・基準 / Applicable Regulations & Standards

- 建築物省エネ法および関連する基準（外皮基準、一次エネルギー消費性能基準）。
- 地域区分・気候データ（敷地条件として入力）。

## 入力・出力 / Inputs & Outputs

- **入力 / Input:** 共有ドメインモデル（外皮部位の構成・面積・方位、開口の仕様、室用途、
  設備仕様）と地域区分。
- **出力 / Output:** UA・ηAC、設計/基準一次エネルギー消費量、BEI、適合判定。

## 決定事項 / Decisions

- 性能計算（外皮性能＋一次エネルギー消費量）を基本とする初期スコープ: [ADR-0003](../adr/0003-initial-target-scope-and-methods.md)。
