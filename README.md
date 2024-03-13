# University World Ranking
<div style="text-align:center;">
    <img src="/images/_c95b8779-e6f0-4e51-8cf5-0b7fffe33b33-removebg-preview.png" alt="logo">
</div>

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


## Top 5 unviersità in Cwur dal 2012 al 2015
![1_posizione-mondiale-top5_cwur.png](/images/1_posizione-mondiale-top5_cwur.png)
Harvard 1° in classifica per tutto il corso degli anni. C'era da aspettarselo
## BoxPlot metriche in Cwur
Per vedere come si distinguono in alcuni paesi le metriche abbiamo usato il BoxPlot per farci un'idea.
![1_ranking_boxplot_cwur.png](/images/1_ranking_boxplot_cwur.png)
Notiamo delle anomalie per le università negli USA, la maggior parte peccano in alcune metriche, però ci sono dei casi che si presentano nelle prime posizioni.

## SpiderWeb Top 5 università in Shanghai
![1_topuni_spiderwab_shanghaidata.png](/images/1_topuni_spiderwab_shanghaidata.png)
Harvard ha quasi tutte le metriche di valutazione al massimo.

## BoxPlot delle metriche in ShanghaiData
Questo BoxPlot invece della posizione in classifica si utilizza lo score.
![1_rankingmetrics_boxplot_shanghaidata.png](/images/1_rankingmetrics_boxplot_shanghaidata.png)

## Sistemando il Times
Nel csv del Times sono presenti dei valori NaN che verranno sostituiti con la media in corrispettivo alla metrica.
Inoltre abbiamo il peso delle varie metriche, è stato effettuato un ricalcolo del total_score.
![metricsweight_dataset.png](/images/metricsweight_dataset.png)

### Differenza tra :
- total_score originale
```
University Original Total Score  \
0                        Harvard University                 96.1   
1        California Institute of Technology                 96.0   
2     Massachusetts Institute of Technology                 95.6  
```
- total_score stimato
```
      Modified Total Score  
0                     95.5  
1                     94.9  
2                     95.1 
```

# :two:: Studio Università Italiane

## Ranking università italane vs USA
![2_rankinguni_itavsUsa.png](/images/2_rankinguni_itavsUsa.png)

## Università Italiane presente in tutti e 3 gli studi
Shanghai Dataset
```
Italian Universities - Shanghai Data (Italian universities do not have scores):
                              university_name world_rank  total_score
141                       University of Milan    101-152          NaN
143                        University of Pisa    101-152          NaN
192                       University of Padua    153-202          NaN
197                       University of Turin    153-202          NaN
256                     University of Bologna    203-300          NaN
263                    University of Florence    203-300          NaN
```
Times Dataset
```
Italian Universities - Times Data:
                              university_name world_rank  total_score
441                     University of Bologna    226-250         35.5
444                       University of Milan    226-250         37.3
445               University of Milan-Bicocca    226-250         37.3
447                       University of Padua    226-250         35.3
448                     University of Trieste    226-250         36.1
499                      University of Trento    276-300         33.0
519           Polytechnic University of Milan    301-350         26.9
520               Sapienza University of Rome    301-350         29.0
528                     University of Ferrara    301-350         30.4
```
Cwur Dataset
```
Italian Universities - CWUR Data:
                                           institution  world_rank  score
76                         Sapienza University of Rome          77  46.34
380                                University of Milan         181  48.48
383                                University of Padua         184  48.40
418                              University of Bologna         219  47.59
430                                University of Turin         231  47.40
465                             University of Florence         266  46.80
471                   University of Naples Federico II         272  46.67
507                                 University of Pisa         308  46.30
```
## SpiderWeb Top 5 Italiane vs Top 5 WorldWide (Times)
![2_differencetop5ita_top5usa.png](/images/2_differencetop5ita_top5usa.png)

![2_differentopITA.png](/images/2_differentopITA.png)


## Andamento della classifica Italiana durante gli anni
Vediamo come le top università italaine sono presentate nella classifica.
Avendo 3 dataset/studi diversi che utilizzano metriche totalmente diverse abbiamo un'andamento temporale abbastanza distinto.

### Cwur Data
![2.4_andamento_cwurdata.png](/images/2.4_andamento_cwurdata.png)

### Times Data
![2.4_andamento_timesData.png](/images/2.4_andamento_timesData.png)

## Shanghai Data
![2.4_andamento_shanghaidata.png](/images/2.4_andamento_shanghaidata.png)


E' stato fatto un piccolo "merge" con un altro CSV, aggiungendo la tabella "country" al csv princiapale associato alle università di quel posto, dato che non erano presenti i Paesi delle università.


## Dove peccano le università Italiane?
Un'analisi a cui tenevo era vedere in che settore/ambito fossimo scadenti.

Questa rappresentazione è data dal posto in classifica
### Ranking in Cwur

![2_worsemetrics_ita_cwur.png](/images/2_worsemetrics_ita_cwur.png)


In questi boxplot notiamo che la sezione brevetti è abbastanza debole anche se abbiamo degli outliers che spiccano verso le prime posizioni.

### Score in Times


Questa rappresentazione è data dal punteggio.


![2_worstmetrics_ita_times.png](/images/2_worstmetrics_ita_times.png)


La metrica teaching e research sono abbastanza basse, proviamo a cambiare un qualcosa.

Questo ci dice che l'insegnamento nelle università italiane non è delle migliori, anche se avrei qualcosa da ridire.
```
```
## E se cambiassimo una qualche metrica?
Abbiamo preso la metrica peggiore in Times nelle università italiane e le abbiamo sostituite con il valore "99" per vedere quanto effettivamente cambiasse nella classifica.

**Prima**
```
                             university_name country world_rank  total_score
1915         Scuola Normale Superiore di Pisa   Italy        112         57.1
1983               Scuola Superiore Sant’Anna   Italy       =180         50.2
2000                     University of Trento   Italy        198         49.1
2005                    University of Bologna   Italy    201-250         46.4
2035          Polytechnic University of Milan   Italy    201-250         46.7
2038              Sapienza University of Rome   Italy    201-250         44.5
2124                      University of Milan   Italy    301-350         39.7
2125              University of Milan-Bicocca   Italy    301-350         38.4
2128         University of Naples Federico II   Italy    301-350         39.0
2136                      University of Padua   Italy    301-350         40.5
2137                      University of Pavia   Italy    301-350         38.6
```
**Dopo**
```
                            university_name country  world_rank  total_score
45          Scuola Normale Superiore di Pisa   Italy          46         70.6
51                      University of Trento   Italy          52         69.6
60           Polytechnic University of Milan   Italy          61         67.4
61                Scuola Superiore Sant’Anna   Italy          62         67.2
73                     University of Bologna   Italy          73         64.3
77               Sapienza University of Rome   Italy          78         62.8
78                       University of Padua   Italy          79         62.5
84                     University of Trieste   Italy          85         61.8
87          University of Naples Federico II   Italy          88         61.3
90                    University of Florence   Italy          91         61.2
```
Notiamo, ovviamente, una notevole differenza sia nella posizione in classifica sia al punteggio.

Nonostante abbiamo la metrica dell'insegnamento abbastanza 
## Ratio studenti Internazionali Top 3 USA vs Top 3 Italiane


![2.8_ratio_internazionale.png](/images/2.8_ratio_internazionale.png)

## Ratio studentesse donne Top 3 USA vs Top 3 Italiane
![2.7_ratio_studentesse.png](/images/2.7_ratio_studentesse.png)



Da qui otteniamo che una delle migliori università nel dataset del Times nell'anno del 2016 ha almeno più della metà di donne presenti.


# 3️⃣ Incidenza del mondo femminile nelle università (Times)
Abbiamo convertito la colonna female_male ratio in "female_ratio" e abbiamo fatto un plot per vedere la correlazione delle donne sulle metriche :
- world rank
- ranking

**Correlazione con world rank**
![3_correlation_females_worldrnak.png](/images/3_correlation_females_worldrnak.png)

**Correlazione con total score**
![3_correlatioTWO.png](/images/3_correlatioTWO.png)


## Effettuiamo una Regressione Lineare
Cerchiamo di vedere se è presente una correlazione tra la percentuale di donne e qualche metrica.


![3_linearregression.png](/images/3_linearregression.png)

Rimuovendo gli outliers riusciamo a trovare un valore di R-Squared:

- Da 0.73 a 0.63 per income
- Da 0.29 a 0.32 per citations
  
## Predizione ranking mondiale e total score

### Predizione world rank delle università utilizzando le seguenti feature:

- female_percentage
- teaching
- international
- research
- citations
- income


```
RMSE: 78.22348254847141
Predizione di 5 università prese a caso prendendo come parametri : 
female_percentage,teaching,international,research,citations,income :

Università: Isfahan University of Technology
World Rank Iniziale: 534
World Rank Predetto: 425.9864026934038
---
Università: Massachusetts Institute of Technology
World Rank Iniziale: 7
World Rank Predetto: -179.15766566460093
---
Università: University of Minho
World Rank Iniziale: 555
World Rank Predetto: 439.47330550774547
---
Università: Oregon State University
World Rank Iniziale: 285
World Rank Predetto: 313.71741551697244
---
Università: Massachusetts Institute of Technology
World Rank Iniziale: 5
World Rank Predetto: -185.91857603259461
---
```

### Predizione world rank attraverso le feature :
- female_percentage
- Italy (valore booleano 0 o 1)


```
RMSE su tutto il set di test: 176.87822162112585
RMSE solo per le università italiane: 88.49229385575435

Predizione di 5 università italiane prese a caso utilizzando le features 'female_percentage' e 'Italy':
Università: University of Ferrara
World Rank Iniziale: 382
World Rank Predetto: 327.8474977166485
---
Università: University of Trento
World Rank Iniziale: 273
World Rank Predetto: 327.94663273831486
---
Università: University of Trieste
World Rank Iniziale: 221
World Rank Predetto: 327.8474977166485
---
Università: University of Milan-Bicocca
World Rank Iniziale: 323
World Rank Predetto: 327.7681896993154
---
Università: University of Catania
World Rank Iniziale: 515
World Rank Predetto: 327.7483626949822
---
```

Abbiamo ottenuto due RMSE diversi.


### Matrice di correlazione

![3_matrixcorrelation_females.png](/images/3_matrixcorrelation_females.png)


Notiamo che non è presente nessuna severa correlazione con la *percentuale di donne*, proviamo ad indagare se esiste una causa-effetto con *international* e *citations*.



### Predizione Total_Score attraverso la feature: 

- Female percentage



```
RMSE: 15.983725130323005
Prediction for 5 randomly selected universities using the feature 'female_percentage' and 'total_score'
female_percentage
University: University of Modena and Reggio Emilia
Total Score Initial: 27.0
Total Score Predicted: 44.92990271211278
---
University: Montpellier University
Total Score Initial: 39.3
Total Score Predicted: 45.15031774253137
---
University: Johannes Kepler University of Linz
Total Score Initial: 31.3
Total Score Predicted: 45.37073277294997
---
University: University of Michigan
Total Score Initial: 82.6
Total Score Predicted: 45.37073277294997
---
University: University of Canterbury
Total Score Initial: 37.3
Total Score Predicted: 45.15031774253137
---
```

Otteniamo un RMSE abbastanza basso, vediamo se riusciamo a trovare una causa-effetto aggiungendo la feature "international"
