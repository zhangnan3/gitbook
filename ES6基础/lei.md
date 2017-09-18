######类的继承也是面向对象编程的基本知识。

* 类的继承

```
class Person {
  sayKind(){
    console.log('human')
  }
}
class Men  extends Person{
  sayGender(){
    console.log('Male');
  }
}
class Women extends Person{
  sayGender(){
    console.log('Famale')
  }
}
const peter =new Men
const billie =new  Women
peter .sayKind()
billie .sayKind()


```
* 上面代码中，父类是 Person ，子类就是 Women 和 Men 。extends 英文本意是拓展 ，这里基本就是继承的意思
