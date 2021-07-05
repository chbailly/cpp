
#  promise 
Créée le dimanche 11 avril 2021


```cpp
template <typename RandomIt>
int parallel_sum(RandomIt beg, RandomIt end)
{
    auto len = end - beg;
 
    RandomIt mid = beg + len/2;
    auto handle = std::async(std::launch::async,
                             parallel_sum<RandomIt>, mid, end);
    int sum = parallel_sum(beg, mid);
    return sum + handle.get();
}
```


**Verison thread (decompose promise + future):**
* promise permet de setter une valeur. On passe le promise au thread qui pourra setter la valeur
* Future (associé à promise) : promise.get_future() => on purra faire un get() en attendant de récupérer la valeur. 

 ''std::future<int> prodResult= prodPromise.get_future()''
''std::future<int> divResult= divPromise.get_future();''

''// calculate the result in a separat thread''
''std::thread prodThread(product,std::move(prodPromise),a,b);''
''Div div;''
''std::thread divThread(div,std::move(divPromise),a,b);''
''// get the result''
''std::cout << "20*10= " << prodResult.get() << std::endl;''
''std::cout << "20/10= " << divResult.get() << std::endl;''

  ''prodThread.join();''
''divThread.join();''

Les promise + thread peuvent être movés

**Version async** (comme exemple): promise et future crées implicitement. 

Policy:
* deferred
* async (thread si possible)
* any

**shared_future**: plusieurs thread peuvent attendre la valeur du promise.

exemple (avec le set on envoie une sorte de signal)

std::shared_future<void> ready_future(ready_promise.get_future())

 auto fun1 = [&, ready_future]() -> std::chrono::duration<double, std::milli>  {
	ready_future.wait();
	  ...
	}
	
auto fun2 = [&, ready_future]() -> std::chrono::duration<double, std::milli> {
	 ready_future.wait()
	...
 }

  auto result1 = std::async(std::launch::async, fun1);
  auto result2 = std::async(std::launch::async, fun2);

ready_promise.set_value();



