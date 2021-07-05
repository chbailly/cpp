
#  5- Concept 
Créée le dimanche 15 novembre 2020


##  defining the concept: 


```cpp
template<typename T>
concept EqualityComparable = requires(T a, T b) {
    { a == b } -> std::same_as<bool>;
    { a != b } -> std::same_as<bool>;
};
```



explication;
* { a == b } doit etre valide
* test sur le  results  : std::same_as<bool>

##  Utilisation 


```cpp
template <EqualityComparable T>
void f(const T&);
```


##  Autre exemple 


defines the concept:
```cpp
template <class T>
concept SignedIntegral = std::is_integral_v<T> && std::is_signed_v<T>;
```


use:
```cpp
template <SignedIntegral T>
void signedIntsOnly(T val) { }
```
