
#  1 - SFINAE 
Créée le dimanche 15 novembre 2020


```cpp
struct Bar {
    typedef double internalType;  
};

template <typename T>  
typename T::internalType foo(const T& t) {  
    cout << "foo<T>\n"; 
    return 0; 
}

int foo(int i) { cout << "foo(int)\n"; return 0; } // => overload #2**

int main() {
    foo(0); // overload #2''
}

```

