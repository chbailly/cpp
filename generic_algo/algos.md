
#  algos 
Créée le lundi 12 avril 2021


###  Map : std::transform 


C'est l'équivalent de map avec output iterator
```cpp
std::vector<std::string> names = {"hi", "test", "foo"};
std::vector<std::size_t> name_sizes;

std::transform(names.begin(), names.end(), std::back_inserter(name_sizes), [](const std::string& name) { return name.size();});
```


##  Filter: 


###  copy_if: 


```cpp
std::vector<int> foo = {25,15,5,-5,-15};
std::vector<int> bar;

// copy only positive numbers:
std::copy_if (foo.begin(), foo.end(), std::back_inserter(bar), [](int i){return i>=0;} );
```


###  More effictent: std::remove_if 
Mets les éléments qui ne vérifient pas la condition au début et retourne l'itérateur de fin 


##  Find 


std::find
std::find_if
std::findçfirstçof (rechercher parmis une liste de possibilités=

##  Join 
```cpp

std::vector<int> vec{ -1, 4, 70};
std::copy( vec.begin(), vec.end(), std::ostream_iterator<int>( std::cout, " "));
```


