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
### 登録手順
```bash
1. ターミナルで以下のコマンドを実行し、公開鍵をクリップボードにコピーする。
   `pbcopy < ~/.ssh/id_ed25519.pub`
2. GitHubにログインし、「Settings」→「SSH and GPG keys」を開く。
3. 「New SSH key」をクリックし、タイトルと公開鍵を入力する。
4. 「Add SSH key」をクリックして、公開鍵を登録する。
5. ターミナルで以下のコマンドを実行し、SSH認証が成功することを確認する。
   `ssh -T git@github.com`
```
### スクリーンショット
<img width="700" height="150" alt="d700c828-c648-4b7d-a58a-d39e4720b4e3" src="https://github.com/user-attachments/assets/3288f7c0-2fc5-4104-aca5-21d9425f379e" />

### ssh -T git@github.com で認証確認した結果
```text
Hi chenbuf1! You've successfully authenticated, but GitHub does not provide shell access.
```




## 03. ローカルリポジトリとGitHubリポジトリの連携
### 実行したコマンド
```bash
git remote add origin git@github.com:chenbuf1/100knock_2.git
```
### git remote -v で認証確認した結果
```text
origin	git@github.com:100knock_2/git-practice.git (fetch)
origin	git@github.com:100knock_2/git-practice.git (push)
```




## 04. ファイルの変更とpush/pull
ローカルでREADME.mdを編集しました。
### 実行したコマンド
```bash
git fetch origin
git log --oneline -5
git log --oneline origin/main -5
```
### 確認した結果
<img width="400" height="142" alt="0b0ef75b-d548-4d58-8b06-2a6b1ab7fa45" src="https://github.com/user-attachments/assets/31b9533f-932f-41cf-8361-94e6ad90610a" />




## 05. .gitignoreファイルの作成
### 実行したコマンド
```bash
cat > .gitignore <<'EOF'
node_modules/
.env
.DS_Store
EOF
```

| ファイル | 無視する理由 |
|---|---|
| `node_modules/` | 依存ライブラリは再インストールできるため。 |
| `.env` | APIキーやパスワードなどの機密情報を含む可能性があるため。 |
| `.DS_Store` | macOSが自動生成する不要な管理ファイルのため。 |

### 確認した結果
<img width="365" height="146" alt="bf14b580-b310-4424-8127-e12e9c7e0525" src="https://github.com/user-attachments/assets/e9d237fb-1fb6-4bfe-a4f7-bfdf42df0e51" />
<br>
<img width="365" height="44" alt="e587fa9b-3502-445d-afc7-733d94f71891" src="https://github.com/user-attachments/assets/f81b2378-0c61-4c0d-b73f-a425fb9d9aec" />


## 06. ブランチの作成と切り替え
<img width="500" height="300" alt="e1e99da7-8d3d-4463-b88d-902f4c72694b" src="https://github.com/user-attachments/assets/8528e37c-362e-4242-9489-ff68e037e504" />

