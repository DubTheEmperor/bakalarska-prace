# Predikce cen bytů v ČR pomocí strojového učení

###### Tento projekt se zabývá analýzou a predikcí vývoje cen bytů v jednotlivých krajích České republiky. K predikci jsou využity pokročilé modely strojového učení v kombinaci s automatickým laděním hyperparametrů.





### Vlastnosti:

* ###### Time Series Cross-Validation: Evaluace modelů na časových řadách pomocí knihovny mlforecast (Nixtla).



* ###### Hyperparameter Tuning: Integrace knihovny Optuna pro optimalizaci parametrů modelů XGBoost a Random Forest.



* ###### Multimodální přístup: Srovnání nelineárních modelů (XGBoost, RF) s lineární regresí a statistickými metodami (Naive).



* ###### Vizualizace: Dashboardy vytvořené v Plotly pro porovnání predikcí s realitou.





### Použité technologie:

* ###### Jazyk: Python 3.10+



* ###### Forecasting framework: mlforecast, statsforecast (Nixtla)



* ###### Optimalizace: optuna



* ###### Machine Learning: scikit-learn



* ###### Analýza a vizualizace: pandas, seaborn, plotly





### Struktura projektu:

* ###### bakalarska\_prace\_projekt.ipynb - Jupyter Notebook s kompletní analýzou



* ###### data/ - Složka obsahující dataset (dataset\_ml.csv)





###### Pro nainstalování potřebných knihoven: pip install -r requirements.txt





### Metodika a zpracování dat:

###### Cílem práce je predikce vývoje cen bytů (v Kč/m²) v jednotlivých krajích České republiky. Bylo vycházeno z kvartálních dat za období let 2019 až 2024.

###### Metodika zahrnuje:

###### 

* ###### Výběr modelů: Pro testování byla zvolena kombinace statistických metod (Naive, Moving average) a modelů strojového učení (Linear Regression, XGBoost, Random Forest). K implementaci byly využity knihovny MLForecast a StatsForecast.

###### 

* ###### Optimalizaci: U modelů strojového učení bylo provedeno automatizované ladění hyperparametrů pomocí frameworku Optuna, pro dosažení co nejvyšší přesnosti předpovědi.





### Průzkumná analýza:

###### Na začátku práce byla provedena analýza dat pomocí vizualizací, které nám o trhu říkají následující:



* ###### Časová řada vývoje cen: Tento graf dokumentuje ukazuje vzestupný trend cen ve všech krajích ČR a ukazuje vysokou setrvačnost trhu i přes vnější vlivy (např. pandemii). Zatímco Praha a Jihomoravský kraj vykazují nejstrmější nárůst, u ostatních regionů je vývoj pozvolnější.



* ###### Boxplot (Rozdělení cen podle krajů): Tento graf slouží k porovnání cenových hladin v regionech. Jasně ukazuje rozdíly mezi Prahou a zbytkem republiky, ale také variabilitu cen v čase. Z rozptylu hodnot je patrné, že ceny v Praze jsou mnohem více volatilní a vykazují větší cenové skoky než například v Karlovarském kraji, kde je vývoj cen stabilnější a predikovatelnější.



* ###### Heatmapa (Korelace cenových změn): Heatmapa je vytvořena z diferencovaných dat (změn cen mezi kvartály). Ukazuje, jak moc jsou trhy v jednotlivých krajích propojené. Vysoká korelace (tmavší barva) značí, že kraje na sebe vzájemně reagují – pokud vzroste cena v jednom, s vysokou pravděpodobností vzroste i v druhém. To potvrzuje, že realitní trh v ČR funguje jako provázaný celek a různé kraje na sebe mají různou závislost.





### Analýza výsledků:

###### Při hodnocení modelů byla jako metrika zvolena MAE (mean absolute error). Je důležité podotknout, že MAE byla počítána pro horizont jednoho období (1 kvartál), zatímco finální predikce je vytvořena na 4 období dopředu (tedy na celý rok 2025). Chyba tedy bude pro 2.-4. kvartál pravděpodobně vyšší.



###### Z výsledků vyplývá toto pořadí úspěšnosti:

###### 

* ###### Linear Regression a Naive model: Tyto modely dosáhly v testování nejnižší chyby. Je to dáno tím, že na krátkém horizontu (jeden kvartál) mají ceny nemovitostí silnou setrvačnost a rostou lineárně.

###### 

* ###### XGBoost a Random Forest: Tyto pokročilejší modely dosáhly velmi podobné přesnosti s jen minimálním odstupem. I když jsou sofistikovanější, jejich síla se projevuje spíše při zachycení složitějších trendů a nelinearit. Pro krátkodobý odhad o jeden kvartál jsou o něco méně přesné než lineární trend, ale pro dlouhodobější předpověď jsou robustnější, protože se nenechají tak snadno ovlivnit náhodným šumem v datech.
