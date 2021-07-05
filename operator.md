
#  operator 
Créée le lundi 16 novembre 2020



Inside class:
```cpp
Vector2 operator+( const Vector2 & other )
    {
        Vector2 ans ;
        ans.x = x + other.x ;
        ans.y = y + other.y ;
        return ans ;''
    }
```

Outside (en declarant friend function de la class)
```cpp
Vector2 operator+( const Vector2& v1, const Vector2& v2 )
{
    Vector2 ans ;
    ans.x = v1.x + v2.x ;
    ans.y = v1.y + v2.y ;
    return ans ;
}
```

Difference; 
Do you want conversions to be performed on the left-hand side parameter of an operator?

Exemple:
string b = "foo" + a;

"foo" sera automatiquement convertit en string avec la free funciton
