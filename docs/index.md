# ドキュメント索引 / Documentation Index

building-designer の設計文書の入口です。セッションを継続する際は、まずここから
現在地を把握してください。

Entry point for the design documentation of building-designer. When continuing across
sessions, start here to understand where the project stands.

---

## 運用ルール / Conventions

- **決定事項は `docs/`、未決事項は GitHub Issues。**
  `docs/` は確定した設計だけを載せます。検討中の論点や要判断事項は
  [GitHub Issues](https://github.com/h-ikeda/building-designer/issues) で管理します。
- **Decided matters go in `docs/`, open questions go in GitHub Issues.**
  `docs/` holds only settled design; anything still under discussion lives in Issues.
- 設計判断そのものは [ADR](./adr/) に記録します。ADR と Issue は相互にリンクします。
  Design decisions themselves are recorded as [ADRs](./adr/), cross-linked with Issues.

---

## 文書一覧 / Documents

| 文書 / Document | 内容 / Contents | 状態 / Status |
| --- | --- | --- |
| [`architecture.md`](./architecture.md) | 全体アーキテクチャの設計 / System architecture | スケルトン / Skeleton |
| [`domains/3d-modeling.md`](./domains/3d-modeling.md) | 3D モデリング / 3D Modeling | スタブ / Stub |
| [`domains/legal-compliance.md`](./domains/legal-compliance.md) | 法適合性照合 / Legal Compliance | スタブ / Stub |
| [`domains/energy.md`](./domains/energy.md) | 消費エネルギー計算 / Energy Calculation | スタブ / Stub |
| [`domains/structural.md`](./domains/structural.md) | 構造計算 / Structural Calculation | スタブ / Stub |
| [`adr/`](./adr/) | 設計判断の記録 / Architecture Decision Records | 運用中 / Active |

> 状態の目安 / Status legend: **スタブ (Stub)** = 節構成のみ、内容は未記入 /
> **スケルトン (Skeleton)** = 受け皿の節を用意、確定次第記入 /
> **運用中 (Active)** = 継続的に追記。

---

## 未決事項の追跡 / Tracking Open Questions

未決の論点は [GitHub Issues](https://github.com/h-ikeda/building-designer/issues) にあります。ラベルで絞り込めます。

Open questions are in [GitHub Issues](https://github.com/h-ikeda/building-designer/issues), filterable by label:

- 領域別 / By area: `domain:3d`, `domain:legal`, `domain:energy`, `domain:structural`
- 種別 / By type: `type:question`, `type:decision`, `type:adr`
