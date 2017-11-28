Progressive Web App
---
- Eiji Kitayama @agektmr

### Progressive Web Appの作り方
- 「[プログレッシブウェブアプリの作り方](http://www.yahoo.co.jp/)」で検索！！
- ProgressiveWebAppはアイコンがホームに

### 話すこと
- 登録時にIDとパスワードを覚えていてくれると嬉しい
 - Identityの取り扱いを改善
- チェックアウトがハードル高い
 - ペイメントのフローをどう改善してくのか

### Identity
- 初級編 - 何もしない
 - 自動的にブラウザが覚えてくれているのを利用する
 - 80億 / month
- 中級編 - autocompleteを活用
```hmtl
<!-- この形で覚えさせることができる!! -- >
<input name="name" type="text" autocomplete="name" />
```
- 上級編: credential management APIを使う
 - Smart Lock For Passwords
  - これを使うとNativeで自動で入力して保存してくれる
  - いっそこれで保存させちゃえば…？ということでログインもしちゃう
  - これをWebにも適用しようぜというのがCredentialManagementAPI
 - 制御できるAPI
  - ワンタップログイン
  - 自動ログイン
   - セッションが切れた状態で来たら最ログインする仕組み
  - ソーシャルログインの選択肢も保存
   - GoogleやFacebookなど、どれでログインしたかを保存
  - 常に最新のクレデンシャルに
   - ログインに成功した場合のみ更新
   - パスワードが変わった時は上書き
  - より良いセキュリティ
   - 生で入力しないのでXSSやフィッシングのリスクを減らす
  - Android晩SmartLockを実装済みサービスのウェブ版は、
  - 情報を共有されているのでCredentialManagementAPIを使うとよい
 - 実装方法
```
window.FederatedCredential
navigator.credentials
```
- これ超使える。相談上げた方が良いな。

### Payment
- 中級編 - autocompleteを利用
 - パラメータ名が結構色々ある
```
※ カード系
cc-name
cc-number
cc-csc
cc-exp
```
 - 仕様があるのでこれを参照のこと`whatwg autofill`
 - autofillで25％のコンバージョンアップ
- PaymentRequest Apiを利用
 - ユーザをフォームから開放する
   - Credit情報をあんまり持っていないと対象として考えていい
 - 住所情報はブラウザに保存されている
 - 支払も同様。AndroidPayでも行ける
 - 支払の処理部分にアプリを開かせる事もできる
    - 支払用のWebAPIにも対応していくらしい

### 今後について
- Chrome53でPaymentRequestApiでサポート
- Chrome53でAndroidPayもサポート
 - ネイティブアプリをきどうして支払
- CredentialManagementAPIは既にサポート済み
- `PaymentRequestApi`で検索！

### 質疑
- どこからこの個人情報は消せるの？
 - 設定画面から消せるよ
- これらのAPIはデスクトップ版でもできる？UIは一緒？
 - CredentialManagementAPIはある。
 - PaymentRequestApiは今後予定レベル
- 攻撃の体制として大量のデータを入れてしまうのは対策しているの？
 - 数千万件の登録情報はどうなる・・・？
 - すみません、わからないですとのこと。対策はしていそう

### 感想
- 携帯端末が情報端末として以上に個人に密接したものに成るね
- 今後のスマートフォンにおけるUXが便利すぎる感じに
