# アプリケーションのインストール

デモアプリ実行環境を用意していく。

この辺はAnsibleとかで雑に管理したいな

## nginxのインストール

```
sudo yum -y install nginx
```

インストール後、nginxの起動

```
sudo service nginx start
```

起動後、EIPにアクセスしてみてブラウザで表示できていればWebサーバの用意は完了、ポートも開いていることがわかる。

## MySQLのインストール

```
sudo yum -y install mysql-server
```

インストール後、mysqlの起動

```
sudo service mysqld start
```

## Webアプリケーション(Rails)の配置

この辺はまぁ今回はそのまま写経でさくっと入れる。

```
sudo yum -y groupinstall 'Development Tools'
sudo yum -y install ruby-devel mysql-devel
sudo yum -y --enablerepo=epel install nodejs
gem install rails io-console --no-rdoc --no-ri
rails -v
rails new aws-training --database=mysql --skip-git --skip-javascript --skip-spring --skip-test-unit
cd aws-training
rake db:create
rake db:migrate
rails server -b 0.0.0.0
```

ここまでで`<EIP>:3000`にアクセスすればとりあえずRailsのインストールを確認できる。

```
echo "gem 'io-console'" >> Gemfile
bundle install
rails generate scaffold book name:string price:decimal
rake db:migrate
rails server -b 0.0.0.0
```

ここまでやったらCRUD機能を持ったアプリが立ち上がるはず。`<EIP>:3000/books` にアクセスしてCRUDを試してみて、問題なさそうならOK。
