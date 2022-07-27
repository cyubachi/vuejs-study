# at-first

以下のページを写経したもの
https://v3.ja.vuejs.org/guide/introduction.html

* [declarative-rendering](./declarative-rendering.html)
* [control-user-input.html](./control-user-input.html)
* [conditional-branch-and-loop.html](./conditional-branch-and-loop.html)

## 覚えておきたいポイント

* `v-bind` 

    以下はこの要素の title 属性を、現在アクティブなインスタンスにおける message プロパティの最新状態に維持するという意味
    ```
    <span v-bind:title="message">
        Hover your mouse over me for a few seconds to see my dynamically bound
        title!
    </span>
    ```

* `v-on`

    イベントリスナをアタッチしてVueのインスタンスのメソッドを呼び出すことができる
    ```
    <div id="event-handling">
    <p>{{ message }}</p>
    <button v-on:click="reverseMessage">Reverse Message</button>
    </div>
    ```

* `v-model`

    アプリケーションとフォームの入力の状態を双方向にバインディングするためのv-modelも利用可能
    ```
    <div id="two-way-binding">
    <p>{{ message }}</p>
    <input v-model="message" />
    </div>
    ```

* `v-if`

    条件分岐
    ```
    <div id="conditional-rendering">
    <span v-if="seen">Now you see me</span>
    </div>
    ```

* `v-for`

    ループ
    ```
    <div id="list-rendering">
    <ol>
        <li v-for="todo in todos">
        {{ todo.text }}
        </li>
    </ol>
    </div>
    ```

* カスタムコンポーネント

    js
    ```
    const TodoItem = {
    template: `<li>This is a todo</li>`
    }

    // Vue アプリケーションを生成する
    const app = Vue.createApp({
    components: {
        TodoItem // 新しいコンポーネントを登録する
    },
    ... // その他のコンポーネントのプロパティ
    })

    // Vue アプリケーションをマウントする
    app.mount(...)
    ```

    html 
    ```
    <ol>
        <!-- todo-item コンポーネントのインスタンスを生成する -->
        <todo-item></todo-item>
    </ol>
    ```