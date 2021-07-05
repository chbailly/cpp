
#  bind 
Créée le lundi 16 novembre 2020


EVITER , PREFERER LAMBDAS

```cpp
std::function<int(int)> f
_1 , _2 sont des placeholders, remplace 1er argument, 2sd argument, ...

int foo_2 (int x, int y) { return 9*x + y; }

std::function<int(int)> f1 = std::bind(foo_2, _1, 3) => _1 : 1er paramètre qui sera âssé à fontion
std::function<int(int)> f1 = std::bind(foo_2, 3, _1)
```
