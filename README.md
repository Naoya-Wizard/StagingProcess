# Stagingサイトの作成手順

## エックスサーバーの管理画面にアクセス
[エックスサーバーの管理画面](https://secure.xserver.ne.jp/xapanel/login/xserver/server/)
にアクセスしてログインします。

## サブドメインの作成
ステージングサイト用のサブドメイン（例: staging.yourdomain.com）を作成します。

- ページの右上に「ドメイン」の項目がありますので、その中から「サブドメイン設定」をクリックします。  

- サブドメインを設定したいドメインの右側にある「選択する」リンクをクリックします。  

- 「サブドメイン設定追加」のタブをクリックします。  

  - サブドメイン名：希望するサブドメインを入力します。  
  - コメント：サブドメインの内容や目的などの覚書を入力します（未入力でもOK）。  
  - 無料独自SSL：セキュリティ強化のため、このオプションを有効にしておきます。  
  - 入力内容を確認し、問題がなければ「確認画面へ進む」ボタンをクリックします。  
  - 確認画面が表示されるので、再度内容を確認して「追加する」ボタンをクリックします。  

- 「サブドメイン設定の追加が完了しました」というメッセージが表示されれば、設定は完了です。  

- 設定が反映されるまで最大1時間ほど待ちます。「反映待ち」というステータスが消えたら、サブドメインの設定が完了しています。  

## データベースのコピー
本番環境のWordPressのデータベースをコピーして、新しいデータベースを作成します。

- サーバーパネル内の「データベース」の項目から「MySQLバックアップ」を選択します。

- 「現在のMySQLをダウンロード」をクリックします。次に、バックアップを行いたいデータベースの圧縮形式（圧縮しない/gz形式）を選択し、「ダウンロード実行」ボタンをクリックします。

- バックアップが自動的に開始され、ダウンロードが始まります。ダウンロードが完了したら、保存したファイルを確認してください。

- サーバーパネル内の「データベース」の項目から「MySQLデータベース追加」を選択し、新しいデータベースを作成します。

- phpMyAdminやエックスサーバーの管理画面を使用して、ダウンロードしたバックアップファイルを新しく作成したデータベースにインポートします。

## ファイルのコピー
本番環境のWordPressのファイルを、新しく作成したサブドメインのディレクトリにコピーします。

- FTPクライアント（例: FileZilla, Cyberduckなど）をインストールして起動します。

- FTPクライアントを使用して、エックスサーバーのFTP情報（ホスト名、ユーザー名、パスワード）を入力して接続します。この情報はエックスサーバーの管理画面や契約時に受け取ったメールに記載されています。

- FTPクライアントを使用して、本番環境のWordPressのファイルが保存されているディレクトリに移動します。

- 全てのファイルとディレクトリを選択し、ローカルのPCにダウンロードします。

- FTPクライアントで新しく作成したサブドメインのディレクトリに移動します。

- 先ほどダウンロードしたWordPressのファイルを選択し、サブドメインのディレクトリにアップロードします。

- 必要に応じて、ファイルやディレクトリのパーミッションを確認・変更します。特に.htaccessやwp-config.phpなどの重要なファイルのパーミッションを確認してください。

- ファイルのコピーが完了したら、新しいサブドメインのURLにアクセスして、サイトが正しく表示されるか確認します。
