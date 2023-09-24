
#  variant 
Créée le dimanche 09 mai 2021



##  Avec class Visitor 

```cpp
using var_t = std::variant<int, const char*>; // (1)

struct Print { // (2)
	void operator() (int i) {
		printf("%d\n", i);
	}

	void operator () (const char* str) {
		puts(str);
	}
};
var_t v;
std::visit(Print(), v);
```

##  Avec mot clef overloaded: 


int main() {
	std::vector<var_t> vars = {1, 2, "Hello, World!"};

	for (auto& v : vars) {
		std::visit(overloaded {  // (3)
			[](int i) { printf("%d\n", i); },
			[](const char* str) { puts(str); }
		}, v);
	}


##  std::monostate() 

C'est le type sans résultat: exemple traiter solution equation 2sd degré.
return std::monostate() si pas de solution

```cpp
void printQuadResult(const var_roots& v){
	std::visit(overloaded {
			[](const std::pair<double,double>& arg) { 
						std::cout << "2 roots found: " 
								  << arg.first << " " << arg.second << '\n'; },
			[](double arg) { std::cout << "1 root found: " << arg << '\n'; }, 
			[](**std::monostate**) { std::cout << "No real roots found.\n"; },
	}, v);
}
```
