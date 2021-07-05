
#  parallel implem 
Créée le dimanche 09 mai 2021

```cpp
std::for_each(
		 std::execution::par,
         std::begin(result),
         std::end(result),
         [divisor](T& val) {  // copies are safer, and the resulting                                   //code will be as quick.''
              // modifies value in place
              val /= divisor;''
          });
```

fonctionne aussi pour std::sort, std::tranform,...


Type de parallelistaion:
* std::execution::seq
* std::execution::par
* std::execution::par_unseq => autorise vectorisation.. Chaque iteration doit être independante (pas de lock par exemple)

