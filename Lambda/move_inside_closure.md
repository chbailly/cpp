
#  move inside closure 
Créée le lundi 16 novembre 2020


```cpp
auto pw = std::make_unique<Widget>();   // create Widget; see
auto func = [pw = std::move(pw)]               // init data mbr
```

Ou initialisé directment:


```cpp
auto func = [pw = std::make_unique<Widget>()] { implem..}
```

