
#  volatile vs atomic 
Créée le lundi 16 novembre 2020


##  Atomic (concurrency) 


* No reordring

```cpp
std::atomic<bool> valAvailable(false);
auto imptValue = computeImportantValue();  // compute value
valAvailable = true;
```


If valAvailable is Tur, All thread will see the imptValue

* Atomic operation

++i
--i

##  Volatile 


Indique juste memoire speciale
