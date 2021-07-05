
#  emplace 
Créée le dimanche 15 novembre 2020


```cpp
class vector {
public:
  …
  void push_back(const T& x);                // insert lvalue
  void push_back(T&& x);                     // insert rvalue
  …
};
```


```cpp
std::vector<std::string> vs;         // container of std::string
vs.push_back("xyzzy");
```


C'est la même chose que:  ''vs.push_back(std::string("xyzzy"));''

Il est préférable d'utilsier ''vs.emplace_back("xyyyz") => constructor on place''
