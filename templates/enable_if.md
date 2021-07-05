
#  enable if 
Créée le dimanche 15 novembre 2020


Utilise SFINAE , equivalent à :
```cpp
template<bool B, class T = void>
struct enable_if {};
 
template<class T>
struct enable_if<true, T> { typedef T type; };
```

Pour loverload (veersion enable_if**_t **=> renvoie le type si true
```cpp
struct T {
    enum { int_t, float_t } type;
    template <typename Integer,
              std::enable_if_t<std::is_integral<Integer>::value, bool> = true => le = true peu important, juste pour initialiser
    >
    T(Integer) : type(int_t) {}
 
    template <typename Floating,
              std::enable_if_t<std::is_floating_point<Floating>::value, bool> = true
    >
    T(Floating) : type(float_t) {} // OK
};
```


Pour return type qui varie, on récupère le type:
```cpp
template<class T>
typename std::enable_if<std::is_trivially_default_constructible<T>::value>::type 
    construct(T*) 
{
    std::cout << "default constructing trivially default constructible T\n";
}
 
// same as above
template<class T>
typename std::enable_if<!std::is_trivially_default_constructible<T>::value>::type 
    construct(T* p) 
{
    std::cout << "default constructing non-trivially default constructible T\n";
    ::new(detail::voidify(p)) T;
```

}
