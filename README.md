# cpp-memes

1. Change field in `const` method without `mutable`
```cpp
class Class
{
public:
    int Field;

    void Const() const
    {
        // Field = 5;
        const_cast<Class*>(this)->Field = 5;
    }
};
```

2.
```cpp
class A
{
};

class B : protected A
{
};

void Function()
{
    // A* a = new B;
    A* a = reinterpret_cast<A*>(new B);
}
```

3.
```cpp
class Class
{
public:
    void Method()
    {
        static int a = 1;
        std::cout << "Class::Method " << a << "\n";
        a++;
    }
};

int Function()
{
    Class* c = new Class;
    delete c;

    c->Method();
    c->Method();

    return 0;
}
```
