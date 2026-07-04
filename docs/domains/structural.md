# 構造計算 / Structural Calculation

> ⚠️ 初期対象スコープと設計手法は [ADR-0003](../adr/0003-initial-target-scope-and-methods.md)
> で確定しています。細部の未決論点は [GitHub Issues](https://github.com/h-ikeda/building-designer/issues)（`domain:structural`）で管理します。
>
> ⚠️ The initial scope and method are fixed in [ADR-0003](../adr/0003-initial-target-scope-and-methods.md).
> Remaining open questions are tracked in [GitHub Issues](https://github.com/h-ikeda/building-designer/issues) under `domain:structural`.

## 目的 / Purpose

構造関係規定に基づき、部材・架構の構造安全性を検証する。

Verify the structural safety of members and framing based on the structural provisions.

## 対象スコープ / Scope

**差し当たり（MVP）/ Initial target** — 木造軸組構法 2 階建て・延べ面積 300㎡以下を
対象に、**構造設計法はルート 1（許容応力度計算）を基本**とする。壁量計算などの仕様規定に
依存した設計は基盤としない（[ADR-0003](../adr/0003-initial-target-scope-and-methods.md)）。

- 荷重: 固定荷重・積載荷重・積雪荷重、地震力（層せん断力）、風圧力。
- 鉛直荷重に対する部材（柱・梁・土台）の許容応力度計算。
- 水平力に対する耐力壁・水平構面の検定、偏心・剛性の確認。
- 接合部の検討（許容応力度による）、基礎（べた基礎）の検討。

**将来 / Later** — 平屋・3 階建てや基礎形式の拡張（B）、S 造・RC 造・混構造、構造
ルート 2/3（層間変形角・剛性率・偏心率・保有水平耐力）（C）、詳細解析（D）。

方針: 許容応力度計算を共通基盤に置くことで、仕様規定の縮小や他構造への拡張に耐える。

## 対象法令・基準 / Applicable Regulations & Standards

- 建築基準法および同施行令の構造関係規定（許容応力度計算・荷重・材料）。
- 関連告示、および木質構造の許容応力度設計に関する基準。

## 入力・出力 / Inputs & Outputs

- **入力 / Input:** 共有ドメインモデル（架構・部材断面・樹種・接合部・荷重条件・
  地域係数・積雪/風の条件）。
- **出力 / Output:** 応力・変形、部材/接合部/基礎の検定比、判定結果、構造計算書ドラフト。

## 決定事項 / Decisions

- 構造設計法はルート 1（許容応力度計算）を基本: [ADR-0003](../adr/0003-initial-target-scope-and-methods.md)。
