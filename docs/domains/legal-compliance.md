# 法適合性照合 / Legal Compliance

> ⚠️ 初期対象スコープは [ADR-0003](../adr/0003-initial-target-scope-and-methods.md) で確定
> しています。細部の未決論点は [GitHub Issues](https://github.com/h-ikeda/building-designer/issues)（`domain:legal`）で管理します。
>
> ⚠️ The initial scope is fixed in [ADR-0003](../adr/0003-initial-target-scope-and-methods.md).
> Remaining open questions are tracked in [GitHub Issues](https://github.com/h-ikeda/building-designer/issues) under `domain:legal`.

## 目的 / Purpose

建築基準法をはじめとする日本の法令・基準への適合性を、設計モデルに対して照合する。

Check the design model against Japanese regulations and standards, primarily the Building
Standards Act (建築基準法).

## 対象スコープ / Scope

**差し当たり（MVP）/ Initial target** — 木造軸組構法 2 階建て・延べ面積 300㎡以下
（新 2 号建築物）を対象に、**採光・換気・集団規定**を中心とする
（[ADR-0003](../adr/0003-initial-target-scope-and-methods.md)）。

- **採光**: 居室の採光有効面積比（令 20 条）。
- **換気**: 換気設備、シックハウス対策（24 時間換気・内装制限、令 20 条の 2 系）。
- **集団規定**: 建蔽率・容積率、道路斜線・隣地斜線・北側斜線、日影規制、用途地域の
  用途制限、高さ・階数。
- **単体規定の基礎**: 居室の天井高、階段寸法、防火・準防火地域の基本判定など。

**将来 / Later** — 条例・地区計画の取り込み、確認申請図書一式の出力（B）、より広い
用途・規模への単体規定拡張（C/D）。

## 対象法令・基準 / Applicable Regulations & Standards

- 建築基準法・同施行令・関連告示（採光・換気・集団規定・関係する単体規定）。
- 用途地域等の都市計画情報（敷地条件として入力）。将来的に条例・地区計画。

## 入力・出力 / Inputs & Outputs

- **入力 / Input:** 共有ドメインモデル（建物形状・室・開口・外皮）と敷地・都市計画条件
  （用途地域、建蔽率/容積率の指定、道路・隣地条件、方位）。
- **出力 / Output:** 項目別の適合/不適合判定、根拠となる数値と条文、指摘一覧。

## 決定事項 / Decisions

- 採光・換気・集団規定を中心とする初期スコープ: [ADR-0003](../adr/0003-initial-target-scope-and-methods.md)。
