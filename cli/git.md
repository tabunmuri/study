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
