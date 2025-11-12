# 🚀 Guida Deploy su Streamlit Cloud

Guida completa passo-passo per pubblicare Trading Predictor su Streamlit Cloud (GRATIS).

---

## 📋 Prerequisiti

### 1. Account GitHub
- ✅ Già configurato: https://github.com/valeriofaggi/TradingClaude
- ✅ Repository con GitHub Actions attivo

### 2. Account Streamlit Cloud (GRATUITO)
- ⏳ Da creare (5 minuti)
- Link: https://streamlit.io/cloud

---

## 🎯 Step 1: Preparare Repository GitHub

### A. Creare Nuovo Repository per Versione WEB

Hai due opzioni:

#### **Opzione A: Repository Separato** (RACCOMANDATO)
Crea un nuovo repository pubblico o privato solo per la versione web.

1. Vai su: https://github.com/new
2. Compila:
   - **Repository name**: `TradingPredictor-Web`
   - **Visibility**: Public (necessario per Streamlit Cloud free tier)
   - **Initialize**: NO (lo popoleremo noi)
3. Click "Create repository"

#### **Opzione B: Stesso Repository**
Usa lo stesso repository `TradingClaude` esistente.

---

### B. Upload File nella Cartella "Trading WEB"

Apri Git Bash nella cartella del progetto:

```bash
cd "D:\Programmi2\Trading WEB"

# Inizializza Git
git init

# Aggiungi tutti i file
git add .

# Commit iniziale
git commit -m "Initial commit - Trading Predictor Web Version"

# Collega al repository GitHub
# OPZIONE A (nuovo repository):
git remote add origin https://github.com/valeriofaggi/TradingPredictor-Web.git

# OPZIONE B (stesso repository):
git remote add origin https://github.com/valeriofaggi/TradingClaude.git

# Push su GitHub
git branch -M main
git push -u origin main
```

**IMPORTANTE**: Se usi Opzione A (repository separato), devi anche copiare i file di raccolta dati:

```bash
# Copia collector e workflows dal repository esistente
cd "D:\Programmi2\Trading WEB"
mkdir -p .github/workflows collector
cp -r "../TRADING Ibrido/.github/workflows/." ".github/workflows/"
cp -r "../TRADING Ibrido/collector/." "collector/"
git add .github collector
git commit -m "Add data collection workflow"
git push
```

---

## 🎯 Step 2: Configurare Streamlit Cloud

### A. Creare Account Streamlit Cloud

1. Vai su: https://streamlit.io/cloud
2. Click "Sign up"
3. **Scegli "Continue with GitHub"**
4. Autorizza Streamlit ad accedere al tuo GitHub
5. Login completato! ✅

### B. Deploy Applicazione

1. Nella dashboard Streamlit Cloud, click **"New app"**

2. Configura app:
   - **Repository**: Seleziona il tuo repository
     - Opzione A: `valeriofaggi/TradingPredictor-Web`
     - Opzione B: `valeriofaggi/TradingClaude`
   - **Branch**: `main`
   - **Main file path**: `app.py`
   - **App URL** (custom): `trading-predictor` (o qualsiasi nome libero)

3. **Advanced settings** (click per espandere):
   - **Python version**: `3.11`
   - **Secrets**: (lascia vuoto per ora, non servono API key)

4. Click **"Deploy!"**

### C. Attesa Deploy

Streamlit Cloud farà:
1. ✅ Clone repository
2. ✅ Install Python 3.11
3. ✅ Install dependencies (requirements.txt)
4. ✅ Start app

**Tempo stimato**: 3-5 minuti

---

## 🎯 Step 3: Sincronizzazione Dati

### Come Funziona

```
┌─────────────────────────────────┐
│  GITHUB ACTIONS (ogni 15 min)  │
│  Raccoglie dati → Commit CSV    │
└────────────┬────────────────────┘
             │
             │ Auto-sync
             ▼
┌─────────────────────────────────┐
│     STREAMLIT CLOUD (24/7)      │
│  Legge CSV → Genera Dashboard   │
└─────────────────────────────────┘
```

**Streamlit Cloud sincronizza automaticamente** il repository ogni volta che:
- Ci sono nuovi commit
- Ricarichi la pagina
- L'app fa un rerun

**NON serve configurare nulla!** I dati raccolti da GitHub Actions saranno automaticamente disponibili.

---

## 🎯 Step 4: Verifica Deploy

### A. Accedi alla Tua App

Dopo il deploy, riceverai un URL tipo:
```
https://trading-predictor-valeriofaggi.streamlit.app
```

Oppure:
```
https://valeriofaggi-tradingpredictor-web-app-xxxxx.streamlit.app
```

### B. Verifica Funzionamento

Controlla che:
- [x] Dashboard si carica correttamente
- [x] Tutti i 10 titoli sono visibili
- [x] Dati storici sono presenti
- [x] Previsioni vengono generate
- [x] Grafici sono interattivi

### C. Se Mancano Dati

**Problema**: Dashboard vuota o errori "Dati non trovati"

**Causa**: GitHub Actions non ha ancora popolato i file CSV

**Soluzione**:
1. Vai su: https://github.com/valeriofaggi/TradingClaude/actions
2. Seleziona workflow "Stock Data Collection"
3. Click "Run workflow" → "Run workflow"
4. Attendi completamento (~1 minuto)
5. Verifica che commit automatico è stato creato
6. Torna su Streamlit Cloud e ricarica la pagina

---

## 🎯 Step 5: Gestione App

### Reboot App (se necessario)

Se l'app ha problemi:
1. Dashboard Streamlit Cloud
2. Click sui 3 puntini (⋮) vicino all'app
3. Click "Reboot app"

### Visualizzare Logs

Per debug:
1. Dashboard Streamlit Cloud
2. Click sull'app
3. Nella parte bassa, click "Manage app"
4. Tab "Logs" mostra tutti gli errori

### Aggiornare App

**Metodo Automatico** (raccomandato):
```bash
# Fai modifiche locali
cd "D:\Programmi2\Trading WEB"
# Modifica file...

# Commit e push
git add .
git commit -m "Update dashboard features"
git push
```

Streamlit Cloud **rileva automaticamente** il push e ricarica l'app!

**Metodo Manuale**:
- Dashboard → Manage app → "Reboot app"

---

## 💰 Costi e Limiti

### Streamlit Cloud - Free Tier

**Quota Gratuita**:
- ✅ 1 app pubblica GRATIS
- ✅ Risorse:
  - 1 GB RAM
  - 1 CPU core
  - Storage limitato (sufficiente per il nostro progetto)
- ✅ Uptime: 24/7
- ✅ Auto-scaling

**Limitazioni**:
- ⚠️ App pubblica (visibile a tutti con URL)
- ⚠️ Si spegne dopo ~5 giorni di inattività (riprende al primo accesso)
- ⚠️ Max 1 app simultanea (free tier)

**Per App Privata**:
- Serve Streamlit Cloud Team: $250/mese
- Alternativa: VPS Aruba ~5€/mese

### Combinazione Costi Totali

**Setup Attuale (GRATIS)**:
- GitHub Actions: 0€ (sotto 2000 min/mese)
- Streamlit Cloud: 0€ (1 app pubblica)
- **TOTALE: 0€/mese** 🎉

---

## 🔧 Configurazioni Avanzate

### Auto-Refresh Dati

L'app riceve automaticamente nuovi dati da GitHub Actions.

Se vuoi forzare refresh manuale:
```python
# In app.py, aggiungi un pulsante
if st.button("🔄 Refresh Dati"):
    st.rerun()
```

### Secrets Management

Se in futuro vuoi aggiungere API key (es. Finnhub):

1. Dashboard Streamlit Cloud
2. Manage app → "Advanced settings"
3. Tab "Secrets"
4. Aggiungi in formato TOML:
```toml
FINNHUB_API_KEY = "your-api-key-here"
```

5. Nell'app, accedi con:
```python
import streamlit as st
api_key = st.secrets["FINNHUB_API_KEY"]
```

### Custom Domain (Opzionale)

Streamlit Cloud supporta domini personalizzati (solo tier a pagamento).

---

## 🐛 Troubleshooting

### Errore: "Requirements.txt not found"

**Causa**: requirements.txt non nella root

**Soluzione**:
```bash
cd "D:\Programmi2\Trading WEB"
ls requirements.txt  # Verifica esista
git add requirements.txt
git commit -m "Add requirements"
git push
```

### Errore: "Module not found"

**Causa**: Dipendenza mancante in requirements.txt

**Soluzione**:
```bash
# Aggiungi la dipendenza mancante
echo "nome-package>=versione" >> requirements.txt
git add requirements.txt
git commit -m "Add missing dependency"
git push
```

### Errore: "App crashed" o "Memory limit exceeded"

**Causa**: Troppi dati caricati in memoria

**Soluzione**:
- Riduci giorni storici caricati
- Implementa caching con `@st.cache_data`
- Ottimizza modelli ML

### App Lenta

**Cause Comuni**:
1. Troppi calcoli ML ad ogni reload
2. Dati non cachati

**Soluzioni**:
```python
# In app.py, usa caching
@st.cache_data(ttl=3600)  # Cache per 1 ora
def load_data(symbol):
    # ... carica dati ...
    return data

@st.cache_resource
def load_ml_model():
    # ... inizializza modello ...
    return model
```

---

## 🎯 Checklist Finale

Verifica tutto funzioni:

- [ ] Repository GitHub con file Trading WEB pushato
- [ ] GitHub Actions attivo e funzionante
- [ ] Account Streamlit Cloud creato
- [ ] App deployata su Streamlit Cloud
- [ ] URL app funzionante
- [ ] Dashboard mostra tutti i titoli
- [ ] Dati storici presenti
- [ ] Previsioni generate correttamente
- [ ] Grafici interattivi

---

## 🔗 Link Utili

- **Tua App**: https://[your-app-url].streamlit.app
- **Streamlit Cloud Dashboard**: https://share.streamlit.io/
- **GitHub Repository**: https://github.com/valeriofaggi/TradingClaude
- **GitHub Actions**: https://github.com/valeriofaggi/TradingClaude/actions
- **Streamlit Docs**: https://docs.streamlit.io/streamlit-community-cloud

---

## 📞 Supporto

### Documentazione Streamlit Cloud
- https://docs.streamlit.io/streamlit-community-cloud

### Community Forum
- https://discuss.streamlit.io/

### GitHub Issues
- https://github.com/streamlit/streamlit/issues

---

## 🎉 Prossimi Passi

Dopo il deploy:

1. **Condividi l'URL** con amici/colleghi
2. **Monitora GitHub Actions** per verificare raccolta dati
3. **Ottimizza performance** con caching
4. **Aggiungi nuove funzionalità**:
   - Notifiche email
   - Export PDF report
   - Più titoli internazionali
   - Backtest strategie

---

**Versione Guida**: 1.0
**Data**: 2025-11-12
**Autore**: Claude Code

---

## 🆘 Problemi Comuni e Soluzioni Rapide

### "My app is sleeping"

**Causa**: App non usata per 5+ giorni

**Soluzione**: Clicca "Wake up" - l'app riparte in ~30 secondi

### "Build failed"

**Passi Debug**:
1. Controlla logs in Streamlit Cloud
2. Verifica requirements.txt
3. Testa localmente:
```bash
cd "D:\Programmi2\Trading WEB"
"D:\Programmi2\Pyton\python.exe" -m streamlit run app.py
```
4. Se funziona in locale, problema è nel deploy
5. Controlla versione Python in Streamlit Cloud (deve essere 3.11)

---

**Fine Guida Deploy** ✅
