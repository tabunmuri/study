# Git-Command
![Git](https://raw.githubusercontent.com/tabunmuri/study/master/images/git.png)

- `git difftool --extcmd icdiff`
	- 良い感じに差分を出す。
- `git diff HEAD^ HEAD`
	- 直前のcommitとその前の差分を出してくれる
- `git diff HEAD^ HEAD --stat`
	- 直前のcommitとその前の差分ファイルを出してくれる
- ブランチを消すコマンド
	- リモート
		- `git push origin :{branch}`
	- ローカル
		- `git branch -D {branch}`


- メインのアカウント(~/.gitconfig)
	- `git config --global user.name "メインアカウントのユーザ名"`
	- `git config --global user.email "メインアカウントのメールアドレス"`
- サブのアカウント(./.git/config)
	- `cd [ローカルリポジトリのディレクトリ]`
	- `git config user.name "サブアカウントのユーザ名"`
	- `git config user.email "サブアカウントのメールアドレス"`
- 新しいブランチを作成               -> `git branch`
- ブランチの切替                    -> `git co <name>`
- 新しいブランチを作成&チェックアウト  -> `git co -b <name>`
- 強引にリモートブランチに合わせる    -> `git fetch origin`
	- `git reset --hard origin/master`
- gitで、あるファイルだけ、以前のバージョンに戻す
	- 以前のバージョンの状態を確認  ->` git show HEAD^:path/to/file`
	- バージョンがわかったら、戻す  -> `git co HEAD^ path/to/file`