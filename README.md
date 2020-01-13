# GoFのデザインパターンについての自分用メモ
概要だけさらっと、後コード

## 生成に関するパターン

### Abstract Factory
互いに関連したり依存し合うオブジェクト群を、その具象クラスを明確にせずに生成するためのインターフェースを提供する。

Client側が具体的にElfKingなのかOrcKingなのか気にしないでも使えるように提供することで関心の分離が出来て良いよねってことみたい。

see: https://github.com/iluwatar/java-design-patterns/tree/master/abstract-factory

### Builder
複合オブジェクトについて、その生成過程を表現形式に依存しないものにすることにより、同じ作成過程で異なる表現形式のオブジェクトを生成できるようにする。

Builder().age(xxx).tall(yyy).build() みたいな、よく見るやつ。全部Heroのコンストラクタにつっこむよりすっきりする。

see: https://github.com/iluwatar/java-design-patterns/tree/master/builder

### Factory Method
オブジェクトを生成するインターフェースだけを規定して、実際にどのクラスをインスタンス化するかはサブクラスが決めるようにする。
Factory Methodパターンは、インスタンス化をサブクラスに任せる。

サブクラスを呼んで、提供されてるオブジェクトを生成するメソッドにenumとかを渡して、実際に何クラスがインスタンス化されるかはClientは気にしない。
ロジックとか変えたい時とか増やしたいときはサブクラスだけいじれば良いから良いのかな

see: https://github.com/iluwatar/java-design-patterns/tree/master/factory-method

### Prototype
生成するべきオブジェクトの種類を原型となるインスタンスを使って明確にし、それをコピーすることで新たなオブジェクトの生成を行う。

ミュータブルで、共通の振る舞いも結構持っているオブジェクトをたくさん生成するときは色々頑張るよりもcopyした方が楽そう。

see: https://github.com/iluwatar/java-design-patterns/tree/master/prototype

### Singleton
あるクラスに対してインスタンスが1つしかないことを保証し、それにアクセスするためのグローバルな方法を提供する。

固定で使いたい値を、インスタンスが1つしかないことを保証して使い回すことで使うってことみたい。
複数生成されてはいけないし、それがアプリケーション全体のコンテキストとして値が変更されてもいけない。(それはグローバル変数なので)

see: https://github.com/iluwatar/java-design-patterns/tree/master/singleton

## 構造に関するパターン

### Adapter
あるクラスのインターフェースを、クライアントが求める他のインターフェースへと変換する。
Adapterパターンは、インターフェースに互換性のないクラス同士を組み合わせることができるようにする。

インターフェースimplementsして関係ないクラスをフィールドで持ってインスタンス化して、
そのインターフェースのメソッドとかの振る舞いをフィールドのクラスの振る舞いで定義しちゃう。色々使えそう。

see: https://github.com/iluwatar/java-design-patterns/tree/master/adapter

### Bridge
抽出されたクラスと実装を分離して、それらを独立に変更できるようにする。

抽出したクラスのインスタンスを生成するときに実装を受け取ってそれを使用する。
そうするとWeaponもEnchantmentもお互いに関係なく独立して実装ができる。

see: https://github.com/iluwatar/java-design-patterns/tree/master/bridge

### Composite
部分と全体階層を表現するために、オブジェクトを木構造で組み立てる。
Compositeパターンにより、クライアントは、ここのオブジェクトとオブジェクトを合成したものを一様に扱うことができるようになる。

部分と合成したものを一様に扱えるか。HTMLの構造みたいなものを表現したいときに良いみたい(ツリーの構造はあるけど、どれもtagだよねみたいな)

see: https://github.com/iluwatar/java-design-patterns/tree/master/composite

### Decorator
オブジェクトに責任を動的に追加する。Decoratorパターンはサブクラス化よりも柔軟な機能拡張方法を提供する。

1つの性質を2回与えることとかも容易。色々使えそう。

see: https://github.com/iluwatar/java-design-patterns/tree/master/decorator

### Facade
サブシステム内に存在する複数のインターフェースに1つの統一インターフェースを与える。
Facadeパターンはサブシステムの利用を容易にするための高レベルインターフェースを定義する。

関心の分離ができるので良さそう、単純だし、色々使えそう。

see: https://github.com/iluwatar/java-design-patterns/tree/master/facade

### Flyweight
多数の細かいオブジェクトを効率よくサポートするために共有を利用する。

等価なオブジェクトを何度も使うなら、その度生成するんじゃなくて共有しておきましょう。ということみたい。

see: https://github.com/iluwatar/java-design-patterns/tree/master/flyweight

### Proxy
あるオブジェクトへのアクセスを制御するために、そのオブジェクトの代理、または入れ物を提供する。

そのままな感じ。オブジェクトへのアクセスを制御するのは、コストの高い処理をなるべく行わないようにするため。

see: https://github.com/iluwatar/java-design-patterns/tree/master/proxy

## 振る舞いに関するパターン

### Chain of Responsibility
1つ以上のオブジェクトに要求を処理する機会を与えることにより、要求を送信するオブジェクトと受信するオブジェクトの結合を避ける。
受信する複数のオブジェクトをチェーン状に繋ぎ、あるオブジェクトがその要求を処理するまで、チェーンに沿って要求を渡していく。

直接的な結合を避けられるので良さそう。

see: https://github.com/iluwatar/java-design-patterns/tree/master/chain

### Command

see: https://github.com/iluwatar/java-design-patterns/tree/master/command

### Interpreter

see: https://github.com/iluwatar/java-design-patterns/tree/master/interpreter

### Itetator

クラスに焦点
see: https://github.com/iluwatar/java-design-patterns/tree/master/iterator

### Mediator

see: https://github.com/iluwatar/java-design-patterns/tree/master/mediator

### Memento

see: https://github.com/iluwatar/java-design-patterns/tree/master/memento

### Observer
ありオブジェクトが状態を変えたとき、それに依存する全てのオブジェクトに自動的にそのことが知らされ、また、それらが更新されるように、オブジェクト間に1:Nの依存関係を定義する。

イメージが掴みきれてない、何に使えるんだろう。ブラウザのイベントリスナーとかはこれみたい、アプリケーションのクリックとかを感知してブラウザの実装に通知するみたいな。

see: https://github.com/iluwatar/java-design-patterns/tree/master/observer

### State

see: https://github.com/iluwatar/java-design-patterns/tree/master/state

### Strategy
アルゴリズムの集合を定義し、各アルゴリズムをカプセル化して、それらを交換可能にする。
Strategyパターンを利用することで、アルゴリズムをそれを利用するクライアントからは独立して変更することができるようになる。

分かりやすく便利そう。いくつか違うアルゴリズム良い感じに使わないといけない時とか。

see: https://github.com/iluwatar/java-design-patterns/tree/master/strategy

### Template Method
1つのオペレーションにアルゴリズムのスケルトンを定義しておき、その中のいくつかのステップにおいては、サブクラスでの定義に任せることにする。
Template Methodパターンでは、アルゴリズムの構造を変えずに、アルゴリズム中のあるステップをサブクラスで定義する。

HalflingThiefでどのサブクラスを使うか切り替えられるようにするのすごく分かりやすい。
これは結構使えそう、基本の流れは一緒だけど、参照するクラスとかテーブルとかロジックとか微妙に違うみたいなのよくありそう。

see: https://github.com/iluwatar/java-design-patterns/tree/master/template-method

### Visitor

see: https://github.com/iluwatar/java-design-patterns/tree/master/visitor
