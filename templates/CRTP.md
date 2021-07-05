
#  CRTP 
Créée le lundi 12 avril 2021


```cpp
template <class T>  struct Base
{
    void interface()
    {
        // ...
        static_cast<T*>(this)->implementation();
        // ...
    }

};

struct Derived : Base<Derived>
{
    void implementation();
};
```
