
#  exceptions 
Créée le dimanche 15 novembre 2020


##  Contructor/destructor 
	1.Pas de'exception dans destructor !!! => undefined behavoir

	2; Exceptions dans contructor OK


##  noexcept 


''int f(int x) noexcept;''

move contrcutor must be no except !!!

If not when a vector<T> is resized it will use copy instead of move !!!
