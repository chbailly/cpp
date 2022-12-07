
#  alias - alias template (using keyword) 
Créée le dimanche 15 novembre 2020


##  alias basic 


```cpp
typedef void (*FP)(int, const std::string&);      // typedef
using FP = void (*)(int, const std::string&);     // alias
```



##  alias template (traits sur type, value) 


pour implémenter des traits 
```cpp
template<class T> struct Alloc { }; => Permet 
```
**spécialisation**'' selon le type=> on implementera plusieurs fonctions''
```cpp
template<class T> using Vec = vector<T, Alloc<T>>; // type-id is vector<T, Alloc<T>>''
Vec<int> v;
```

Evite de faire avec typedef type

```cpp
template<typename T>                    
struct Vec {                     // is synonym for
  typedef std::vector<T, Alloc<T>> type; // std::list<T,
};
```
	  Vec<i>::type v

Plus simple:
	std::remove_const<T>::type           // C++11: const T → T
	​std::remove_const_t<T>! C++14

Meyers, Scott. Effective Modern C++: 42 Specific Ways to Improve Your Use of C++11 and C++14 . O'Reilly Media. Édition du Kindle. 

On peut faire la même chose pour des value traits.

template<typename T> constexpr T pi = T(3.14159265358979323846);
t''emplate<class T> using myClass = Class2<T, pi<T>>; ''

