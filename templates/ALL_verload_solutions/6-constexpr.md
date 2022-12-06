
#  6-constexpr , constrexpr if
Créée le mardi 06 avril 2021

constexpr if permet de supprimer des conditions de branche à la compilation

```cpp
void algorithm_signed  (int i)      { /*...*/ } 
void algorithm_unsigned(unsigned u) { /*...*/ } 


template <typename T>
void algorithm(T t)
{
    if constexpr(std::is_signed<T>::value)
        algorithm_signed(t);
    else
    if constexpr (std::is_unsigned<T>::value)
        algorithm_unsigned(t);
    else
        static_assert(std::is_signed<T>::value || std::is_unsigned<T>::value, "Must be signed or unsigned!");
}
```
