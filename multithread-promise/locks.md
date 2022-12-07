
#  locks 
Créée le dimanche 11 avril 2021


* scoped_lock

```cpp
{
    // safely locked as if using std::lock
    std::scoped_lock<std::mutex, std::mutex> lock(mutex1, mutex2);     
}
```
Remarque: lock_guard n'est plus utilisé

* shared_mutex

Peu t etre locké (par writer, exclsif) ou shared_locké (plusierus reader
```cpp
  std::shared_mutex mutex_;

  unsigned int get() const {
	std::shared_lock lock(mutex_);
	return value_;
  }

  // Only one thread/writer can increment/write the counter's value.
  void increment() {
	std::unique_lock lock(mutex_);
	value_++;
  }
```
