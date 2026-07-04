# 3D モデリング / 3D Modeling

> ⚠️ 初期対象スコープは [ADR-0003](../adr/0003-initial-target-scope-and-methods.md) で確定
> しています。細部の未決論点は [GitHub Issues](https://github.com/h-ikeda/building-designer/issues)（`domain:3d`）で管理します。
>
> ⚠️ The initial scope is fixed in [ADR-0003](../adr/0003-initial-target-scope-and-methods.md).
> Remaining open questions are tracked in [GitHub Issues](https://github.com/h-ikeda/building-designer/issues) under `domain:3d`.

## 目的 / Purpose

建物形状・空間・部材を 3D で表現し、他機能（法適合性照合・消費エネルギー計算・
構造計算）の入力となるモデルを構築する。全機能が参照する共有ドメインモデルの基盤を担う。

Build a 3D representation of building geometry, spaces, and components that serves as input to
the other features (legal compliance, energy, structural), forming the shared domain model.

## 対象スコープ / Scope

**差し当たり（MVP）/ Initial target** — 木造軸組構法 2 階建て・延べ面積 300㎡以下
（[ADR-0003](../adr/0003-initial-target-scope-and-methods.md)）。

- 軸組（柱・梁・土台・筋かい／耐力壁）、床・屋根、外皮、開口部、室（空間）のモデリング。
- 平面（間取り）入力から 3D を生成し、階を積み上げる。
- 敷地（境界・道路・方位）と建物の配置。
- 各機能が必要とする属性を保持する（部材の断面・樹種、外皮部位の熱性能、室の用途・
  面積・天井高、開口の寸法・仕様）。

**将来 / Later** — 平屋・3 階建てや多様な基礎・屋根形状（B）、他構造の部材表現（C）、
BIM/IFC 連携（D）。

## 入力・出力 / Inputs & Outputs

- **入力 / Input:** ユーザーによる平面・立面・部材・敷地の入力。
- **出力 / Output:** 共有ドメインモデル（建物 / 階 / 室 / 部材 / 開口 / 外皮 / 敷地）。
  構造・法令・省エネの各機能はこのモデルを入力として参照する。

## 決定事項 / Decisions

- 初期対象スコープと役割: [ADR-0003](../adr/0003-initial-target-scope-and-methods.md)。
