
#  pimpl 
Créée le dimanche 15 novembre 2020


Cacher l'implem des variables membres , improve compilation times
```cpp
private: 
	// Internal implementation class 
	class Impl; 
	 
	private:
	// Pointer to the internal implementation 
	unique_ptr<Impl> pimpl; 
	};
	
	Dans Impl on mettra toutes les données membre.
```

