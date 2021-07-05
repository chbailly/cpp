Content-Type: text/x-zim-wiki
Wiki-Format: zim 0.4
Creation-Date: 2021-05-19T21:36:19+02:00

## 20 - Covariance- contravariance
Créée le mercredi 19 mai 2021

##  List not covariant (if writable)

list<cat> n'est pas une list<animals> car on peut ajouter un dog dans animals.

##  Return type can be covariant in C++ (override permitted) 

```cpp

struct AnimalBreeder {
	virtual Animal *produce() = 0;
};

struct CatBreeder : AnimalBreeder {
	**Cat** *produce() override { return new Cat; }
};

struct HorseBreeder : AnimalBreeder {
	**Horse** *produce() override { return new Horse; }
};
```