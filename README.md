Java开发面试知识点

#Java基础
怎么实现多态？
父类定义子类的构建、接口定义实现类的构建、抽象类定义实体类的构建

参考：Java中的多态有哪些具体表现形式

override、overload区别？
overload 方法重载：一个类中多态性的一种表现。多个方法具有相同的方法名和不同的参数列表（参数个数、参数类型或参数顺序），返回类型可以相同也可以不同。

override 方法重写：父类与子类之间多态性的一种表现。子类中定义的方法与父类中的方法具有相同的名字、参数列表、返回值类型。（@Override 是一个关键字。@Override是告诉使用者这个方法是重写了基类或者接口的方法。不加编译器也知道这个方法重写了基类或者接口的方法。不加理解上默认已经加过，加了子类或者接口没有对应需要重写的方法则一定会报错。）

参考：Java 重写(Override)与重载(Overload)

接口和抽象类区别？
1、抽象方法：抽象方法是一种特殊的方法：它只有声明，而没有具体的实现。必须用 abstract 关键字进行修饰。

abstract void fun();
抽象类：如果一个类含有抽象方法，则称这个类为抽象类，抽象类必须在类前用 abstract 关键字修饰。

[public] abstract class ClassName {
    abstract void fun();
}
抽象类和普通类的区别：

1）抽象方法必须为 public 或者 protected（因为如果为 private，则不能被子类继承，子类便无法实现该方法），默认情况下默认为 public。

2）抽象类不能用来创建对象；

3）如果一个类继承于一个抽象类，则子类必须实现父类的抽象方法。如果子类没有实现父类的抽象方法，则必须将子类也定义为为 abstract 类。

 

2、接口：接口中可以含有 变量和方法，一般情况下不在接口中定义变量。接口中的变量会被隐式地指定为 public static final 变量，而方法会被隐式地指定为 public abstract 方法且只能是 public abstract 方法，并且接口中所有的方法不能有具体的实现。

[public] interface InterfaceName {
 
}
允许一个类遵循多个特定的接口。如果一个非抽象类遵循了某个接口，就必须实现该接口中的所有方法。对于遵循某个接口的抽象类，可以不实现该接口中的抽象方法。

 

抽象类和接口的区别：

1、语法层面上的区别

1）抽象类可以提供成员方法的实现细节，而接口中只能存在public abstract 方法；

2）抽象类中的成员变量可以是各种类型的，而接口中的成员变量只能是public static final类型的；

3）接口中不能含有静态代码块以及静态方法，而抽象类可以有静态代码块和静态方法；

4）一个类只能继承一个抽象类，而一个类却可以实现多个接口。

2、设计层面上的区别

抽象类是对一种事物的抽象，即对类抽象，而接口是对行为的抽象。抽象类是对整个类整体进行抽象，包括属性、行为，但是接口却是对类局部（行为）进行抽象。

抽象类作为很多子类的父类，它是一种模板式设计。而接口是一种行为规范，它是一种辐射式设计。对于抽象类，如果需要添加新的方法，可以直接在抽象类中添加具体的实现，子类可以不进行变更；而对于接口则不行，如果接口进行了变更，则所有实现这个接口的类都必须进行相应的改动。
