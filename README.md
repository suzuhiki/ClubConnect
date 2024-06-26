
## SAPPORO
PBLの授業で開発を行ったリポジトリ

最終プレゼンのスライド:https://speakerdeck.com/suzuhiki/clubconnet-shou-ye-zui-zhong-purezen

チームメンバー6名でSuzuhikiがバックエンドとデザインを担当してリーダーを務めた


### 作業ブランチ
外製部は```External```ブランチ、内製部は```Internal```ブランチにて作業を行う

```master```ブランチはmdファイルのみを配置しクリーンに保つ

上記3つのブランチはマージのみ受け入れる

### ブランチ命名規則
``` {ブランチ作成者名}/{issue番号}_{作業内容} ```

## リリース文
### 概要
サークル/部活向けメンバー管理アプリ「ClubConnect」のv1.0.0版です。

本アプリは、コロナウイルス感染が収まらないなかで、体温報告管理などの負担を強いられているサークル/部活の運営メンバーに向けて開発しました。
体温報告が行える機能のほかに、メンバーの個人情報をメンバー自身が登録し、それを運営メンバーが確認できる機能などを実装しています。

### アプリの設置方法
本アプリはPHP、HTML、CSS、SQLite3を利用して記述されており、表示のためにはApacheなどのWebサーバーソフトウェアが必要です。
また、環境によっては`php.ini`からPHPのSQLite拡張機能を有効化する必要があります。

### ファイルの配置

1. 本リリースのzipファイルを解凍し、Webサーバーがアクセスするディレクトリに配置してください。
1. phpファイルが配置されているディレクトリに`database`ディレクトリを作成してください。このディレクトリにデータベースファイルが生成されます。
1. Linux環境では`database`ディレクトリに対して777の権限を与えてください(`chmod 777 database`)。

### 使い方
- `index.php`にWebブラウザからアクセスするとログイン画面が表示されます。`index.php`と`CreateTeam.php`以外のページに直接アクセスすることはできません。
- 新規チーム作成ページから、チーム名とチームパスワード、管理者メールアドレスと管理者パスワードを登録してチームを作成してください。
- チーム名とチームパスワードはサークル/部活のメンバーに共有してください。管理者メールアドレスと管理者パスワードは管理者権限が必要な操作で使用しますので、共有せずに管理してください。
- ログイン時はチーム名とチームパスワードが必要です。
- ログインすると以下のような画面が表示されます。一般メンバーはイベントの一覧の閲覧と、イベント詳細情報と参加申請へのアクセス、メンバー情報の登録を行うことができます。
- 上の管理者ログインのボタンより、管理者ログインのページに移動すると、チーム作成時に登録した管理者メールアドレスと管理者パスワードを利用して管理者ログインすることができます。
- 管理者ログインをすると一般メンバーには表示されないボタンが表示されます。利用できる機能は、イベントの作成、部員名簿の閲覧、イベント参加者の抽選、イベントの削除です。
- イベント参加申請には自由記述欄を設けています。体温報告などにご利用ください。

### データの削除について
データは`database`ディレクトリに保存されます。`チーム名.db`を削除するとそのチームのデータが、`login.db`を削除するとすべてのチームのチーム名とチームパスワード、
管理者メールアドレスと管理者パスワードのデータが破棄されます。
