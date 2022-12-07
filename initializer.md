
#  initializer 
Créée le dimanche 15 novembre 2020


Les accolades sont les initialisers universels
''Widget w{10, 5.0};''

Evite conversions impkicit + rigoureux.
	''int i = 4.5;'' => fonctionne
	''int i{5}'' ne foncitonne pas


##  iniitializer_list 


```cpp
Point::Point(std::initializer_list<int> list)
{
    if(list.size() == 3)
    {
        std::initializer_list<int>::iterator it = list.begin();
        mX = *it++;
        mY = *it++;
        mZ = *it;
    }
    std::cout << "Point:: Initializer_list<int>Constructor\n";
}
```
 Point P{ 5, 6 }
 it will always give preference to constructor with std::initializer_list<int>



Links:  [links.md](links.md) 
