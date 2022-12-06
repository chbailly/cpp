
#  policy traits 
Créée le lundi 12 avril 2021

```cpp

template <typename T>
struct Addition
{
        static void Accumuler(T& Resultat, const T& Valeur)
        {
            Resultat += Valeur;
        }
    };
] 
```
On peut définir l'addition pour chaque type. L'algo Accumulation va utiliser l'operation associée au type

```cpp
 template <typename T, typename Operation>
T Accumulation(const T* Debut, const T* Fin)
{
  T Resultat = 0;
  for ( ; Debut != Fin; ++Debut)
      Operation::Accumuler(Resultat, *Debut);
    
   return Resultat;
 }
 ```

UN autre exemple si on a une classe S qu'on veut utilsier dans une map en tant que clé:
```cpp
template<>
struct std::hash<S>
{
    std::size_t operator()(S const& s) const noexcept
    {
        std::size_t h1 = std::hash<std::string>{}(s.first_name);
        std::size_t h2 = std::hash<std::string>{}(s.last_name);
        return h1 ^ (h2 << 1); // or use boost::hash_combine
    }
};
```


On va pouvoir defintir un comportement different pour differents types
