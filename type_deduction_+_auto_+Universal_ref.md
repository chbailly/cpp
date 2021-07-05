
#  type deduction + auto + Universal ref 
Créée le dimanche 15 novembre 2020


Template
3 cas :
* Si reference, on enleve la reference et on match
* Si uiversal reference, pareil si rvalue. Sion lvalue reference
* Si T: on enleve la reference et le const et volatile

auto foncitonne pareil pourr tpe deduction

exception:  auto x = {3, 4} utilse std::initializer_list

```cpp
auto authAndAccess(Container& c, Index i)       // requires
{
  authenticateUser();
  return c[i];
}
```


mais c[i] retourne une référence et auto va **perdre la référecence** (rule 3 type deduction)

Solutions:
* ''auto authAndAccess(Container& c, Index i) -> decltype c[i])'' => fonctionnera mieux
* **decltype(auto) AuthAndAccess(Container& c, Index i) => mettre cette version**


Encore mieux **(universal reference**):
```cpp
template<typename Container, typename Index>       // final
decltype(auto)  authAndAccess(Container&& c, Index i)              // version
{
  authenticateUser();
  return std::forward<Container>(c)[i];
}
```


Autre utilisation (pour **ne pas perdre le const**:
```cpp
const Widget& cw = w;
decltype(auto) w2 =  cw;
```


Visauliser type T d'un template:  ''typeid(T).name()''


