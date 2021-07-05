
#  3- expression SFINAE 
Créée le dimanche 15 novembre 2020

```cpp
template <class T> auto f(T t1, T t2) -> decltype(t1 + t2);
```

Sera choisi si t1 + t2 a du sens
