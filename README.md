# How-to-access-dev-missions

世界を救えに存在する開発者ミッションにアクセスする方法を数ヶ月の間研究し、再現することが出来たのでここに記録します。

※これによって損害が発生した場合私は一切の責任を負いません。


### 1.必要な物を用意する。

##### [VisualStudio2022](https://visualstudio.microsoft.com/ja/vs/)

##### [Xenos](https://github.com/DarthTon/Xenos/releases/tag/2.3.2)

##### [Fiddler](https://www.telerik.com/download/fiddler)

##### [MissionEditor](https://github.com/LemonCCjp/Savetheworld-MissionEditor)

#### 以上を全てダウンロード・インストールしてください。

##### (XenosとCobaltはウイルス対策ソフトに削除される可能性があります。オフにするか許可をしてください。)

##### VisualStudio2022のセットアップを進めると、インストールの選択画面が出てくるのでC言語(C, C++, C# など)関連を全て選択してインストールしてください。(かなり時間がかかります)

##### 全てのインストールが完了したら、リポジトリのクローンを選択して`https://github.com/Milxnor/Cobalt.git`を貼り付けてクローンしてください。

##### クローンが完了したらCobalt.slnを開きソリューションエクスプローラーのCobaltの上で右クリックしプロパティを開いてください。構成プロパティ内の`C/C++`を開くと`プリコンパイル済みヘッダー`という項目があるので、`プリコンパイル済みヘッダーを使用しない`に設定して適用してください。

##### 次にCobalt内の`settings.h`を開いて`ECobaltUsage::Private;`を`ECobaltUsage::Hybrid;`に書き換えて保存し、`Ctrl + B`を押してビルドしてください。成功すればクローンしたファイルの中の`x64`の中の`Debug`というファイルの中に`Cobalt.dll`が作成されていると思います。


### 2.Missionファイルを取得する。

##### ダウンロードした`ｍission_editor.zip`を解凍して中の`MissionEditor.exe`を開きます。

##### `最新のミッションファイルを取得しますか?`と表示されるのではいを選択。ブラウザでEPICGamesアカウントにログインしている状態で表示されているリンクにアクセスすると認証コードを取得できるので貼り付けてください。

![imgur](https://github.com/LemonCCjp/How-to-access-dev-missions/blob/main/img/auth.png?raw=true)

##### 同じ階層に`mission.json`が作成されたと思います。

##### 1を入力すると全てのミッションのアクセス制限が解除されます。他に編集したいものがあれば行ってください。詳細は最後の方に書いてあります。

##### 完了したらMissionEditorを閉じてください。


### 3.Fiddlerの設定をする。

##### Fiddlerを開き、まず`Tools`の中の`Opotions`を開きます。`HTTPS`に移動し`Capture HTTPS Conets`と`Decrypt HTTPS traffic`と`Check for certificate revocation`にチェックを入れます。

##### 右上の方にある`Actions`を開き`Trust Root Certificate`をクリック。全てYesを押してOKを押してください。

##### Opotionsを閉じ、右上の方にある`FiddlerScript`をクリックしスクリプトを全て削除してSaveしてください。

##### 次に`AutoResponder`をクリックし、`Enable Rules`と`Unmatched requests passthrough`にチェックを入れてください。

##### `Add Rule`を押し上のBOXに`https://fngw-mcp-gc-livefn.ol.epicgames.com/fortnite/api/game/v2/world/info`を貼り付け。下のBOXは右側のドロップダウンを開き一番下の`Find a file`を選択し先程作成したMissionEditorファイル内にある`mission.json`を選択してSaveを押してください。


### 4.Fortniteを起動する。

##### Fortniteを起動する前にXenosを準備しておきます。

##### `Xenos.exe`または`Xenos64.exe`のいずれかを開き`add`を押して先程作成した`Cobalt.dll`を選択してください。

##### EPICGamesLauncherからFortniteを起動し、ロードが始まったら急いでProcessで`FortniteClient-Win64-Shipping_BE.exe`, `FortniteClient-Win64-Shipping_EAC`, `FortniteClient-Win64-Shipping_EAC_EOS`のいずれかがあるので選択して`Inject`を押してください。(`FortniteLauncher`は選択しないでください。)

##### この時エラーが発生した場合はFortniteを起動からやり直してください。環境等の小さな変化でエラーが発生する場合もあります。何度も発生する場合はFortniteのアップデート等を待ってください。現環境では動作しないがアップデートすると動作する場合などがあります。

#### 開発者ミッションが開放されていれば成功です。

![画像](https://pbs.twimg.com/media/GF-CeBna0AAn1yA?format=jpg&name=large "変更後の表示")


## MissionEditorの機能

#### 基本的には[ここ](https://github.com/LemonCCjp/Savetheworld-MissionEditor)に書いてありますが軽く紹介します。

##### 1.アクセス制限の解除 - 全てのミッションのアクセス制限を解除します。

##### 2.アラート交換 - 現在交換したミッションに参加できません。

##### 3.theater表記の変更 - "トワインピークス"等のtheaterの表記名と詳細を変更できます。

##### 4.最新ファイルの取得 - 最新のミッションファイルを取得します。

##### 5.再読み込み - 手動でファイルを用意した際などに再読み込みできます。

##### 6.ミッション検索 - PL・tileIndexなどからミッションを絞り込み、jsonファイルに保存します。

##### 7.ミッションの上書き - ミッション検索で保存したミッションを上書きします。報酬の数など細かく変更できます。

##### 8.アラート削除 - ミッションアラートを全て削除します。これにより昨日のミッションアラートを受け取ることが可能になります。
