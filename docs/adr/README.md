# ADR — 設計判断の記録 / Architecture Decision Records

このディレクトリは、プロジェクトの設計判断を記録する ADR（Architecture Decision
Record）を保管します。ADR は「なぜその設計にしたか」を後から追えるようにするための
軽量な記録です（Michael Nygard 形式）。

This directory holds Architecture Decision Records (ADRs) — lightweight records of *why* a
design decision was made, so the reasoning can be traced later (Michael Nygard style).

---

## 運用ルール / Conventions

- **1 決定 = 1 ファイル。** ファイル名は連番付きで `NNNN-short-title.md`
  （例: `0001-record-architecture-decisions.md`）。
- **One decision = one file**, named `NNNN-short-title.md`.
- 新しい ADR は [`0000-template.md`](./0000-template.md) を複製して作成します。
- 一度確定した ADR は原則書き換えず、覆す場合は新しい ADR を追加して古い方を
  `Superseded`（廃止）にします。
- Existing ADRs are not rewritten; to reverse one, add a new ADR and mark the old one
  `Superseded`.

## Issue との連携 / Linking with Issues

- 未決事項は GitHub Issue（`type:question`）で管理し、決定が下りたら ADR を追加します。
- ADR 本文には解決した Issue 番号（`解決した Issue: #N`）を記載します。
- 対応する Issue には、決定要約と ADR へのリンクをコメントし、`type:decision` に更新して
  クローズします。

## 一覧 / Index

| ADR | タイトル / Title | 状態 / Status |
| --- | --- | --- |
| [0001](./0001-record-architecture-decisions.md) | ADR で設計判断を記録する / Record architecture decisions in ADRs | Accepted |
| [0002](./0002-track-open-questions-as-github-issues.md) | 未決事項は GitHub Issues で管理する / Track open questions as GitHub Issues | Accepted |
