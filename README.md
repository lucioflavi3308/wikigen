# wikigen

GitHub リポジトリのソースコードから自動で Wiki (Markdown) を生成する CLI ツール。

Claude Code (`claude -p`) がリポジトリを直接読んでドキュメントを生成します。

## アーキテクチャ

```
wikigen → git clone → claude -p --add-dir ./repo
                           │
                           ├── Read (ソースコード読み取り)
                           ├── Grep (パターン検索)
                           ├── Glob (ファイル探索)
                           └── Bash (git log 等)
```

Docker、Ollama、embedding 一切不要。

## 前提条件

- Go 1.22+
- git
- `claude` CLI がインストール・認証済み

## セットアップ

```bash
git clone https://github.com/tomohiro-owada/wikigen.git
cd wikigen
cp .env.example .env
# .env に GITHUB_TOKEN を記入
go build -o wikigen .
```

## 使い方

```bash
# 単一リポジトリ
./wikigen owner/repo

# 複数
./wikigen owner/repo1 owner/repo2

# ファイルから一括
./wikigen -f repos.txt

# 並列実行
./wikigen -f repos.txt -p 3

# モデル指定
./wikigen -f repos.txt -model haiku

# 英語で生成
./wikigen -f repos.txt -lang en

# ログをファイルに
./wikigen -f repos.txt -log batch.log
```

## 出力形式

GitHub Wiki 互換のディレクトリ構成で出力されます。`{repo}.wiki.git` にそのまま push 可能。

```
wiki-output/{repo}/
  Home.md           ← トップページ（目次）
  _Sidebar.md       ← ナビゲーション
  System-Architecture.md
  API-Specification.md
  Data-Model.md
  ...
```

### GitHub Wiki への push

```bash
git clone https://github.com/owner/repo.wiki.git
cp -r wiki-output/repo/* repo.wiki/
cd repo.wiki
git add -A && git commit -m "Update wiki" && git push
```

## オプション

| フラグ | デフォルト | 説明 |
|---|---|---|
| `-f` | - | リポジトリリストファイル |
| `-r` | - | カンマ区切りリポジトリ |
| `-token` | `$GITHUB_TOKEN` | GitHub PAT |
| `-model` | `$CLAUDE_MODEL` | Claude モデル (haiku, sonnet, opus) |
| `-o` | `./wiki-output` | 出力ディレクトリ |
| `-clone-dir` | `./.repos` | clone先ディレクトリ |
| `-p` | `1` | 並列数 |
| `-lang` | `ja` | 出力言語 |
| `-log` | stderr | ログファイルパス |

## ドキュメント生成方針

コードベースから以下のカテゴリのドキュメントを自動生成します：

### A. コードから確実に生成（事実ベース）
- システム概要、アーキテクチャ、API仕様、データモデル
- ルーティング、状態管理、コンポーネント一覧
- 設定・環境変数、ビルド・デプロイ、テスト構成
- 認証・認可、エラーハンドリング、外部連携

### B. コードパターンからの推論（高い確度）
- 処理フロー、セキュリティ設計、パフォーマンス考慮

コードに根拠がないものは生成しません。
