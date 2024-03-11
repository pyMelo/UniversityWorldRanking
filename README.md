# University World Ranking
Questo progetto si basa su un'analisi approfondita del dataset sul ranking delle università mondiale.

All'interno di esso troviamo vari tipi di classificazioni delle università come :
- **Cwur** (Central for World University Ranking): Si tratta di un'organizzazione indipendente con sede negli _Emirati Arabi uniti_.
Valuta le università in base alla qualità di insegnamento, qualità del corpo docente, impatto della ricerca e altro.
- **Shanghai** (ARWU - Academic Ranking of World Universities): Questa classifica è pubblicata dal _Center for World-Class Universities_ dell'Università Jia Tong di Shanghai.
Valuta in base ai premi Nobel, medaglie Fields (vinti dai membri del corpo docente), pubblicazioni accademice e altro.
- **Times** (Times Higher Education World University Rankings): Prodotta dalla rivista _Times Higher Education_, in collaborazione con Elsevier (casa editrice di pubblicazioni scientifiche).
Prende in considerazione vari fattori tra cui insegnamento, ricerca, citazioni, internazionalizzazione e impatto sulla società.


L'analisi del dataset si suddivide in tre princiapli studi:
- **1.** Analisi generale 
- **2.** Studio inerente alle università Italiane
- **3.** Incidenza donne


# :one:: Analisi Generale 
Cercheremo di ottenere dei dati per poter descrivere e analizzare il dataset nei vari studi effettuati.

## Head del dataset
```
cd
   world_rank                            institution         country  \
0           1                     Harvard University             USA   
1           2  Massachusetts Institute of Technology             USA   
2           3                    Stanford University             USA   
3           4                University of Cambridge  United Kingdom    
4           5     California Institute of Technology             USA   

   national_rank  quality_of_education  alumni_employment  quality_of_faculty  \
0              1                     7                  9                   1   
1              2                     9                 17                   3   
2              3                    17                 11                   5   
3              1                    10                 24                   4   
4              4                     2                 29                   7   

   publications  influence  citations  broad_impact  patents   score  year  
0             1          1          1           NaN        5  100.00  2012  
1            12          4          4           NaN        1   91.67  2012  
2             4          2          2           NaN       15   89.50  2012  
3            16         16         11           NaN       50   86.17  2012  
4            37         22         22           NaN       18   85.21  2012
```
