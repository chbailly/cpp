
#  pimpl 
Créée le dimanche 15 novembre 2020


Cacher l'implem des variables membres (pas les methodes) , improve compilation times

1. basic example (non template)
	1. hpp

	```cpp
	// api.hpp
	#include <memory>

	class API { 
	public:
		API();
		~API(); // Do not use define in header. also 'default'.
	private:
		class Impl;
		std::unique_ptr<Impl> pImpl;
	};
	```
	
	2. cpp

	```cpp
	class API::Impl {
	private:
		// hide member variables and methods
		std::vector<int> data;
	};

	API::API() : pImpl(std::make_unique<Impl>())
	{}
	API::~API() = default;
	```

3. example with template

	The client calls the contructor **and** destructor from client side (destructor can be called if exception occurs in constructor)

	1. hpp

	```cpp
	#include <memory>

	class API { 
	public:
		API();
		~API();

		template <typename T>
		explicit API(T value)
		{ // do something }

	private:
		class Impl;
		struct ImplDeleter // Add custom deleter of Impl
		{
			void operator()(Impl*);
		};

		std::unique_ptr<Impl, ImplDeleter> pImpl;
	};
	```

	2. cpp

	```cpp
	#include <memory>
	API::~API() = default;

	void API::ImplDeleter::operator()(Impl* ptr)
	{
		delete ptr;
	};
	```
