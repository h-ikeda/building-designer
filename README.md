# building-designer

> 日本の建築物をワンストップで設計するためのソフトウェア
> One-stop software for designing buildings in Japan

---

## 概要 / Overview

**building-designer** は、日本の建築物の設計に必要な作業を一つのツールで完結させることを
目指すソフトウェアです。3D モデリングから、法令への適合性チェック、消費エネルギー計算、
構造計算までを一貫して扱うことを構想しています。

*building-designer* aims to be an all-in-one tool that covers the whole workflow of designing
a building in Japan — from 3D modeling to legal compliance checking, energy-consumption
calculation, and structural analysis.

現在は **基本設計フェーズ** にあり、複数のセッションを通じて要件・ドメインモデル・
アーキテクチャ方針を固めていきます。実装はまだ始まっていません。

The project is currently in the **basic design phase**. Requirements, the domain model, and
the architecture are being worked out over multiple sessions. Implementation has not started
yet.

---

## 対象機能スコープ（暫定）/ Feature Scope (tentative)

> ⚠️ **暫定・可変** — 以下は現時点の候補です。今後の検討で追加・統合・削除される
> 可能性があります。確定した内容だけを `docs/` に、検討中の論点は
> [GitHub Issues](https://github.com/h-ikeda/building-designer/issues) に記録します。
>
> ⚠️ **Tentative and subject to change** — the list below reflects current candidates only.
> Items may be added, merged, or dropped as design proceeds. Only decided matters live in
> `docs/`; open questions are tracked in [GitHub Issues](https://github.com/h-ikeda/building-designer/issues).

| 領域 / Area | 目的 / Purpose |
| --- | --- |
| 3D モデリング / 3D Modeling | 建物形状・空間・部材を 3D で表現し、他機能の入力となるモデルを構築する。 |
| 法適合性照合 / Legal Compliance | 建築基準法などの日本の法令・基準への適合性を照合する。 |
| 消費エネルギー計算 / Energy Calculation | 省エネ基準等に基づき建物の消費エネルギーを計算・評価する。 |
| 構造計算 / Structural Calculation | 構造関係規定に基づき部材・架構の構造安全性を検証する。 |

---

## 設計方針 / Design Principles

- **基本設計フェーズを優先 / Design-first**: いまは要件・ドメインモデル・アーキテクチャ
  方針を固める段階。実装や技術選定を急がない。
- **機能・技術は未確定で柔軟に / Keep scope and stack flexible**: 機能スコープも技術
  スタックも確定事項として固定せず、検討に応じて見直す。
- **日本の法令・基準への準拠を前提 / Built for Japanese regulations**: 建築基準法、
  省エネ基準、構造関係規定などへの準拠を前提に設計する。
- **決定は記録に残す / Record decisions**: 設計判断は ADR（`docs/adr/`）に、未決事項は
  GitHub Issue に残し、セッションを跨いでも判断の経緯を追えるようにする。

---

## ロードマップ / Roadmap

| フェーズ / Phase | 内容 / Contents | 状態 / Status |
| --- | --- | --- |
| **Phase 0** | ドキュメント環境整備（本作業）/ Documentation setup | 進行中 / In progress |
| **Phase 1** | 基本設計 — 要件定義・ドメインモデル・アーキテクチャ方針・技術選定 / Basic design | 未着手 / Not started |
| **Phase 2+** | 詳細設計・実装 / Detailed design & implementation | 未着手 / Not started |

各フェーズの具体的な検討項目は GitHub Issues で管理します。

Concrete work items for each phase are tracked as GitHub Issues.

---

## ドキュメント構成 / Documentation Map

| 場所 / Location | 内容 / Contents |
| --- | --- |
| [`README.md`](./README.md) | プロジェクトの概要・方針・ロードマップ（この文書）/ Overview, principles, roadmap |
| [`CLAUDE.md`](./CLAUDE.md) | 各セッションでの AI の動作ルール / Operating rules for AI sessions |
| [`docs/index.md`](./docs/index.md) | ドキュメントの索引・運用ルール / Documentation index & conventions |
| [`docs/architecture.md`](./docs/architecture.md) | 全体アーキテクチャの設計 / System architecture |
| [`docs/domains/`](./docs/domains/) | 領域別の設計文書 / Per-domain design docs |
| [`docs/adr/`](./docs/adr/) | 設計判断の記録（ADR）/ Architecture Decision Records |
| [GitHub Issues](https://github.com/h-ikeda/building-designer/issues) | 未決事項・検討中の論点 / Open questions and discussions |

> **運用の要点 / Convention**: `docs/` には **決定事項のみ** を記載し、**未決事項は
> GitHub Issues** で管理します。詳細は [`docs/index.md`](./docs/index.md) を参照。
>
> Only **decided matters** go into `docs/`; **open questions** are managed in GitHub Issues.
> See [`docs/index.md`](./docs/index.md) for details.
