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




## 01. リポジトリの初期化と最初のコミット
### 実行したコマンド
```bash
cd ~/Desktop
mkdir git-practice
cd git-practice
git init
touch README.md
echo "# Git Practice" > README.md
cat README.md
git add README.md
git commit -m "Initial commit"
git rev-parse HEAD
```
### 初回コミットID
`2022ad73356d6e14dc8c26f9b4c3dfe9d7c25318` （git rev-parse HEAD）
### 実行結果
<img width="700" height="126" alt="9a000a7f-7bbc-4fc7-b8e8-5570e07e5a60" src="https://github.com/user-attachments/assets/f196e652-2b1f-434a-8ad7-3715130405b6" />

## 02. GitHubアカウントの作成，2段階認証とSSHキー登録
### GitHubの「Settings → SSH and GPG keys」に鍵が登録された画面のスクリーンショット
<img width="700" height="150" alt="d700c828-c648-4b7d-a58a-d39e4720b4e3" src="https://github.com/user-attachments/assets/3288f7c0-2fc5-4104-aca5-21d9425f379e" />
### ssh -T git@github.com で認証確認した結果
```bash
Hi chenbuf1! You've successfully authenticated, but GitHub does not provide shell access.
```
