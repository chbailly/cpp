
#  4- tag dispatching 
Créée le dimanche 15 novembre 2020


```cpp
template <typename T>
int get_int_value_impl(T t, std::true_type) {
    return static_cast<int>(t+0.5f);
}

template <typename T>
int get_int_value_impl(T t, std::false_type) {
    return static_cast<int>(t);
}

template <typename T>
int get_int_value(T t) {
    return get_int_value_impl(t, std::is_floating_point<T>{});
}
```
