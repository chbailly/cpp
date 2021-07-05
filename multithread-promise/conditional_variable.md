
#  conditional variable 
Créée le dimanche 11 avril 2021



condition_variable cv;


std::thread{[&cv, &go, &m, i]() {
		unique_lock<mutex> verrou{m};
        
		cv.wait(verrou, [&]() { return go; }); => run the function when notified !!
		cout << "Youppi, thread " << i << '!' << endl;
}

cv.notify_all();


Important ! on revérifie la condition dans la lmambda passé en paramètre.

