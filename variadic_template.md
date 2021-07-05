
#  variadic template 
Créée le jeudi 20 mai 2021


```cpp
auto SumCpp11(){
    return 0;
}

template<typename T1, typename... T>
auto SumCpp11(T1 s, T... ts){
    return s + SumCpp11(ts...);
}
```


Avec C++17  (Fold expressions)

```cpp
template<typename ...Args> auto sum2(Args ...args) 
{ 
    return (args + ...);
}
```
