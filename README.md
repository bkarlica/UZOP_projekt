# UZOP – Uvod u znanost o podacima: projekt

Projekt iz kolegija Uvod u znanost o podacima (UZOP), izrađen u Pythonu (Jupyter Notebook). Sastoji se od tri dijela: pripreme i analize jednog skupa podataka te replikacije i poboljšanja rezultata iz znanstvenog članka.

## Sadržaj

* **Prvi dio** (`projekt-prvi-dio_Budimir.ipynb`) – priprema podataka na skupu *Life Expectancy* (očekivani životni vijek po državama): uklanjanje konstantnih i monotonih stupaca, obrada nedostajućih vrijednosti, kodiranje kategoričkih značajki (One-Hot i Label encoder), deskriptivna statistika, normalizacija i vizualizacija (histogram, pitni, kutijasti graf i graf raspršenja).
* **Drugi dio** (`projekt-drugi-dio_Budimir.ipynb`) – priprema podataka iz članka *Implementation of Machine Learning Model to Predict Heart Failure Disease*: skup *heart_disease_uci.csv* sveden je na podatke bolnice Cleveland, uklonjene su konstantne značajke, nedostajuće vrijednosti i stršeće vrijednosti, kategoričke značajke su kodirane (kao u članku), a podaci standardizirani. Uključena je analiza korelacija i vizualizacije u odnosu na ciljnu varijablu `num`. Rezultat su CSV datoteke spremne za treniranje.
* **Treći dio** (`projekt-treci-dio.ipynb`) – replikacija članka: Decision Tree, Naive Bayes, Random Forest, logistička regresija i SVM (linearna, polinomijalna i RBF jezgra) na dva skupa: **Set A** (originalna ciljna varijabla, 5 klasa) i **Set B** (binarna ciljna varijabla). Modeli su evaluirani točnošću, preciznošću, odzivom, F1-mjerom i matricom zabune, a hiperparametri optimizirani pretraživanjem mreže s unakrsnom validacijom (*grid search*). Podjela podataka je 85% / 15%.
* `Paper_37-Implementation_of_Machine_Learning_Model.pdf` – članak koji replicira projekt.
* `Implementation_of_Machine_Learning_Model_to_Predict_Heart.pptx` – prezentacija trećeg dijela.
* CSV datoteke s podacima.

## Rezultati

Prema prezentaciji, najbolji je bio Random Forest na binarnoj ciljnoj varijabli (Set B) s točnošću oko 91%. Uz točnost smo izračunali i preciznost, odziv i F1-mjeru, jer je skup nebalansiran (najveća klasa ima oko 12 puta više primjera od najmanje), a na višeklasnom skupu (Set A) točnost je znatno niža. Usporedba s člankom nalazi se u prezentaciji i u zadnjem dijelu treće bilježnice.

### Razlike u odnosu na članak

* članak `num` tretira kao binarnu varijablu, a u podacima ima vrijednosti od 0 do 4, pa smo usporedili oba pristupa,
* podjela 85% / 15% umjesto 90% / 10% (više primjera u testnom skupu),
* uz točnost računamo preciznost, odziv, F1-mjeru i matricu zabune.

## Tehnologije

Python, pandas, NumPy, scikit-learn, seaborn, Matplotlib, Plotly

## Pokretanje

```bash
pip install pandas numpy scikit-learn seaborn matplotlib plotly
```

Bilježnice se pokreću ovim redoslijedom: drugi dio sprema datoteke `heart_failure_train_ready.csv` i `heart_failure_train_ready_standard.csv`, koje učitava treći dio. CSV datoteke moraju biti u istoj mapi kao bilježnice.

## Autori

Karla Budimir (prvi i drugi dio, priprema podataka), Mateo Jakšić, Ana Knezović (treći dio)
