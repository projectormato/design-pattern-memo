# GoFのデザインパターンについての自分用メモ
概要だけさらっと、後コード

## 生成に関するパターン

### Abstract Factory
互いに関連したり依存し合うオブジェクト群を、その具象クラスを明確にせずに生成するためのインターフェースを提供する。

Client側が具体的にElfKingなのかOrcKingなのか気にしないでも使えるように提供することで関心の分離が出来て良いよねってことみたい。

see: https://github.com/iluwatar/java-design-patterns/tree/master/abstract-factory

### Builder

see: https://github.com/iluwatar/java-design-patterns/tree/master/builder

### Factory Method
オブジェクトを生成するインターフェースだけを規定して、実際にどのクラスをインスタンス化するかはサブクラスが決めるようにする。
Factory Methodパターンは、インスタンス化をサブクラスに任せる。

サブクラスを呼んで、提供されてるオブジェクトを生成するメソッドにenumとかを渡して、実際に何クラスがインスタンス化されるかはClientは気にしない。
ロジックとか変えたい時とか増やしたいときはサブクラスだけいじれば良いから良いのかな

see: https://github.com/iluwatar/java-design-patterns/tree/master/factory-method

### Prototype

see: https://github.com/iluwatar/java-design-patterns/tree/master/prototype

### Singleton

see: https://github.com/iluwatar/java-design-patterns/tree/master/singleton

## 構造に関するパターン

### Adapter
あるクラスのインターフェースを、クライアントが求める他のインターフェースへと変換する。
Adapterパターンは、インターフェースに互換性のないクラス同士を組み合わせることができるようにする。

インターフェースimplementsして関係ないクラスをフィールドで持ってインスタンス化して、
そのインターフェースのメソッドとかの振る舞いをフィールドのクラスの振る舞いで定義しちゃう。色々使えそう。

see: https://github.com/iluwatar/java-design-patterns/tree/master/adapter

### Bridge

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

see: https://github.com/iluwatar/java-design-patterns/tree/master/facade

### Flyweight

see: https://github.com/iluwatar/java-design-patterns/tree/master/flyweight

### Proxy

see: https://github.com/iluwatar/java-design-patterns/tree/master/proxy

## 振る舞いに関するパターン

### Chain of Responsibility

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
