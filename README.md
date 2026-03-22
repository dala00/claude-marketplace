# claude-marketplace

Claude Code プラグインマーケットプレイス。

## セットアップ

### 1. マーケットプレイスの追加

```
/plugin marketplace add dala00/claude-marketplace
```

### 2. プラグインのインストール

```
/plugin install security-check@daladala-marketplace
```

## プラグイン一覧

### security-check

個人開発プロダクトのセキュリティチェッカー。プロジェクトの構成を自動判定し、該当するチェックをすべて実行します。

```
/security-check:security-check
```

#### サブスキル

| スキル                      | 対象                        | 主なチェック項目                                                        |
| --------------------------- | --------------------------- | ----------------------------------------------------------------------- |
| `security-check-web`        | Webフロントエンド           | XSS, CSP, CORS, ビルド時の環境変数漏洩, SRI など                        |
| `security-check-app`        | モバイル/デスクトップアプリ | 証明書ピンニング, ローカルDB暗号化, IPC, 権限管理 など                  |
| `security-check-backend`    | バックエンド                | SQLインジェクション, 認証, APIセキュリティ, レスポンスの情報漏洩 など   |
| `security-check-client-db`  | クライアント側DB            | セキュリティルール, 認証の強制, Admin SDK の分離, ストレージルール など |
| `security-check-compliance` | 法務・コンプライアンス      | 電気通信事業届出, 特商法, 利用規約, クレジット表記, 商標 など           |

統合スキル (`security-check`) はプロジェクト構成に応じて該当するサブスキルをすべて実行し、compliance は常に実行します。各サブスキルは単独でも呼び出し可能です。

## ライセンス

MIT

## Contribution

不足や修正項目などあればガンガンissueを立てたりPR投げたりしてください。
