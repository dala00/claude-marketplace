# claude-marketplace

Claude Codeプラグインマーケットプレイス。

## ルール

- プロンプト関連のファイル（SKILL.md、CLAUDE.md など）は日本語で記述すること
- 設定ファイル（JSON）は英語で記述すること
- レスポンスは日本語で行うこと

## スキル構成

### security-check プラグイン

`security-check` を大本のスキルとし、プロジェクトの種類に応じてサブスキルに振り分ける構成。

```
security-check              ← 統合スキル（プロジェクト構成を判定し、該当するサブスキルを呼び出す）
├── security-check-web          ← Webフロントエンド（React, Vue, Angular, 静的サイトなど）
├── security-check-app          ← モバイル/デスクトップアプリ（Flutter, React Native, Electron など）
├── security-check-backend      ← バックエンド（APIサーバー, CLI, バッチ処理など）
├── security-check-client-db    ← クライアント側DB（Firebase, Supabase, Appwrite など）
└── security-check-compliance   ← 法務・コンプライアンス（電気通信事業届出, 特商法, 利用規約, 商標など）
```

- web / app / backend はプロジェクト構成に応じて該当するもののみ実行
- client-db はクライアント側DBの利用を検出した場合のみ実行
- compliance はプロジェクトの種類を問わず常に実行

#### 設計方針

- チェック項目が多くなったサブスキルは、さらに細分化する
  - 例: `security-check-backend-auth`（認証・認可）、`security-check-backend-api`（APIセキュリティ）など
- 各サブスキルは単独でも呼び出し可能
- 統合スキルはプロジェクト構成の自動判定→該当スキルの呼び出し→総合レポートの流れで動作する
