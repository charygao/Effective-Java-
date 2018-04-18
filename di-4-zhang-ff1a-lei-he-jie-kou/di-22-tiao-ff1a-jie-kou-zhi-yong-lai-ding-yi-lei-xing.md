### 第22条：接口只用来定义类型

When a class implements an interface, the interface serves as

当一个类实现了一个接口，这个接口可以作为一个类型，并作为实现它的类实例的引用。因此，若一个类实现了一个接口，则表明了客户端可以如何处理该类的实例。为其它目的来定义一个接口是不合适的。

One kind of interface that fails this test is the so-called constant

有种接口并不符合上述的目的，它就是所谓的常量接口。这种接口不包含方法；它仅有静态final域组成，每个域导出一个常量。需要使用这些常量的类通过实现接口而避免了需要用类名来限定常量名。下面是一个例子：

```
// Constant interface antipattern - do not use!
public interface PhysicalConstants {
// Avogadro's number (1/mol)
static final double AVOGADROS_NUMBER =
6.022_140_857e23;
// Boltzmann constant (J/K)
static final double BOLTZMANN_CONSTANT =
1.380_648_52e-23;
// Mass of the electron (kg)
static final double ELECTRON_MASS = 9.109_383_56e-31;
}
```


