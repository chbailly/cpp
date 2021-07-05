Content-Type: text/x-zim-wiki
Wiki-Format: zim 0.4
Creation-Date: 2021-05-19T23:06:36+02:00

# 30 - Test-And-Set, memory barrier, lock free 
Créée le mercredi 19 mai 2021

Retourne true ou flase si a updaté la valeur.

Teste si la valeur n'a pas été changé (égale) et set la nouvelle valeur si c'est le cas

## fonction cas

```cpp
function cas(p: pointer to int, old: int, new: int) is
    if *p ≠ old
        return false

    *p ← new
    
    return true
```


##  Adder atomic

**Boucle tant que n'a pas mis à jour**

```cpp
function add(p: pointer to int, a: int) returns int
    done ← false

    while not done
        value ← *p  // Even this operation doesn't need to be atomic.
        done ← cas(p, value, value + a)
    
    return value + a
```


## Barrière de mémoire 

Garde l'ordre d'exécution avant [[/après]] atomic
