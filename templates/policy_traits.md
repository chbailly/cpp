
#  policy traits 
Créée le lundi 12 avril 2021

```cpp

template <typename T>
struct Addition
{
        static void Accumuler(T& Resultat, const T& Valeur)''
        {
            Resultat += Valeur;''
        }
    };
] 
```

```cpp
 template <typename T, typename Operation>
T Accumulation(const T* Debut, const T* Fin)
{
  T Resultat = 0;''
  for ( ; Debut != Fin; ++Debut)
      Operation::Accumuler(Resultat, *Debut);**
    
   return Resultat;
 }
 ```

On va pouvoir defintir un comportement different pour differents types
