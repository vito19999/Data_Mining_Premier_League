# Data_Mining_Premier_League
Progetto end-to-end di Data Mining sulla Premier League 2020-21. Include pipeline di pulizia dati (Silver Layer), Feature Engineering (aggregazione eventi), EDA, e modelli di Machine Learning (Random Forest, SVM) per classificare e prevedere l'esito dei match.



#  Data Mining & Machine Learning: English Premier League 2020-21

 **Versione Italiana**

Questo progetto esplora l'uso del Data Mining e del Machine Learning per profilare gli esiti delle partite di Premier League (Vittoria, Pareggio, Sconfitta) analizzando i pattern statistici generati in campo. Partendo da un dataset grezzo (Bronze Layer) di ~607.000 eventi, il progetto sviluppa una pipeline end-to-end strutturata in 3 Jupyter Notebook.

###  Tecnologie Utilizzate
*   **Linguaggio:** Python
*   **Librerie:** Pandas, NumPy, Scikit-Learn, SHAP, Seaborn, Matplotlib, SciPy, .....
*   **Approcci ML:** Random Forest, Support Vector Machine (Lineare & RBF), Clustering (K-Medoids, Ward)

###  Pipeline del Progetto

1. **`Data_Cleaning_and_Understanding.ipynb` (Bronze & Silver Layer):**
   * **Data Understanding:** Analisi approfondita della semantica dei dati, interpretazione dei "null strutturali" (non imputabili) e costruzione algoritmica di un `match_id` univoco partendo da contatori intra-partita.
   * **Data Cleaning & Parsing:** Filtraggio degli eventi e parsing vettorializzato di dati complessi (JSON `qualifiers`) per estrarre 28 nuove metriche tattiche e spaziali (es. passaggi lunghi, zone del corpo, coordinate).
     
2. **`Feature_extraction_EDA.ipynb` (Gold Layer):**
   * **Aggregazione Dimensionale:** Trasformazione del dataset pulito da ~607k eventi singoli a 760 righe aggregate (una per squadra-partita).
   * **Feature Engineering:** Creazione di metriche di dominanza relazionale e situazionale per limitare la ridondanza.
   * **Exploratory Data Analysis (EDA):** Analisi delle distribuzioni e gestione degli outlier (metodo IQR), accompagnata da un'ampia visualizzazione grafica dei risultati (boxplot, matrici di correlazione).
  
3. **`Machine_Learning_Modeling.ipynb`:**
   * **Apprendimento Supervisionato:** Classificazione multiclasse (Win/Draw/Loss) con Random Forest e SVM. Ottimizzazione tramite GridSearchCV e cross-validation (GroupKFold) per evitare il *group leakage*. Interpretazione del modello tramite valori SHAP e visualizzazione grafica dei risultati (confusion matrix, grafici di comparazione delle performance).
   * **Apprendimento Non Supervisionato:** Analisi di clustering (K-Medoids con $K=3$, validato tramite Silhouette Score) per segmentare oggettivamente le squadre in profili tattici reali (es. *Dominio Territoriale*, *Catenaccio*).

---

 **English Version**

This project explores the use of Data Mining and Machine Learning to profile the outcomes of Premier League matches (Win, Draw, Loss) by analyzing on-pitch statistical patterns. Starting from a raw dataset (Bronze Layer) of ~607,000 events, the project features an end-to-end pipeline divided into 3 Jupyter Notebooks.

###  Technologies Used
*   **Language:** Python
*   **Libraries:** Pandas, NumPy, Scikit-Learn, SHAP, Seaborn, Matplotlib, SciPy, ...
*   **ML Approaches:** Random Forest, Support Vector Machine (Linear & RBF), Clustering (K-Medoids, Ward)

###  Project Pipeline

1. **`Data_Cleaning_and_Understanding.ipynb` (Bronze & Silver Layer):**
   * **Data Understanding:** In-depth analysis of data semantics, interpretation of "structural nulls" (non-imputable), and algorithmic construction of a unique `match_id` from intra-match counters.
   * **Data Cleaning & Parsing:** Event filtering and vectorized parsing of complex JSON arrays (`qualifiers`) to extract 28 new tactical and spatial metrics (e.g., long balls, body parts, coordinates).
     
2. **`Feature_extraction_EDA.ipynb` (Gold Layer):**
   * **Dimensional Aggregation:** Transforming the clean dataset from ~607k raw events into 760 team-match aggregated records.
   * **Feature Engineering:** Creation of relational and situational dominance metrics to reduce redundancy.
   * **Exploratory Data Analysis (EDA):** Distribution analysis and outlier detection (IQR method), supported by comprehensive data visualization and result graphs (boxplots, correlation matrices).
     
3. **`Machine_Learning_Modeling.ipynb`:**
   * **Supervised Learning:** Multiclass classification (Win/Draw/Loss) using Random Forest and SVM. Optimization via GridSearchCV and GroupKFold cross-validation to prevent *group leakage*. Model interpretation via SHAP values and graphical visualization of results (confusion matrices, performance comparison charts).
   * **Unsupervised Learning:** Clustering analysis (K-Medoids with $K=3$, validated via Silhouette Score) to objectively segment teams into distinct tactical profiles (e.g., *Territorial Dominance*, *Defensive Block*).
