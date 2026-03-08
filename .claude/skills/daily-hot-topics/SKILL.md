# daily-hot-topics

前日にホットだった話題をarxiv.orgとreddit.comから収集し、マークダウンで保存してGitHubへpushするスキル。

## 使い方

`/topics` と入力して実行する。

## 実行手順

以下の手順を順番に実行してください。

### 1. 情報収集

**arxiv.org** と **reddit.com**, **https://huggingface.co/papers/trending**, **youtube.com**から前日（yesterdayの日付）にホットだった話題を収集する。
- 
- arxiv.org: 前日に投稿・注目された論文（cs, AI, physics などの人気カテゴリ）
- reddit.com: 前日にホットだったポスト（r/technology, r/science, r/programming など）
- https://huggingface.co/papers/trending: 画像関係の最新論文をまとめる
- youtube.com: AIに関連する動画

各サイトから上位20件を目安に収集する。

### 2. データ整理

各トピックについて以下を作成する：
- タイトル
- URL
- 1行でのまとめ（日本語）

### 3. マークダウンファイル生成

以下の形式でMDファイルを生成し、`/home/mattz/newspapers/ideas/` 直下に保存する。

ファイル名: `YYYY-MM-DD.md`（前日の日付）

```markdown
# YYYY-MM-DD ホットトピックまとめ

## arxiv.org

| タイトル | URL | まとめ |
|---------|-----|--------|
| タイトル1 | [リンク](URL) | 1行まとめ |
| タイトル2 | [リンク](URL) | 1行まとめ |

## reddit.com

| タイトル | URL | まとめ |
|---------|-----|--------|
| タイトル1 | [リンク](URL) | 1行まとめ |
| タイトル2 | [リンク](URL) | 1行まとめ |
```

### 4. Gitコミット

生成したMDファイルをコミットする。

```bash
cd /home/mattz/newspapers
git add YYYY-MM-DD.md
git commit -m "Add daily hot topics: YYYY-MM-DD"
```

### 5. GitHubへpush

```bash
git push
```

## 注意事項

- WebSearchまたはWebFetchツールを使って情報を取得する
- 前日の日付はシステムの現在日時から計算する
- pushに失敗した場合はエラー内容をユーザーに報告する
