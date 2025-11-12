# 📈 Trading Predictor - Web Version

Sistema di analisi e previsione prezzi azionari con Machine Learning, ottimizzato per **Streamlit Cloud**.

**🌐 SEMPRE ONLINE - GRATIS - ACCESSIBILE OVUNQUE**

---

## 🎯 Cos'è Trading Predictor Web?

Versione cloud del Trading Predictor che gira 24/7 su Streamlit Cloud (hosting gratuito).

### Caratteristiche
- ✅ **100% Gratuito** - Zero costi operativi
- ✅ **Sempre Online** - Accessibile 24/7 da qualsiasi dispositivo
- ✅ **Dati Aggiornati** - Raccolta automatica ogni 15 minuti via GitHub Actions
- ✅ **Machine Learning** - Previsioni con Prophet + Random Forest
- ✅ **10 Titoli Italiani** - FTSE MIB principali
- ✅ **Dashboard Interattiva** - Grafici Plotly, analisi tecnica, storico previsioni

---

## 🏗️ Architettura

```
┌─────────────────────────────────┐
│   GITHUB ACTIONS (24/7)         │
│   • Raccolta dati Yahoo Finance │
│   • Commit automatici CSV       │
│   • Orari mercato: 7-17 UTC     │
└────────────┬────────────────────┘
             │
             │ Git Sync Automatico
             ▼
┌─────────────────────────────────┐
│   STREAMLIT CLOUD (24/7)        │
│   • Dashboard sempre online     │
│   • ML predictions real-time    │
│   • Grafici interattivi         │
│   • Accessibile da web          │
└─────────────────────────────────┘
```

---

## 🚀 Deploy Rapido

### Prerequisiti
1. ✅ Account GitHub (già configurato)
2. ⏳ Account Streamlit Cloud (gratis, 5 min setup)

### Steps
1. **Leggi la guida completa**: [DEPLOY_GUIDE.md](./DEPLOY_GUIDE.md)
2. **Push questo progetto su GitHub**
3. **Deploy su Streamlit Cloud** (3 click)
4. **App online!** 🎉

**Tempo totale**: 10-15 minuti

---

## 📊 Funzionalità Dashboard

### 8 Sezioni Principali

1. **🌐 Panoramica Completa**
   - Tutti i 10 titoli a colpo d'occhio
   - Prezzi live e variazioni
   - Performance giornaliera

2. **📈 Analisi Titolo**
   - Grafici dettagliati
   - Indicatori tecnici (SMA, RSI, MACD, Bollinger)
   - Volume trading

3. **⏱️ Previsioni 2 Ore**
   - Breve termine ultra-preciso
   - Ideale per day trading

4. **📅 Previsioni 1-3-7 Giorni**
   - Medio termine
   - Swing trading
   - Trend analysis

5. **🎯 Accuratezza Modello**
   - Storico previsioni vs realtà
   - Metriche performance (MAE, RMSE, MAPE)
   - Confidence intervals

6. **📊 Grafici Accuratezza**
   - Visualizzazioni avanzate
   - Trend errori nel tempo
   - Filtri per orizzonte temporale

7. **Sidebar**
   - Selezione titolo
   - Gestione watchlist
   - Settings

---

## 🎓 Titoli Tracciati

### FTSE MIB Top 10
- **ENI.MI** - Eni
- **ISP.MI** - Intesa Sanpaolo
- **UCG.MI** - UniCredit
- **ENEL.MI** - Enel
- **A2A.MI** - A2A
- **TIT.MI** - Telecom Italia
- **G.MI** - Generali
- **RACE.MI** - Ferrari
- **BAMI.MI** - Banco BPM
- **TEN.MI** - Tenaris

**Personalizzabile**: Aggiungi/rimuovi titoli dalla dashboard

---

## 🧠 Machine Learning

### Algoritmi
1. **Prophet** (Meta/Facebook)
   - Time series forecasting
   - Trend + seasonality detection
   - Anomaly detection

2. **Random Forest**
   - Ensemble learning
   - Feature importance
   - Robust to overfitting

### Indicatori Tecnici
- Moving Averages (SMA 20/50/200, EMA 12/26)
- RSI (Relative Strength Index)
- MACD (Moving Average Convergence Divergence)
- Bollinger Bands
- ATR (Average True Range)
- OBV (On-Balance Volume)

---

## 📁 Struttura Progetto

```
Trading WEB/
├── app.py                    # Dashboard Streamlit (main)
├── requirements.txt          # Dipendenze Python
├── .streamlit/
│   └── config.toml          # Configurazione Streamlit
├── models/
│   └── predictor.py         # ML models
├── utils/
│   ├── data_collector.py    # Data fetching
│   ├── technical_indicators.py
│   ├── sentiment_analyzer.py
│   └── prediction_logger.py
├── config/
│   └── config.py            # Settings
├── data/                     # Dati (da GitHub Actions)
│   └── .gitkeep
├── DEPLOY_GUIDE.md          # Guida deploy completa
└── README.md                # Questo file
```

---

## 💰 Costi

### Totale: 0€/mese 🎉

**Breakdown**:
- Streamlit Cloud: 0€ (Free tier - 1 app pubblica)
- GitHub Actions: 0€ (sotto 2000 min/mese)
- Yahoo Finance API: 0€ (gratuita)

**Confronto Alternative**:
- VPS Aruba: ~5€/mese
- AWS/Azure: ~10-20€/mese
- Heroku: ~7€/mese

---

## 🔧 Requisiti Tecnici

### Server (Streamlit Cloud)
- Python 3.11
- 1 GB RAM
- 1 CPU core
- Auto-scaling

### Client (Browser)
- Qualsiasi browser moderno
- Chrome, Firefox, Safari, Edge
- Mobile friendly

---

## 🌐 Accesso

Dopo il deploy, la tua app sarà accessibile da:
```
https://[your-custom-url].streamlit.app
```

**Da qualsiasi dispositivo**:
- 💻 PC / Mac
- 📱 Smartphone
- 📱 Tablet
- 🌍 Ovunque nel mondo

---

## 🔐 Sicurezza

- ✅ Repository privato GitHub (dati non pubblici)
- ✅ Nessuna API key necessaria
- ✅ Yahoo Finance gratuito (no authentication)
- ⚠️ App URL pubblica (chiunque con link può accedere)

**Per rendere app privata**:
- Upgrade a Streamlit Cloud Team ($250/mese)
- Oppure usa VPS privato

---

## 🆚 Differenze vs Versione Ibrida

| Feature | Ibrida (Locale) | Web (Cloud) |
|---------|-----------------|-------------|
| **Hosting** | PC locale | Streamlit Cloud |
| **Accessibilità** | Solo da PC casa | Ovunque, 24/7 |
| **Costo** | 0€ | 0€ |
| **PC sempre acceso** | NO | NO |
| **Raccolta dati** | GitHub Actions | GitHub Actions |
| **Privacy** | Massima | Media (URL pubblico) |
| **Setup** | 10 min | 15 min |

---

## 📚 Documentazione

- **[DEPLOY_GUIDE.md](./DEPLOY_GUIDE.md)** - Guida deploy completa
- **Streamlit Docs**: https://docs.streamlit.io/
- **Prophet Docs**: https://facebook.github.io/prophet/
- **yfinance Docs**: https://pypi.org/project/yfinance/

---

## 🐛 Troubleshooting

### App non si carica
1. Controlla logs su Streamlit Cloud
2. Verifica GitHub Actions ha raccolto dati
3. Riavvia app da dashboard

### Dati mancanti
1. Vai su GitHub Actions
2. Run workflow "Stock Data Collection" manualmente
3. Attendi commit
4. Ricarica app Streamlit

### Deploy fallito
1. Controlla requirements.txt
2. Verifica Python version = 3.11
3. Testa localmente prima

**Guida completa**: [DEPLOY_GUIDE.md](./DEPLOY_GUIDE.md#troubleshooting)

---

## 🎯 Roadmap Futuri Sviluppi

### Breve Termine
- [ ] Notifiche email alert
- [ ] Export PDF report
- [ ] Dark mode

### Medio Termine
- [ ] Espansione titoli USA (S&P 500)
- [ ] Portfolio tracking
- [ ] Backtesting strategie

### Lungo Termine
- [ ] Trading automatico (paper trading)
- [ ] Criptovalute
- [ ] Mobile app

---

## 🤝 Contributi

Questo è un progetto personale, ma suggerimenti sono benvenuti!

---

## 📄 Licenza

Progetto personale - Uso educativo e di ricerca.

---

## 📞 Supporto

**Per deploy su Streamlit Cloud**:
- 📖 Leggi [DEPLOY_GUIDE.md](./DEPLOY_GUIDE.md)
- 🌐 Streamlit Community: https://discuss.streamlit.io/

**Per questioni tecniche**:
- 📋 GitHub Issues: https://github.com/streamlit/streamlit/issues

---

## 🎉 Inizia Ora!

1. **Leggi**: [DEPLOY_GUIDE.md](./DEPLOY_GUIDE.md)
2. **Deploy**: 3 click su Streamlit Cloud
3. **Enjoy**: App online 24/7! 🚀

---

**Versione**: 1.0 - Web Cloud Edition
**Data**: 2025-11-12
**Status**: ✅ Pronto per produzione
