# How-to-access-dev-missions

世界を救えに存在する開発者ミッションにアクセスする方法を数ヶ月の間研究し、再現することが出来たのでここに記録します。

### 1.必要な物を用意する。

##### [VisualStudio2022](https://visualstudio.microsoft.com/ja/vs/)

##### [Xenos](https://github.com/DarthTon/Xenos/releases/tag/2.3.2)

##### [Fiddler](https://www.telerik.com/download/fiddler)

##### [MissionEditor](https://github.com/LemonCCjp/Savetheworld-MissionEditor)

#### 以上の物を全てダウンロード・インストールしてください。

##### (XenosとCobaltはウイルス対策ソフトに削除される可能性があります。オフにするか許可をしてください。)

##### VisualStudio2022のセットアップを進めると、インストールの選択画面が出てくるのでC言語(C, C++, C# など)関連を全て選択してインストールしてください。(かなり時間がかかります)

##### 全てのインストールが完了したら、リポジトリのクローンを選択して`https://github.com/Milxnor/Cobalt.git`を貼り付けてクローンしてください。

##### クローンが完了したらCobalt.slnを開きソリューションエクスプローラーのCobaltの上で右クリックしプロパティを開いてください。構成プロパティ内の`C/C++`を開くと`プリコンパイル済みヘッダー`という項目があるので、`プリコンパイル済みヘッダーを使用しない`に設定して適用してください。

##### 次にCobalt内の`settings.h`を開いて`ECobaltUsage::Private;`を`ECobaltUsage::Hybrid;`に書き換えて保存し、`Ctrl + B`を押してビルドしてください。成功すればクローンしたファイルの中の`x64`の中の`Debug`というファイルの中に`Cobalt.dll`が作成されていると思います。

### 2.Missionファイルを取得する。

##### ダウンロードした`ｍission_editor.zip`を解凍して中の`MissionEditor.exe`を開きます。

##### `最新のミッションファイルを取得しますか?`と表示されるのではいを選択。ブラウザでEPICGamesアカウントにログインしている状態で表示されているリンクにアクセスすると認証コードを取得できるので貼り付けてください。

![imgur](https://media.discordapp.net/attachments/1084186482975178946/1131445313094307840/auth.png?width=1440&height=103)

### 3.Fiddlerの設定をする。

##### Fiddlerを開き、まず`Tools`の中の`Opotions`を開きます。`HTTPS`に移動し`Capture HTTPS Conets`と`Decrypt HTTPS traffic`と`Check for certificate revocation`にチェックを入れます。

##### 右上の方にある`Actions`を開き`Trust Root Certificate`をクリック。全てYesを押してOKを押してください。

##### Opotionsを閉じ、右上の方にある`FiddlerScript`をクリックしスクリプトを全て削除してSaveしてください。

##### 次に`AutoResponder`をクリックし
