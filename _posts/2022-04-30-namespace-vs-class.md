# The differences beteween namespace and class

- A **class** is a data type. If you have a class named `boo`, you can create objects of class `boo` and use them in many ways.

- A **namespace** is simply an abstract way of grouping items together. Normally, you cannot have two functions in your program named `boo()`. If you place them in separate namespaces, then they can coexist (for example, as `A::boo()` and `B::boo()`). A namespace cannot be created as an object; think of it more as a naming convention.

- If you are writing code that you want to be associated with an object that you can define and use as a variable, write a class. If you are writing an API or library and you want to wrap up all of the functions and constants so that their names don't clash with anything that the user might have written, use a namespace.

- A **class** defines a type, a **namespace** may contain multiple classes.
- You can have a unnamed namespace, but can not have a unnamed class.

- One major difference is that **namespace** can be re-opened, but **class** cannot be:

``` cpp
namespace A {
    int f1();
}

namespace A {
    int f2();
}
```

is legal, but:

```cpp
class A {
    int f1();
};

class A {
    int f2();
};
```

is not.

