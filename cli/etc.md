■公開鍵／秘密鍵を作成
    ssh-keygen -t rsa

■centOS 7用のネットワーク設定
    詳細 -> http://fnya.cocolog-nifty.com/blog/2014/07/centos-7-virtua.html

■OSシャットダウン方法
    -> shutdown -h now

■OS再起動
    -> reboot
    -> shutrown -r now

■mysql.sock の場所を調べる
    -> mysql_config --socket


■cp [-abfilprsuv] <コピー元> <コピー先>
    <コピー元>  コピーするファイルまたはディレクトリを指定します。コピー先がディレクトリであれば、スペース区切りで複数列挙することができます。
    <コピー先>  コピー先のファイル名またはディレクトリを指定します。

    -a  元のファイルの属性とディレクトリ構成を可能な限り保持します。
    -b  上書きされるファイルのバックアップを作成します。
    -f  コピー先に同じ名前のファイルがあれば、確認なしで上書きします。
    -i  上書きされるファイルがあれば、その可否を確認します。
    -l  コピーのかわりにハード・リンクを作成します。ただしディレクトリは除外します。
    -p  元のファイルの属性(タイムスタンプ等)を可能な限り保持します。
    -r  ディレクトリを中身ごとコピーします。
    -s  コピーするかわりにシンボリック・リンクを作成します。
    -u  同名のファイルが存在する場合、コピー先のタイムスタンプが同じか新しいときはコピーしません。
    -v  経過を表示します。

■coffeeコマンド一覧
    -c, --compile       .coffee を .js にコンパイル
    -i, --interactive   REPLを起動。rlwrap と併せて使うと良い。
    -o, --output [DIR]  JavaScript出力ディレクトリ指定。
                        --compile や --watch と併せて使う（下の例を参照）。
    -j, --join          コンパイル前に、全てのスクリプトを渡された順番通りに結合する。大きなプロジェクトで使うと便利。
    -w, --watch         ソースが更新されたらすぐに再コンパイル
    -p, --print         ファイル出力の代わりに標準出力
    -l, --lint          JavaScriptをLintでチェック。jslコマンド（JavaScript Lint）が必要。
                        --watch と併せて使うと便利。
    -s, --stdio         標準入力からcoffeeスクリプトを読んで、標準出力にJavaScriptを渡す。
    -e, --eval          コマンドラインで書かれた短いコードを実行
                        例：coffee -e "puts num for num in [10..1]"
    -r, --requiure      コンパイルや実行の前にライブラリを読み込む
    -b, --bare          トップレベル関数safety wrapper無しでJavaScriptをコンパイル（？）。
                        (function() {〜〜})(); でくくらないということかな。
                        Node.jsモジュールとしてCoffeeScriptを使う場合に用いる。
    -t, --tokens        CoffeeScriptをパースする代わりに、Lexで字句解析してトークンを出力。
    --nodejs            nodeコマンドには --debug や --max-stack-size のような便利なオプションがある。このフラグを使って Node.js にオプションを渡す。
    -v, --version       バージョンを表示
    -h, --help          ヘルプ

■JavaScriptをforeverで起動する例
 - sudo forever start /home/pi/node-dht-sensor/sensor.js
 - sudo forever start /home/pi/webapp/app.js
■CoffeeScriptをforeverで起動する例
 - sudo forever start -c coffee /home/pi/node-dht-sensor/sensor.coffee
 - sudo forever start -c coffee /home/pi/webapp/app.coffee

■現在のディレクトリのファイル数をカウント
    - ls -F | grep -v / | wc -l
■ディレクトリの権限だけ変更
    通常時
        - find Model -type d -exec chmod 755 {} \;
    files以下の場合
        - find files -type f -exec chmod 777 {} \;

■yum 関連
    yum install ソフトウェア名                  : ソフトウェアをインストールします
    yum clean packages                          : 今までダウンロードしたパッケージを削除します（サーバーの容量を広げます）
    yum update ソフトウェア名                   : ソフトウェアをアップデートします
    yum remove ソフトウェア名                   : ソフトウェアをアンインストールします
    yum list installed                          : 既にインストールしたソフトウェアの一覧を表示します
    yum list installed | grep ソフトウェア名    : 指定したフトウェアのバージョン名を表示します。
    yum list                                    : インストール可能なソフトウェアの一覧を表示します
    yum list updates                            : インストールしたフトウェアでアップデートが必要（できる）一覧です。

    ※ リポジトリを変更する場合は、こんな感じ
        sudo yum --enablerepo=epel install java-1.7.0-openjdk.x86_64
        yum --enablerepo=remi-php55 install php-fpm

    ※オプション
        yumコマンドの直後に-ｙをつけると、全自動でyesになります。
        例（ntpサーバーをインストールする例）
            yum -y install ntp
■nginx
    設定ファイルの場所
        /etc/nginx/
    再起動
        sudo service nginx restart
    リロード
        sudo service nginx reload
    コンフィグテスト
        sudo service nginx configtest
    nginx起動時に求められるパスワードを自動化するには？
        cp cert.key cert.key.org
        openssl rsa -in cert.key.org -out cert.key

■mysql関連
    mysql.server start

■ファイル、ディレクトリ毎に権限を再帰的に変更するコマンド
 - sudo find files -type d -exec chmod 755 {} \; && sudo find files -type f -exec chmod 644 {} \;

■ファイルの権限だけ変更
 - find Model -type f -exec chmod 644 {} \;

■現在のディレクトリ以下のフィアルより、指定の文字列が存在しないか検索
    find ./ -name "*.*" -exec grep -l "検索対象文字列" {} \;

■ファイルのエンコードを変更する。
 - nkf -j euc_file > jis_file
    オプション 出力先文字コード
        -j      JIS （ISO-2022-JP）
        -e      EUC（Extended UNIX Code）
        -s      シフトJIS
        -w      UTF-8

■圧縮／解凍関係
tar.gzに圧縮したい -> tar cvzf <圧縮ファイル名>.tar.gz 対象ディレクトリ
tar.gzを解凍したい -> tar xvzf filename.tar.gz

■gitの操作
    メインのアカウント(~/.gitconfig)
        -> git config --global user.name "メインアカウントのユーザ名"
        -> git config --global user.email "メインアカウントのメールアドレス"

    サブのアカウント(./.git/config)
        -> cd [ローカルリポジトリのディレクトリ]
            git config user.name "サブアカウントのユーザ名"
            git config user.email "サブアカウントのメールアドレス"

    新しいブランチを作成               -> git branch
    ブランチの切替                    -> git co <name>
    新しいブランチを作成&チェックアウト  -> git co -b <name>
    ブランチを削除                    -> git branch -D <name>
    リモートブランチを削除             -> git push origin :<name>
    強引にリモートブランチに合わせる    -> git fetch origin
                                            git reset --hard origin/master
    gitで、あるファイルだけ、以前のバージョンに戻す
        以前のバージョンの状態を確認  -> git show HEAD^:path/to/file
        バージョンがわかったら、戻す  -> git co HEAD^ path/to/file

■compassの操作
    -> compass watch <.rubyのあるディレクトリ>

■sftpの操作
    ディレクトリ状態を確認
        - リモートホスト -> ls
        - ローカルホスト -> lls

    一つのファイルを転送したい
        - リモートホスト -> ローカルホスト
        get ファイル名

        - ローカルホスト -> リモートホスト
        put ファイル名

    複数のファイルを転送したい
        - リモートホスト -> ローカルホスト
            mget 複数ファイルをスペース区切りで指定
            (※mgetコマンドは、メタキャラクタ ([*]) を利用できるので， `*.tex' や `kadai?.tex' など のようにファイル名を指定することで 複数のファイルを同時に転送できます．)

        - ローカルホスト -> リモートホスト
            mput 複数ファイルをスペース区切りで指定
            (※mputコマンドは、`*.tex' や `kadai?.tex' など のようにファイル名を指定することで 複数のファイルを同時に転送できます．)

    sftpコマンドの終了
        - exit

■ntp関連
    ntpを停止
        -> /etc/init.d/ntpd stop
    時刻同期
        -> ntpdate clock.nc.fukuoka-u.ac.jp
    時刻合わせ
        -> ntpq -p

Ansibleまとめ
    ■Ansible Tutorial
    http://yteraoka.github.io/ansible-tutorial/

    ■応用例
    応用例 1: ファイルをリモートにコピーする
        ansible webservers -m copy -a "src=/tmp/spam dest=/tmp/ham"
    応用例 2: ディレクトリ作成
        ansible webservers -m file -a "dest=/path/to/c mode=644 owner=mdehaan group=mdehaan state=directory"
    応用例 3: パッケージインストール
        ansible webservers -m yum -a "name=dstat state=installed"
    応用例 4: gitからデプロイ
        ansible webservers -m git -a "repo=git://foo.example.org/repo.git dest=/srv/myapp version=HEAD"
    応用例 5: サービス
        ansible webservers -m service -a "name=httpd state=started"
     (http://tdoc.info/blog/2014/01/22/ansible_adhoc_commands.html)

    ■playbookまとめ
    （http://qiita.com/moriteru@github/items/45d69a5744d658ce5c6e）



■mongoDBの話
    ログイン時に起動しておきたい場合
        ln -sfv /usr/local/opt/mongodb/*.plist ~/Library/LaunchAgents

    mongodb 起動
        launchctl load ~/Library/LaunchAgents/homebrew.mxcl.mongodb.plist

    launchctlを使わずに 起動
        mongod --config /usr/local/etc/mongod.conf

    起動確認用接続
        mongo
