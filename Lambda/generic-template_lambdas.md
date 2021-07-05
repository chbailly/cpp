
#  generic-template lambdas 
Créée le dimanche 11 avril 2021


* generic

const auto fooDouble = [](auto x, auto y) { /*...*/ };

* template =>+ flexibilité que version précédente.

auto foo = []<typename T>(std::vector<T> const& vec) {  ..}
