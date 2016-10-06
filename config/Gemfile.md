# Gemfile

一番ベーシックなやつを置いておきます。
ここのやつをコピってくればいいYO

```
# frozen_string_literal: true
source 'https://rubygems.org'
ruby_version = File.read(File.expand_path('../.ruby-version', __FILE__)).strip
ruby ruby_version

# Bundle edge Rails instead: gem 'rails', github: 'rails/rails'
gem 'rails', '>= 5.0.0.rc2'
# Use mysql as the database for Active Record
gem 'mysql2', '0.4.4'

# Use SCSS for stylesheets
gem 'sassc-rails'
# Use Uglifier as compressor for JavaScript assets
gem 'uglifier'
# Use CoffeeScript for .coffee assets and views
gem 'coffee-rails'
# See https://github.com/rails/execjs#readme for more supported runtimes
# gem 'therubyracer', platforms: :ruby

# Use jquery as the JavaScript library
gem 'jquery-rails'
# Turbolinks makes following links in your web application faster. Read more: https://github.com/rails/turbolinks
gem 'turbolinks'
# Build JSON APIs with ease. Read more: https://github.com/rails/jbuilder
gem 'jbuilder'
# bundle exec rake doc:rails generates the API under doc/api.
gem 'sdoc', '~> 0.4.0', group: :doc

# Use ActiveModel has_secure_password
# gem 'bcrypt', '~> 3.1.7'

# Use Capistrano for deployment
# gem 'capistrano-rails', group: :development

# slim
gem 'slim-rails'

# 環境変数周りを設定するgem
gem 'dotenv-rails'

group :production do
  # Use Unicorn as the app server
  gem 'unicorn'
  gem 'rails_12factor'
end

group :development do
  # https://rubygems.org/gems/pry
  gem 'pry', '~> 0.10.4'

  # Use Pry as your rails console
  # https://rubygems.org/gems/pry-rails
  gem 'pry-rails', '~> 0.3.4'

  # Access an IRB console on exception pages or by using <%= console %> in views
  gem 'web-console'

  # ログ出力整形
  gem 'awesome_print'

  # パラメータ、SQL整形
  gem 'rails-flog'

  # エラー画面拡張
  gem 'better_errors'
  gem 'binding_of_caller'

  # ER図を出力する
  gem 'rails-erd', '~> 1.5'
end

group :development, :test do
  # Spring speeds up development by keeping your application running in the background. Read more: https://github.com/rails/spring
  gem 'spring'

  # モデルの出力結果を表形式で表示する
  gem 'hirb'
  # hirbの日本語などマルチバイト文字の出力時の出力結果がすれる問題に対応
  gem 'hirb-unicode-steakknife'

  # テスト
  gem 'rspec-rails'
  gem 'factory_girl_rails'

  # capybaraでブラウザを開くときに必要な為
  gem 'launchy'

  # 静的解析
  gem 'rubocop', '~> 0.43.0'

  # ドキュメント生成用のgem
  gem 'yard', require: false

  # テストの並列実行
  gem 'parallel_tests'

  # 外部との通信を遮断する為のツール
  gem 'webmock'

  # テストごとにDBをリセット
  gem 'database_rewinder'
end

group :test do
  # カバレッジの測定
  gem 'simplecov', '0.12.0', require: false

  # Coveralls.io
  gem 'coveralls', require: false

  # エンドツーエンドテスト
  gem 'poltergeist'

  # junit形式のxmlを出力する
  gem 'rspec_junit_formatter', '0.2.3'
end
```