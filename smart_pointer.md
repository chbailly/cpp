
#  smart pointer 
Créée le dimanche 15 novembre 2020


##  std::unique_ptr<T> 


##  std::shared_pt<T> 


##  std::weak_ptr<T> 


Initialisés à partir dun shared_ptr SANS INCREMENTER COMPTEUR

avec lock, permet de transformer en shared_ptr (si existe encore)

```cpp
{
auto objPtr = cache[id].lock();
if (!objPtr) {
```
	   ...
	  }

Utile pour pattern observer, notifier observer qui n'existent peut être plu...
Pour éviter cycles aussi
