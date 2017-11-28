WebGL 2.0
---

### WebGL2.0 現実的なウェブにおける影響は?
- Sugimoto Masahiro (doxas
- WebGL2.0の機能的なものに関してはスライドのリンクを参照

### WebGL2.0
- ドライバテスト通過済みでWebGLは利用しても良いと思って良さそう
 - ハードウェア側は準備OK
- 嬉しさとは何か、どんなイノベーションが起きるかという視点
 - 現状はChrome Canaryのみで動作
- Webの世界でもCGが当たり前になりそう
 - どんどんリッチなUIになっていくね
- three.jsのcontributerが一通り対応をしてくれる
 - WebGL周りはスクラッチでかくより、Three.jsをフル活用する方向が賢そう
 - three.jsのLicense次第だけど
- 既存のWebGLとそもそも違う処理になっているので、後方互換は気にせずOK
- tyottodakeyokunattayotte kotowo 20hun tukatte hanasiteta

### slide url
- https://doxas.org/slide/html5conf2016/

Web VR
---
### 話す人
- 比留間 和也

### Web VRとは
- 2016年はVR元年
 - VRの登場は1960年代
 - デパートのアトラクションとしてが最初
- WebVRはWebで実現する技術…ではない！
 - APIの名称
 - W3Cで勧告されている仕様
 - //w3c.github.com/w3c/webvr/
- Mozzilaさんが頑張ってサンプル作っているっぽい。MDN?
- やることは3つ
 - VRディスプレイ(デバイス)の取得
 - ユーザのポーズ(姿勢)の取得 キャリブレーション
 - ヘッドセットの空間
 - eyeパラメータs
- 想像以上にデバイスと接続している
 - APIはデバイスのパラメータ取得がメイン
- 3D部分はWebGLでコンテンツを作成する
 - 基本的にthree.jsで作るのが非常にお手軽ってことで
- モバイルでの体験方法がいろんな方法が増えている
 - 適切なコンテンツを適切な表現するのが非常に大事そう
### 調べる単語
- 物理ベースレンダリング
- 遅延レンダリング
- skybox

