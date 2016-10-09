# rails-dash

とりあえず、急いでrailsプロジェクトを走らせないといけない時に、やる最低限の設定

## 環境を決める

- プランA
	- 本番環境
	- アルファ環境
	- 開発環境
- プランB
	- 本番環境
	- アルファ環境
	- ベータ環境
	- 開発環境

## heroku? or aws?

どんな環境が求められているのでしょうか。

## DBの設計を行う
erdとか使って作っていくと良いかも。

## gemfile
### Gemfileのひながた
[config/Gemfile.md](https://github.com/tabunmuri/study/blob/master/config/Gemfile.md)

### 必要に応じて入れるやつ
#### ■device

```
# device
gem 'devise'
```
- [rubygems.org](https://rubygems.org/gems/devise)
- [github](https://github.com/plataformatec/devise)
- [Devise+OmniAuthでQiita風の複数プロバイダ認証](http://qiita.com/mnishiguchi/items/e15bbef61287f84b546e)

#### ■twitter bootstrap
```
# twitter bootstrap
gem 'bootstrap-sass'
```
- [rubygems.org](https://rubygems.org/gems/bootstrap-sass)
- [github](https://github.com/twbs/bootstrap-sass)
- [Rails bootstrapの導入 sassのススメ](http://qiita.com/shizuma/items/83cdadbe0a629f1f74d1)

### ■font-awesome-sass
```
# アイコンを増やす
gem 'font-awesome-sass', '~> 4.6', '>= 4.6.2'
```
- [rubygems.org](https://rubygems.org/gems/font-awesome-sass)
- [github](https://github.com/FortAwesome/font-awesome-sass)
- [bootstrap-sassとfont-awesome-sassをrails4に導入する](http://qiita.com/wantata222/items/8fe547ae9fb9616492ef)

### ■pre-commitを入れたら
```
# commit前に自動的にチェックが走る
gem 'pre-commit', '~> 0.30.0'
```
- [rubygems.org](https://rubygems.org/gems/pre-commit)
- [github](https://github.com/jish/pre-commit)

`rspec`と`rubocop`を有効にする。

```
git config pre-commit.checks "rspec"
git config pre-commit.checks "rubocop"
```

これで、commit前に、自動でチェックされるようになる。

## ci系

準備中

## テスト設定

準備中

## rubocop

準備中

## Capistrano

- [入門 Capistrano 3 ~ 全ての手作業を生まれる前に消し去りたい](http://labs.gree.jp/blog/2013/12/10084/)
- [github](https://github.com/capistrano/capistrano)

## Nginxの設定

準備中

## Unicornの設定

[Unicorn の起動と停止](http://qiita.com/py0n/items/1ced5574d57853f004d9)
