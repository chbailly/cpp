
#  2- enable if 
Créée le dimanche 15 novembre 2020


Voir section [[enable if]]

C++11:
```cpp
template <class T>
typename std::enable_if<std::is_arithmetic<T>::value, T>::type 
foo(T t) {
  std::cout << "foo<arithmetic T>\n";
  return t;
}
```

C++14:
```cpp
template <class T>
typename std::enable_if_t<std::is_arithmetic_v<T>, T> // << shorter!
foo(T t) {
  std::cout << "foo<arithmetic T>\n";
  return t;
}
```
