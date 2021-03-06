# Vue.jsを触ってみよう

(1)

Vue.jsをCDN(Contents Delivery Network)から読み込みます。今回は学習目的なので、簡単に環境構築できる方法を選択しています。業務などで本格的なアプリケーションを開発する場合は、Vue CLIなどを使って環境構築することが多いと思います。(参考: [インストール — Vue.js](https://jp.vuejs.org/v2/guide/installation.html))


(2)

Vue.jsの実体(=インスタンス)を作成している箇所です。`new Vue()`とすることで、Vue.jsのインスタンスを作成することができます。`new Vue({ el: '#app' })`のように、JSのオブジェクトリテラルを渡すことで、インスタンス生成時のオプションを指定できます。指定できるオプションの一覧は、[API — Vue.js](https://jp.vuejs.org/v2/api/#%E3%82%AA%E3%83%97%E3%82%B7%E3%83%A7%E3%83%B3-%E3%83%87%E3%83%BC%E3%82%BF)です。今回のコードで利用しているオプションは、以下のものです。

- [el](https://jp.vuejs.org/v2/api/#el)
- [data](https://jp.vuejs.org/v2/api/#data)

詳しい説明はリンク先を見ていただきたいですが、ざっくり説明でいうと、以下のようなものです。

- el 
  - HTMLのどの部分をVue.jsの処理対象にするかを決めるオプション
  - CSS風なセレクタでHTMLのDOMを指定する (e.g. `'#app'`)

- data
  - 保持したい状態を、`{ data名: 値 }`の形式で指定するオプション
  - 作成した状態は、HTMLと紐付ける(bindingと言ったりもする)ことができる
    - 紐づける方法はいくつか種類があるが、その内の1つが `{{ data名 }}` (HTML上に、`data`オプションで保持している状態を表示できる)

(3)

(2)で説明した、`el`オプションと一致するDOMなので、Vue.jsが処理します。`{{ greet }}`と書いてHTMLと紐付けを行なっているので、ブラウザで表示すると、`こんにちは！`(`data`オプションで保持している`greet`の値)が表示できます。

(4)

(2)で説明した、`el`オプションと一致しないDOMなので、Vue.jsが処理をしません。そのため、`{{ greet }}`と書いても、単なる文字列としてそのまま表示します。