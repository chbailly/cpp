
#  type traits 
Créée le mardi 06 avril 2021


2 types: 

* value 

std::is_signed<T>::value (c+11) => std::is_signed**_v**<T>

remarque std::signed<T> derive de true_tpe ou fals_type (cf tag dispatching)

* type

Transforme un type

std::remove_const<T>::type;  (C++11)   std::remove_const_t<T>; (C++14)
