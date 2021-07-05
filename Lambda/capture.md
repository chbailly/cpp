
#  capture 
Créée le dimanche 15 novembre 2020


[=] => cature all ocal by value + this
[&]: local variables par reference + this
[i] caputre i
[&i] capture i par ref

ATTENTION [[CAPTURE]] DATA MEMBER (divisor dans exemple)

```cpp
void Widget::addFilter() const
{
  filters.emplace_back(
    [=](int value) { return value % divisor == 0; }
  );
}
```

le = capture this, pas divisor !! Donc divisor  ⇔ this->divisor et lifetime depend de this.

Pour capturer divisor;
```cpp
void Widget::addFilter() const
{
  auto divisorCopy = divisor;                // copy data member

  filters.emplace_back(
    [divisorCopy](int value)                 // capture the copy
    { return value % divisorCopy == 0; }     // use the copy
  );
```


