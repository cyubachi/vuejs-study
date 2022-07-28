# application-and-component-instance

以下のページの内容で覚えておきたいものをまとめたもの
https://v3.ja.vuejs.org/guide/instance.html

## 覚えておきたいポイント

* 全ての Vue アプリケーションは createApp 関数で新しい アプリケーションインスタンス (application instance) を作成するところから始まる
* アプリケーションインスタンスが公開するほとんどのメソッドは、同じインスタンスを返すので、チェーンすることが可能

* createApp に渡されたオプションは、ルートコンポーネント の設定に使われる。  
  このコンポーネントは、アプリケーションを マウント する際に、レンダリングの起点として使われます。

* アプリケーションは DOM 要素にマウントする必要がある。  
  例えば、 Vue アプリケーションを `<div id="app"></div>` にマウントしたい場合、 #app を渡す必要がある
  ```
  const RootComponent = {
  /* オプション */
  }
  const app = Vue.createApp(RootComponent)
  const vm = app.mount('#app')
  ```

* ほとんどのアプリケーションメソッドとは異なり、 mount はアプリケーションを返しません。代わりにルートコンポーネントのインスタンスを返す

* data で定義されたプロパティは、コンポーネントインスタンスを介して公開される
    ```
    const app = Vue.createApp({
    data() {
        return { count: 4 }
    }
    })

    const vm = app.mount('#app')

    console.log(vm.count) // => 4
    ```

* コンポーネントインスタンスのすべてのプロパティは、それらがどのように定義されているかに関わらず、コンポーネントのテンプレートからアクセスできる。

* Vue はコンポーネントインスタンスを介した $attrs や $emit などいくつかの組み込みプロパティも公開していて、これらのプロパティはすべて $ プレフィックスとなっており、ユーザ定義のプロパティ名と衝突を避けるようになっている。

* ライフサイクルダイアグラム
　後でたくさん見ることになりそう
  https://v3.ja.vuejs.org/guide/instance.html#%E3%83%A9%E3%82%A4%E3%83%95%E3%82%B5%E3%82%A4%E3%82%AF%E3%83%AB%E3%82%BF%E3%82%99%E3%82%A4%E3%82%A2%E3%82%AF%E3%82%99%E3%83%A9%E3%83%A0

* 