# Predikce cen bytů v ČR pomocí strojového učení

###### Tento projekt se zabývá analýzou a predikcí vývoje cen bytů v jednotlivých krajích České republiky. K predikci jsou využity pokročilé modely strojového učení v kombinaci s automatickým laděním hyperparametrů.





### Vlastnosti:

* ###### Time Series Cross-Validation: Evaluace modelů na časových řadách pomocí knihovny mlforecast (Nixtla).



* ###### Hyperparameter Tuning: Integrace knihovny Optuna pro optimalizaci parametrů modelů XGBoost a Random Forest.



* ###### Multimodální přístup: Srovnání nelineárních modelů (XGBoost, RF) s lineární regresí a statistickými metodami (Naive, ARIMA, ETS).



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

