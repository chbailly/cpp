
#  constexpr 
Créée le dimanche 15 novembre 2020


constexpr != const.

constexpr signifie que varibale peut être déterminée )à la compilation
const pas nécessaireement à compil

Une fonction constexpr n'est pas forcément constexpr, fonctionnera aussi si appelée avec varibales runtime

###  std::array<T, size> 


On ne peut pas utiliser std::vector mais std::array dans une constrexpr

```cpp
constexpr auto numConds = 5;                
std::array<int, pow(3, numConds)> results;
```


 
