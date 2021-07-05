
#  stl 
Créée le mardi 11 décembre 2018


##  Tuple 


decl; tuple<int, time_t, int>
make_tuple(x,y,z) pour une instance de tuple
std::get<0>(tuple) => premier elt

##  deque (queue adaptor based on deque) 
allouée par chunck (zones contigues), les chuncks sont chainés

ajouter/supprimer debut ou fin.

##  map, set 
if faut queavoir fonciton de comparaison.

trié via des tree => Avantage insertion facile/

##  unirderd_map 
= hashed map

Il faus avoir une fonction de hash, par défaut std::hash<T>
