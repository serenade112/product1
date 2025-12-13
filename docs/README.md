# ドキュメント構成ガイド

このフォルダはプロダクト開発に必要なドキュメント一式を管理します。

## 📋 フォルダ構成概要

```
docs/
├── README.md                    # このファイル
├── glossary.md                  # 用語集
│
├── requirements/                # 要件定義
│   ├── prd.md                  # プロダクト要求・PRD
│   └── user-stories.md         # ユーザーストーリー一覧
│
├── design/                      # 設計・アーキテクチャ
│   ├── architecture.md         # システム全体像・技術スタック
│   ├── features-ui.md          # 機能設計・UI/UX
│   ├── api.md                  # API 設計・エンドポイント概要
│   ├── data.md                 # データベース設計・スキーマ
│   └── operations.md           # 運用・オペレーション方針
│
├── process/                     # プロセス・スクラム運用
│   ├── sprints/
│   │   ├── README.md           # スプリント運用ガイド
│   │   ├── sprint-YYYYWW-template.md  # スプリント計画テンプレ
│   │   └── sprint-YYYYWW.md    # 各スプリントのノート（例）
│   │
│   └── decisions/
│       ├── decision-log.md     # 重要決定のログ
│       └── adr/
│           └── adr-0001-template.md  # Architecture Decision Record テンプレ
│
├── templates/                   # 再利用可能なテンプレ集
│   ├── sprint-note-template.md # スプリントノート雛形
│   ├── adr-template.md         # ADR 雛形
│   └── user-story-template.md  # ユーザーストーリー雛形
│
├── changes/                     # 変更履歴・リリースノート
│   └── changelog.md            # 簡易変更履歴（Keep a Changelog 風）
│
└── assets/                      # 図・画像
    └── （各種ダイアグラムやワイヤーフレーム）
```

## 📖 各ファイルの役割

### 要件（requirements/）
プロダクトの目的・ユーザー・機能要件を定義します。

| ファイル | 説明 | 記載内容 |
| --- | --- | --- |
| **prd.md** | プロダクト要求 | 概要、スコープ、成功指標、非機能要件、リスク対応 |
| **user-stories.md** | ユーザーストーリー一覧 | ストーリー概要と GitHub Issue リンク |

### 設計（design/）
システムアーキテクチャから運用方針まで、実装に必要な技術設計をまとめます。詳細は必要に応じて追加・拡充します。

| ファイル | 説明 | 記載内容 |
| --- | --- | --- |
| **architecture.md** | システム全体像 | コンポーネント構成、技術スタック、非機能対応 |
| **features-ui.md** | 機能設計・UI/UX | 機能概要、ユースケース、受け入れ条件、画面設計、ガイドライン |
| **api.md** | API 設計 | エンドポイント一覧、規約、セキュリティ |
| **data.md** | データベース設計 | スキーマ、マイグレーション、ライフサイクル |
| **operations.md** | 運用設計 | 監視、アラート、環境、障害対応 |

### プロセス（process/）
スクラム運用と意思決定を記録・管理します。

#### process/sprints/
| ファイル | 説明 |
| --- | --- |
| **README.md** | スプリント運用ガイド（セレモニー・アーティファクト） |
| **sprint-YYYYWW-template.md** | スプリント計画テンプレ（コピーして使用） |
| **sprint-YYYYWW.md** | 実績スプリントノート（ゴール、レビュー、振り返り）例：sprint-202501.md |

#### process/decisions/
| ファイル | 説明 |
| --- | --- |
| **decision-log.md** | 重要な技術判断の一覧（決定日・タイトル・ADR リンク） |
| **adr/adr-0001-template.md** | Architecture Decision Record（ADR）テンプレ |

### テンプレ集（templates/）
繰り返し使う文書の雛形を管理します。

| ファイル | 説明 |
| --- | --- |
| **sprint-note-template.md** | スプリントノート雛形（計画・レビュー・振り返り）|
| **adr-template.md** | ADR 雛形（背景・決定・影響・代替案） |
| **user-story-template.md** | ユーザーストーリー雛形（As/I want/So that） |

### 変更履歴（changes/）
| ファイル | 説明 |
| --- | --- |
| **changelog.md** | ユーザー向け変更履歴（Keep a Changelog 形式） |

### 用語集・資産
| ファイル | 説明 |
| --- | --- |
| **glossary.md** | プロダクト・チーム内で使う用語の定義 |
| **assets/** | 図（ER図、システム図）、ワイヤーフレーム等の画像 |

## 📝 更新のコツ

### 最小限で効率的に
- **プロダクト正本**: GitHub Projects（Issue・Board）
- **docs の役割**: ゴール、ルール、意思決定、学び の要約
- 詳細・タスク・状態は Projects を参照させる

### 修正を容易に
- 各ページの冒頭に「最終更新日」を記載（手動更新でOK）
- 全体的に箇条書きより テーブルと短文で簡潔に
- 大型ドキュメントより小さな更新を積み重ねる方針

### リンクの統一
- GitHub Issue は `#123` 形式で参照
- 内部リンク（同フォルダ）は相対パスで簡潔に
- 図は `assets/` に配置し相対リンク `![alt](../assets/file.png)` で参照

## 🔄 スクラム運用との連携

1. **計画フェーズ**
   - `process/sprints/sprint-YYYYWW-template.md` をコピーして新規スプリント作成
   - 対象 PBI を GitHub Projects から選定し、Issue # を列挙

2. **実行フェーズ**
   - Daily Scrum は Projects のコメントで報告
   - ブロッカーや決定事項はスプリントノートに簡潔に記録

3. **振り返りフェーズ**
   - Sprint Review / Retro の結果をスプリントノートに記載
   - 重要な学びや決定は Decision Log / ADR へ

4. **継続的な改善**
   - 設計やプロセスに変更がある場合は対応ドキュメントを更新
   - 新しい判断は ADR として `process/decisions/adr/adr-NNNN-title.md` に記録

## 📌 よくある質問

**Q: スプリントノートのファイル名は？**  
A: `sprint-YYYYWW.md` （YYYY=年、WW=週番号。例：`sprint-202501.md`）

**Q: バックログや進捗を docs に記載する？**  
A: 不要です。GitHub Projects が正本です。docs は要約とリンクのみ。

**Q: テンプレをカスタマイズできる？**  
A: はい。必要に応じて調整し、プロジェクト特有の形式に変更できます。

**Q: 図や画像はどこに置く？**  
A: `docs/assets/` に格納し、マークダウンから相対リンクで参照。

---

**最終更新**: 2025-12-14  
**バージョン**: v0.1
