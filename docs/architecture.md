# アーキテクチャ / Architecture

システム全体のアーキテクチャを **決定事項ベース** でまとめる文書です。現時点では
ほとんどが未確定のため、各節は確定した内容の受け皿として用意しています。未確定の
論点は [GitHub Issues](https://github.com/h-ikeda/building-designer/issues) で追跡します。

This document captures the system architecture on a **decisions-only** basis. Most items are
still undecided, so each section is a placeholder to be filled in as decisions are made. Open
questions are tracked in [GitHub Issues](https://github.com/h-ikeda/building-designer/issues).

---

## プラットフォーム / Platform

Web アプリケーションかローカルアプリケーションか。この選択は設計フロー全体
（配布、オフライン計算、データ保管、3D 描画性能など）に影響します。

Web application vs. local application. This choice affects the entire design flow
(distribution, offline computation, data storage, 3D rendering performance, etc.).

- **状態 / Status:** 未確定 / Undecided — 関連 Issue を参照 / see related Issue.

---

## モジュール分割 / Module Decomposition

各機能領域（3D モデリング、法適合性照合、消費エネルギー計算、構造計算）の分割方針と
相互関係。

How the feature areas (3D modeling, legal compliance, energy calculation, structural
calculation) are decomposed and how they relate to each other.

- **状態 / Status:** 未確定 / Undecided — 関連 Issue を参照 / see related Issue.

---

## 共有ドメインモデル / Shared Domain Model

建物・空間・部材などをどのように表現し、各機能で共有するか。

How buildings, spaces, and components are represented and shared across features.

- **状態 / Status:** 未確定 / Undecided — 関連 Issue を参照 / see related Issue.

---

## 外部データの扱い / External Data

法令データ、気象データ、材料データなどの取得・保持・更新方法。

How external data (regulations, climate, materials, etc.) is obtained, stored, and updated.

- **状態 / Status:** 未確定 / Undecided — 関連 Issue を参照 / see related Issue.
