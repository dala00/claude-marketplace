---
description: プロジェクト全体のセキュリティチェックを実行する
---

このプロジェクトのセキュリティ監査を実施してください。以下の手順で進めること：

## 1. プロジェクト構成の判定

まずプロジェクトのファイル構成を確認し、以下の**すべての項目について**該当するかどうかを判定する。複数に該当することが一般的であり、該当するものはすべてチェック対象とする：

- **Webフロントエンド**: React、Vue、Angular、Svelte、静的HTML/JS など
- **モバイル/デスクトップアプリ**: Flutter、React Native、Swift、Kotlin、Electron など
- **バックエンド**: APIサーバー、CLIツール、バッチ処理 など
- **クライアント側DB**: Firebase、Supabase、Appwrite、AWS Amplify など

各項目について該当・非該当の判定と、その根拠（使用フレームワーク、ディレクトリ構成など）を簡潔に報告すること。

## 2. 該当するセキュリティチェックをすべて実行

判定結果に基づき、該当する**すべての**スキルを実行する：

- Webフロントエンドに該当 → `/security-check:security-check-web` を実行
- モバイル/デスクトップアプリに該当 → `/security-check:security-check-app` を実行
- バックエンドに該当 → `/security-check:security-check-backend` を実行
- クライアント側DBに該当 → `/security-check:security-check-client-db` を実行

また、プロジェクトの種類を問わず以下を常に実行する：

- `/security-check:security-check-compliance`（法務・コンプライアンスチェック）

## 3. 総合レポート

すべてのチェック完了後、以下を含む総合レポートをまとめる：

- 検出された問題の一覧（重大度順）
- 優先的に対応すべき項目のハイライト
- プロジェクト全体のセキュリティ評価（A〜Eの5段階）

## 4. レポートの保存

総合レポートの表示後、Markdownファイルとして保存するかどうかをユーザーに確認する。保存を希望した場合、レポートを `.md` ファイルとしてプロジェクト内に保存する。

$ARGUMENTS
