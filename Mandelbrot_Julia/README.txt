                                    Generare paralele de fractali folosind multimile Mandelbrot si Julia

        Prima data se citesc argumentele programului: fisierele de intrare si de iesire si 
    numarul de thread-uri. Apoi, are loc citirea datelor din fisierele Mandelbrot si Julia 
    si alocam memorie pentru cele doua rezultate corespunzatoare celor doua functii    
    run_julia si run_mandelbrot (result1 si result2).
        Functiile run_julia si run_mandelbrot le voi adauga intr-o functie f,
    pe care o folosesc in crearea thread-ului. Iau fiecare functie si o paralelizez. 
    Incepem cu functia Juliei. Pentru a castiga eficienta in timp, modificam primul for in asa
    fel incat sa se intample in mai putini pasi de la un start pana la end, care se obtin diferit
    in functie de numarul de thread-uri. Urmeaza o bariera care limiteaza aceasta paralelizare de 
    codul ce urmeaza. Imaginea pe care o obtinem este oglindita, asa ca trebuie transformat
    rezultatul din coordonate matematice in coordonate ecran. 
    For-ul care face treaba asta trebuie si el paralelizat la randul lui, afland un start si un end. 
    Vom scrie in fisier rezultatul obtinut. Analog se procedeaza si in cazul functie run_mandelbrot. 
    Pentru ca functia f sa aiba un singur parametru, am declarat global toate variabilele de care am nevoie.
    Dupa ce creez pthread-ul, ii dam join. La final, eliberez toata memoria consumata de cele doua
    matrici.