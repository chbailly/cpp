
#  tag dispatch 
Créée le dimanche 15 novembre 2020


template <bool> 
struct UseIteratorSemantics
{};

//...
void construct (Iterator first, Iterator lst, UseIteratorSemantic<true>)

construct(first, last, UseIteratorSemantics<true>{});

On peut uiliser plusieurs tag comme std::true_type , std::false_type.
