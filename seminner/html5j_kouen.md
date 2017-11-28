HTML5 Conference

# 基調講演

### 村井純先生
- 俺の考えるインターネット原理
    1. フラグメントするな、グローバル標準だ
    2. 全計算機資源はインターネットで最適利用できる
    3. 洗練された分散処理の理想の基盤であるべき
    4. 計算速度と量に対する要求はムーアの法則どころじゃない。際限ない。
        - ブラウザでWebRTCなどで並列処理ができるようになると嬉しいらしい。
    5. インターネット上のデータ量は無限に増えると考えるべきだ
    6. 経路の冗長性、資源の保管性、その切替の判断がインターネットの命だ。
    7. 分散した協調運用が神。安定して柔軟な運用は分散システムとしてのみ可能。
    8. システムを守ろう。人を守るのは社会がやる。

### 及川さん
- 新しい技術潮流とWeb
    - 技術イノベーションからWebへの影響を考える
    - Hype Cycle ( Gartner )
        - 技術の黎明期から安定までどのように普及していくかの流れ
    - ３つのトレンド(emerging technology)
        - AI everywhere
            - AI
        - Transparently Immersive Experiences
            - 透過的な没入体験
            - VR/AR
            - ブレインコンピュータインターフェイス
        - Digital Platforms
            - Iot、BlockChain
    - Webでは？
        - HypeCycleにたいしてWebはどう関わっている？
    - 技術トレンドとWeb
        - W3Cにはグループやコミュニティが出来ている
        - AI以外は。
    - AI
        - 機械学習 = データ + コンピューティングパワー
        - 機会に優しいWebを目指す必要がある
    - SPA、PWA、Headless Chrome…
        - 機会には優しくない
        - セマンティックス性を深める必要が有る
        - 人と機会の両方に読ませる必要がある
            - JSON-LDとWebComponentsを組み合わせていくというのも面白い

# 各セッション

### なかゆうすけ　WebRTC
- 実践 WebRTC ~ 最新事例とカイアhつノウハウの紹介 ~
- スライド
    - https://www.slideshare.net/yusukenaka52/webrtc-80090858
- 60. この話がわかりやすく解説されています SDP: Your Fears Are Unleashed https://webrtchacks.com/webrtc-sdp-inaki-baz-castillo/
- 62. そんなAPIの進化ついていけない… 大丈夫です。 adapter.js（shim）を使えばだいたいうまくやってくれます。
    - Shim to insulate apps from spec changes and prefix differences
    - https://github.com/webrtc/adapter/
- 74. 雰囲気じゃなくてちゃんとやりたい人はこれ読もう
    - https://goo.gl/9DWMGZ @leader22

### 佐藤歩 @ahomu
- 最近のWebパフォーマンス改善について知っておきたいこと
    - パフォーマンス
        - ページロード
            - Spead Curve (ツール
        - ランタイム
            - ページを開いた後
            - FPS
            - Chromeのデバッガ、FrameChartで取得できる
    - 多様性
        - 変数
            - デバイス
            - ブラウザ、OS
            - ネットワーク
            - ユーザ
        - 速度の基準
        - http://developers.google.com/web/fundatmentals/performance/all
            - なんかあったね、こんなの
    - ページロードの技術
        - クリックして開くまで
        - scriptタグのasyncはともかく、deferってなんぞ
    - 操作までの時間を一度計測しておこう
        - キャッシュしている場合と、していない場合
        - わりとチリツモ。
        - JavaScript Start-UP Performance　re.loading
        - zopfli, brotli
            - あとで詳細調べる
            - gzip的な圧縮関連
        - es modules ブラウザ側対応
            - いつから使えんだろ
        - preloadとresource hints
            - preloadはロードの前に取る
            - 他のpreは説教的に行うよ
    - 計測、評価方法
        - Synthetic Monitoring
        - Real User monitoring
        - UserTimingAPI
    - Runtime
        - JSはあくまでシングルスレッドなのを考える
        - Project Quantum
            - Firefox (Mozilla)
        - Intersection Observer IntersectionObserver
            - LazyLoadがハイパー簡単にできるそうで…
            - めっちゃいい！！
        - element.addEventListener('touchmove', ()=>{}, {passive: true})
        - requestIdleCallback
        - css will-change
            - will-change: transform
        - css Containment
            - 処理を封じ込め

### Diogo Franco @kovensky
- ECMAScript and the feture with Babel.
- https://slack.babeljs.io/
- Technical Committee 39
    - https://github.com/tc39/ecma262
    - https://github.com/tc39/proposals
    - http://github.com/tc39/agendas
    - https://github.com/rwaldron/tc39-notes
- stage-0("strawman")
    - ただのアイデア vague idea
    - 誰も意義しなければStage-0になる
    - 実際に言語になるかはわからない
- stage-1('proposal')
    - concrete proposal
    - specに書いてるぐらい
    - Array.prorotype.flatMap
- stage-2('draft')
    - 将来に言語にはいると思われるもの
- stage-3('candidate')
    - この段階はブラウザに実装して欲しい状態
    - Chromeのnightlyとかに入っているレベル
- stage-4('finished')
    - ２つのブラウザエンジンで実装されている必要がある
    - 浅井さんが以前行っていたやつだね
- Babelとの関連
    - ECMAScript6を5に変更するための仕組み
    - まだ必要
- 将来的にも必要なのか？
    - JSの拡張で必要
        - JSX
            - 関数のショートハンド
        - 新ESProposalの仕様
    - Babel6
        - babel-core
            - API Entry pointメインライブラリ
        - babylon
            - ASTを作るための仕組み
        - babel-traverse
            - Pluginを実行する
        - babel-generate
            - 新しいソースコードを作成する
        - babel-types
            - 便利ライブラリ、これいま必須になってる？npmで怒られる
        - Babel Plugin
            - visitor keyを基本的に拡張して作成する
        - polyfills
            - ブラウザの足りない部分を実行するやつね。
            - SPECが完成していないときとかもやってくれる
        - Userful API
            - scope
                - アクセスできるidentifierが見れる
            - babel-template
                - ソースコードを解釈してミニastを作成してくれる
                - human-readble manner
        - TC39 involvement
    - REPL Improvements
        - https://babeljs.io/repl
    - babel-preset-env from babel 7
    - OpenCollective
        - https://opencollective.com/babel
        - Started Recently

### 浅井 智也
- Web 技術とブラウザ - 今知っておくべきWeb最新動向 - 
- CTO @ WebDINO Japan(2017年7月にMozilla JAPANから社名変更)
    - CTOになってる…！
- スライド
    - slideshare.net/dynamis
- 去年から今年
    - html5終了(obsolete)
        - CTCを通過
        - ACレビューの段階
    - 昨年のWeb標準実装状況
        - 2016年 9912  / 12106 Chrome
        - 2017年 10871 / 12193 Firefox
            - position: stickyってなんだろ
        - Progressive Web Application(PWA)
            - ServiceWorker、Push、Paymeny Request API
        - マルチメディア系API
            - WebGL、WebVR
    - 開発ツールの新機能
        - ビデオで学べるとのこと
        - What's New in Chrome
        - What's Nw in DevToolsが新たに開始
- Chrome update
    - 56(2017/02)
        - Web Bluetooth API対応
            - BLEのGATTプロトコルに対応
        - CSS position: sticky
        - WebVR(origin)
    - 57(2017/03)
        - CSS Grid Layoutに対応
            - 今年最も注目の新機能
        - Media Session API
            - 再生中のメディア情報をロック画面へ
    - 58(2017/4)
        - IndexedDB 2.0 サポート完了
        - フル画面アプリ(display: fullscreen)
            - web app manifestにて指定すると全画面起動
            - iPhone Xでのフル画面
        - CSS display: flow-root
            - clear fix Hackとのお別れ
    - 59(2017/5)
        - Headless Browsingサポート
            - メモリ内で自動処理
            - Firefoxも同時期に同様の機能をサポート
        - Notificationの表示がMacOS標準UIに
        - Image Capture API
            - カメラで写真撮影
    - 60(2017/07)
        - Paint Timing API
            - Headless Browsingでも利用可能
        - CSS font-display
            - WebFont読み込み時の反映タイミングを指定
        - WebAssembly 正式対応‼
    - 61(2017/09)
        - JavaScript Moduleのサポート
        - Payment Request API
        - WebShareAPI, WebUSB
            - シェアするのはもう「標準」
            - ネイティブ系の機能の実装に積極
- Edge Update
    - jiggles
    - ユーザのフィードバックを次々と対応している
        - Sonar(lint)
    - Payment Request API
    - Brotli(RFC 7932)
    - ServiceWorker
        - やっと対応したか…
    - WebVR、WebRTC
    - レンダリング
- FireFox updated
    - HTMLInputEement.webKitxx
    - FLAC音声コーデックに対応
    - WebGL
    - WebAssembly
- Safari
    - Safari Grid Layout
    - Fetch API
    - WebAssemblyサポート


### 泉水さん @1000ch
- Te state of web Components
- Why Web Components
    - Webにおける部品の難しさ
        - HTMLとCSSにスコープが存在しない
        - 作った部品を再利用しにくい
    - WebComponents
        - Shadow DOM
        - Custom Elements
        - Html Imports → 今は ES Modules
        - Templates
    - Shadow Dom
        - HTML, CSS, JSの影響範囲を限定する
        - ShadowDOM外部からの影響を限定する

```
const button = document.quertSelector('botton');
const shadowRoot = botton.attach
----------------------
<button>
    #shadow-root
    <style>
        button{}
    </style>
    <button>
        <slot></slot>  ⇠ 本来の子要素が入る 
    </button>
    fancy button
</button>
```
- custom elementsとは
        - 独自のHTML要素を宣言する
        - 任意の振る舞いを定義する
    - カスタム要素のライフサイクル
        - constructor
        - connectedCallback
        - dissconnectedCallback
        - attributeChangedCallback
        - adoptedCallback
- shadow dom + web componentns
    - バッチリ scoped
- templates
    - 非活性なHTML要素を宣言する
    - https://1000ch.github.io/webcomponents-sandbox
- webcomponents.js
- WAI-ARIA
- ATF
