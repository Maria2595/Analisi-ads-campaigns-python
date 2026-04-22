📊 Progetto Python: Tracciamento KPIs ads campaigns

Data progetto: Aprile 2026
Dataset: 10.000 campagne pubblicitarie online (3 tipi di abbonamento) 

🔗 Dashboard Power BI
👉(https://github.com/Maria2595/Analisi-ads-campaigns-python/raw/main/Dashboard/Marketing%20Dashboard%20.pbix)

📌 Nota: La dashboard non è pubblicata online per rispettare le policy di sicurezza

📁 Contenuto repository

```
Analisi-vendite-sql/
├── Dashboard/
│   └── Marketing Dashboard.pbix          # Dashboard Power BI
├── AnalisiPython/
│   └── MP1.ipynb                          # Query: KPI, trasformazioni, aggregazioni per report dati
├── Dataset/
│   └── MP.csv                             # Dataset originale (Zenodo)
└── README.md

📝 Descrizione del progetto
Obiettivo: Calcolare KPI, tracciare e categorizzare le campagne Ads in base alle performance.
Cosa contiene l'analisi:

•	10.000 campagne pubblicitarie online
•	3 tipi di abbonamento: Basic, Standard, Premium
•	KPI calcolati: ROAS (Return on Ad Spend), ARPU (Average Revenue Per User), Profit Margin, Cost per Click
•	Categorizzazione performance campagne pubblicitarie (custom functions)


Tecniche utilizzate:
•	Aggregazioni per definire range (min, max, avg)
•	Custom functions per aggiungere etichette alle categorie
•	Trasformazione dati in report per Power BI

⚠️ Limiti dichiarati (trasparenza)
Con i dati a disposizione, mancano informazioni su:

•	Target specifico delle Ads (dati demografici, interessi, se già clienti/acquistato precedentemente, fasce orarie di sottoscrizione abbonamento)
•	Categoria/tipo di prodotto pubblicizzato

Cosa servirebbe per andare oltre:

Integrare dati qualitativi o di targeting per identificare i fattori di successo


Strumenti	Utilizzati

Python (pandas)	Calcolo KPI, aggregazioni, custom functions
Jupyter Notebook	Analisi esplorativa e documentazione
Power BI	Dashboard interattiva

Insight 1 – Buona perfromance delle campagne per tutti gli abbonamenti
•	Basic, Standard e Premium mantengono un livello di profitto sopra la media

Insight 2 – Premium meno efficiente nella conversione
•	Costo per click (CPC) più alto rispetto alle conversioni in confronto agli altri due abbonamenti
•	Richiede ottimizzazione del targeting

Insight 3 – Standard il più volatile
•	Vendite con maggiore variabilità nel tempo
•	Necessario monitoraggio continuo

Insight 4 – ROAS e ARPU sotto la media per tutti e tre i tipi
•	Performance complessiva migliorabile
•	Opportunità di ottimizzazione per tutti i segmenti


## 💻 Snippet Python (esempio)

Ecco un esempio della custom function utilizzata per classificare le performance delle campagne:

```python
def ROAS_range(ROAS, valore_medio=5, valore_alto=100):
    """Classifica il ROAS in Basso, Medio o Alto."""
    if ROAS <= valore_medio:
        return 'ROAS Basso'
    elif ROAS <= valore_alto:
        return 'ROAS Medio'
    else:
        return 'ROAS Alto'

# Applicazione della funzione al DataFrame
campaign_report['Livello_ROAS'] = campaign_report['ROAS'].apply(ROAS_range)
```

**Cosa fa questo codice:**
- Classifica il ROAS (Return on Ad Spend) in tre livelli di performance
- Utilizza una **custom function** riutilizzabile su qualsiasi colonna numerica
- La logica può essere facilmente adattata ad altri KPI (ARPU, CPC, ecc.)

📌 *Il codice completo è disponibile in `AnalisiPython/MP1.ipynb`.*
