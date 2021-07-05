
#  move + forward 
Créée le dimanche 15 novembre 2020


Voir universal reference

Ne pas confondre rvalue reference et  universal reference
auto &&r& = r2
template <T> void f(T && param)

Va binder soit une lvalue reference soit unre rvalue.

Utiliser std::move avec des rvalue reference et std::forward sur des universal reference.

std::move : cast en rvalue reference
std::forward: cast conditionnel en lvalue reference ou rvalue refernce

Attention:
Move requests on const objects are silently transformed into copy operations.
