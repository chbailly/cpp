
#  extended lifetime of const 
Créée le jeudi 20 mai 2021


```cpp
int return_int_ref() {
    int a {123};
    return a; // Returning a copy now, see return type
}

int main() {
    const int &int_ref {return_int_ref()}; // is now const

    std::cout << "Some stack overwriting intermediate print\n";

    std::cout << int_ref << '\n';
}
```

Règle
C++ feature to extend the life time of a temporary object to the life time of the const reference which refers to it.
