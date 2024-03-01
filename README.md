# 開発者ミッションにアクセスする方法

世界を救えの開発者ミッションにアクセスする方法を記載します。

**※損害発生時の責任について：**
この手順に従って行動した場合、発生した損害については一切責任を負いかねます。

## 1. 必要なソフトウェアの準備

- [VisualStudio2022](https://visualstudio.microsoft.com/ja/vs/)
- [Xenos](https://github.com/DarthTon/Xenos/releases/tag/2.3.2)
- [Fiddler](https://www.telerik.com/download/fiddler)
- [MissionEditor](https://github.com/LemonCCjp/Savetheworld-MissionEditor)

すべてのソフトウェアをダウンロードし、インストールしてください。

（注：XenosやCobaltはウイルス対策ソフトによって削除される可能性があるため、オフにするか許可を与える必要があります。）

### VisualStudio2022のインストール
VisualStudio2022をインストールする際は、C言語（C, C++, C# など）関連のオプションをすべて選択し、インストールしてください。インストールには時間がかかります。

全てのインストールが完了したら、次の手順に進んでください。

- Cobaltのリポジトリをクローンしてください。リンク：`https://github.com/Milxnor/Cobalt.git`
- Cobalt.slnを開き、プロパティを設定します。
  - Cobaltの上で右クリックし、プロパティを開いてください。
  - 構成プロパティ内の`C/C++`を開き、「プリコンパイル済みヘッダーを使用しない」に設定してください。
- Cobalt内の`settings.h`を開き、`ECobaltUsage::Private;`を`ECobaltUsage::Hybrid;`に書き換えて保存します。
- `Ctrl + B`を押してビルドしてください。成功すると、`Cobalt.dll`が作成されます。

## 2. Missionファイルを取得する

- `ｍission_editor.zip`をダウンロードして解凍します。
- 中にある`MissionEditor.exe`を開きます。
- 「最新のミッションファイルを取得しますか？」と表示されたら「はい」を選択します。
- 表示されたリンクにアクセスして認証コードを取得し、貼り付けます。
- 同じ階層に`mission.json`が作成されます。
- 必要に応じてミッションのアクセス制限を解除し、編集を行います。

## 3. Fiddlerの設定

- Fiddlerを開き、`Tools`の中の`Opotions`を開きます。
- `HTTPS`に移動し、`Capture HTTPS Conets`と`Decrypt HTTPS traffic`と`Check for certificate revocation`にチェックを入れます。
- `Actions`を開き、`Trust Root Certificate`をクリックします。全ての許可を与えてOKを押してください。
- `FiddlerScript`を削除して保存します。
- `AutoResponder`を開き、`Enable Rules`と`Unmatched requests passthrough`にチェックを入れます。
- `Add Rule`を押し、`https://fngw-mcp-gc-livefn.ol.epicgames.com/fortnite/api/game/v2/world/info`を貼り付けます。下のボックスから`mission.json`を選択して保存します。

## 4. Fortniteを起動する

- Fortniteを起動する前にXenosを開きます。
- `add`を押し、`Cobalt.dll`を選択します。
- EPICGamesLauncherからFortniteを起動し、ロードが始まったら次のいずれかのプロセスを選択して`Inject`します。
  - `FortniteClient-Win64-Shipping_BE.exe`
  - `FortniteClient-Win64-Shipping_EAC`
  - `FortniteClient-Win64-Shipping_EAC_EOS`
（`FortniteLauncher`は選択しないでください。）

これで開発者ミッションが開放されます。

![変更後の表示](https://pbs.twimg.com/media/GF-CeBna0AAn1yA?format=jpg&name=large)

## MissionEditorの機能

- アクセス制限の解除
- アラート交換
- theater表記の変更
- 最新ファイルの取得
- 再読み込み
- ミッション検索
- ミッションの上書き
- アラート削除

詳細は[こちら](https://github.com/LemonCCjp/Savetheworld-MissionEditor)をご覧ください。

