# Rails
## 基本
- 名前に困ったらここを見る
	- [Railsにおける命名規則](http://qiita.com/gakkie/items/3afcd505c786364aa5fa)

## rails Command(Rails5〜)

`rake`コマンドは、`rails`コマンドに統合されました。(rails5〜)

- `rails -T`
	- 使用可能なコマンド一覧
- `rails db:migrate:reset`

## rails g
- `rails g <Model / Controller / View> <単数形>`

#### `スネークケース`か`キャメルケース`か

`rails generate`コマンドには、キャメルケースでもスネークケースでもどちらでも良い

```
rails g controller sales_point
rails g controller SalesPoint
```

### 大まかな枠組み
- `rails g <Model / Controller / View>`
	- 他にも種類はあるが、詳細は`rails g --help`を見ると良い。
- `rails g model {単数形のresource名}`
	- コマンドの後ろに書くと、ある程度、カラムの設定はしてくれる
		- 例
		- `name:string`
		- `published_on:date`
		- `price:integer`
		- `number_of_page:integer`
		- `body:text`
		- `issue:references`
- `rails g controller {単数形のresource名} <index / show / new / edit create / update / destroy>`
	- index show new edit create update destroy
- `rails g view`


### オプション
- `--migration=false`
	- migration無しで作れる
- `--no-controller-specs`
	- Controllerのspecの作成をskipしてくれる
- `--no-view-specs`
 	- Viewのspecの作成をskipしてくれる
- `--p` 
	- `dryrun`。どんなファイルが生成されるのか確認ができる

## subコマンド
- `bundle exec erd --filetype=png`
	- pngでER図を出力
	- エイリアス `erd`
- `rails rubocop`
	- ロボコップによるコード品質のチェックが走る
- `./bin/rspec`
	- rspecによるテストが走る
- `rails routes`
	- routingのリストを出力。`peco`まで、パイプでつなぐと、捗る

