# 0002. 未決事項は GitHub Issues で管理する / Track open questions as GitHub Issues

- **状態 / Status:** Accepted
- **日付 / Date:** 2026-07-03
- **解決した Issue / Resolves Issue:** なし / none

## 背景 / Context

基本設計フェーズでは未決の論点が多数生じる。これらを設計文書（`docs/`）内に「未決」
「TBD」として書くと、文書が確定事項と検討中事項の混在で読みにくくなり、状態管理も
難しい。GitHub Issues は状態・ラベル・担当・親子関係などの管理機能を備える。

The basic design phase produces many open questions. Writing them inline in `docs/` as "TBD"
mixes settled and unsettled content and makes state hard to manage. GitHub Issues provide
state, labels, assignment, and parent/child relationships.

## 決定 / Decision

未決事項は **GitHub Issues** で管理し、`docs/` には **決定事項のみ** を記載する。

- 検討中の論点は `.github/ISSUE_TEMPLATE/design-question.yml` を用いて起票する。
- ラベル体系で分類する: 領域別 `domain:3d` / `domain:legal` / `domain:energy` /
  `domain:structural`、種別 `type:question` / `type:decision` / `type:adr`。
- 大きな論点はサブイシューに分解してよい。
- 決定が下りたら ADR を追加し、必要に応じて `docs/` に反映し、元の Issue に ADR への
  リンクを残してクローズする。

Track open questions in **GitHub Issues** and keep **only decided matters** in `docs/`, using
the design-question issue form and the label taxonomy above; decompose large questions into
sub-issues; and on decision, add an ADR, update `docs/` as needed, and close the Issue with a
link to the ADR.

## 影響 / Consequences

- `docs/` が常に「確定した設計」を表すため読みやすくなる。
- `docs/` stays readable as a record of settled design.
- 未決事項の状態・分類・優先度を GitHub 上で管理できる。
- Open questions can be tracked, labeled, and prioritized on GitHub.
- docs と Issue の二重管理を避けるため、決定時に Issue を確実にクローズする運用が必要。
- To avoid double bookkeeping, Issues must be reliably closed when decisions are recorded.
