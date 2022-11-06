# http-server-node

- 手元でテスト用に実行するhttpまたはhttpsサーバー
- 待受プロトコルはhttpかhttpsのどちらかを指定できます。
- httpsを使うときのサーバー証明書と秘密鍵のフォルダを指定できます。
- 待受ポート番号を指定できます。デフォルトは 8080 です
- 待受IPアドレスを指定できます。
- (未実装) リダイレクト用ホスト名を指定できます。
- ファイルを配置したフォルダー(folder, directory)を指定して、その中のファイルの内容を応答します
- ファイルの大きさが2048バイトを超えていると、1024バイト単位で分割して応答します (Transfer-Encoding: chunked)
- ファイルの大きさが2048バイト以下のときは一括して応答します (Content-length: ... )
- 実行後、リクエストが1時間ないと終了します

```
localServer.js
```

```
ln -s /etc/letsencrypt/live/my.domain.example.com ~/.myCerts

mkdir temporalServFolder
echo "<h1>Hello world</h1>" > temporalServFolder/index.html

localServer.js temporalServFolder
```
