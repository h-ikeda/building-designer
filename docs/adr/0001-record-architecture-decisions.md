# 0001. ADR で設計判断を記録する / Record architecture decisions in ADRs

- **状態 / Status:** Accepted
- **日付 / Date:** 2026-07-03
- **解決した Issue / Resolves Issue:** なし / none

## 背景 / Context

building-designer は複数セッションにまたがって基本設計を進める。設計判断の経緯を
残さないと、後のセッションで「なぜこの設計なのか」が分からなくなり、同じ議論を
繰り返すおそれがある。

building-designer's basic design proceeds across multiple sessions. Without a record of *why*
decisions were made, later sessions lose the rationale and risk re-litigating the same
questions.

## 決定 / Decision

設計上の判断は ADR（Architecture Decision Record）として [`docs/adr/`](./) に記録する。
形式は Michael Nygard 形式（状態・背景・決定・影響）に従い、1 決定 1 ファイル・連番管理と
する。

Record architecture decisions as ADRs in [`docs/adr/`](./), following the Michael Nygard
format (status, context, decision, consequences), one decision per numbered file.

## 影響 / Consequences

- 決定の経緯がリポジトリ内に残り、セッションを跨いで追跡できる。
- Decisions are traceable within the repository across sessions.
- ADR を書く手間が増えるが、基本設計フェーズでは経緯の保存を優先する。
- Writing ADRs adds overhead, but preserving rationale takes priority in the design phase.
