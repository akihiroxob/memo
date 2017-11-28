Web技術動向とブラウザベンダー戦略のこれから
---
- Tomoya ASAI
- @dynamitter
- shideshare.net/dynamis

### 現在のWebと近未来のWeb
### 第一部
- わんこはServoエンジン
 - rust
- LocalとGlobalで相互接続がされた際に、ただ繋がるだけでは意味が無い
- デバイスがすべてインターネットの一部になるのが、今後の確信となる
- cpuコアがたくさんあるから並列処理は大事
- 全部Workerに分けるような作りがよい
- Foxkeh Embedded

### 第二部
- パッケージ型アプリの終焉
- デスクトップ向けWebアプリの今後
 - PWA - Progressive Web App
   - ServiceWorkerでインストールさせていく形
- 標準化は二社以上が実装しないと標準にならない
- Positron, SpiderNodeなどでちゃんと作られている
- 課金系システム
 - Safari - Apple pay
 - Chrome - Android Pay
- ビデオの自動再生
 - 音さえ出さなければ自動再生できるように
- 接頭辞から実行時 config/flagへ
 - no more -webkit-
- AndroidなどのFireFoxブラウザで、端末の情報は一切載せないと明言された
- HTMMLはLivingの無印を見ているとよい
- 日本語組版レベルのWebへ
- CSS Font Features
- Math.randomが更新された！
- SharedArrayBufferがすごい
- ::backdrop
- addEventListenerのonceオプションがFirefox 2016/11
- Presentation API
- linkの要素のPreloadがある
- preventDefaultをしないぜ！って宣言ができる
- CSS Containment
- Shadow DOM実装がv0からv1に
 - 実装は進んでいる
- 6-8週間毎にWeb世界は更新されている






### 調べるもの
- MPU
- SOC
- NXP
- FireFox on Renesaas RZ/G Yocto
- Yocto Project
- shimizu
- XULRunner, Graphene on Gecko
- Animation周りはひととおり調べておこう
- Broti Algolism
