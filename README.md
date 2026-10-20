# テーマ0：GitとGitHubの基本・演習
## 00. Gitのインストールと初期設定

### 1. Gitのバージョン確認

以下のコマンドを実行し、Gitがインストールされていることを確認した。

```bash
git --version
```

実行結果：

```text
git version 2.39.5 (Apple Git-154)
```

### 2. Gitの初期設定

以下のコマンドを使用して、ユーザー名、メールアドレス、デフォルトブランチ名を設定した。

```bash
git config --global user.name "chen"
git config --global user.email "236504822+chenbuf1@users.noreply.github.com"
git config --global init.defaultBranch main
```

メールアドレスには、プライバシー保護のため、GitHubが提供するnoreplyアドレスを使用した。

### 3. 設定内容の確認

以下のコマンドを実行した。

```bash
git config --global --list
```

実行結果：

```text
filter.lfs.clean=git-lfs clean -- %f
filter.lfs.smudge=git-lfs smudge -- %f
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
user.name=chen
user.email=236504822+chenbuf1@users.noreply.github.com
init.defaultbranch=main
```

以上より、Gitのインストールと初期設定が正常に完了したことを確認した。
