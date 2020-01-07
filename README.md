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

### Adepter

クラスに焦点(どっちもある)
最初
see: https://github.com/iluwatar/java-design-patterns/tree/master/adapter

### Bridge

see: https://github.com/iluwatar/java-design-patterns/tree/master/bridge

### Composite

最初
see: https://github.com/iluwatar/java-design-patterns/tree/master/composite

### Decorator

最初
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

最初
see: https://github.com/iluwatar/java-design-patterns/tree/master/observer

### State

see: https://github.com/iluwatar/java-design-patterns/tree/master/state

### Strategy

最初
see: https://github.com/iluwatar/java-design-patterns/tree/master/strategy

### Template Method

クラスに焦点
最初
see: https://github.com/iluwatar/java-design-patterns/tree/master/template-method

### Visitor

see: https://github.com/iluwatar/java-design-patterns/tree/master/visitor
