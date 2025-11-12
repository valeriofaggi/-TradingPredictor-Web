# ⚡ Quick Start - Trading Predictor WEB

Comandi rapidi per testare e deployare.

---

## 🧪 Test Locale (Prima del Deploy)

### 1. Installa Dipendenze

```bash
cd "D:\Programmi2\Trading WEB"
"D:\Programmi2\Pyton\python.exe" -m pip install -r requirements.txt
```

### 2. Copia Dati di Test

Per testare localmente, copia i dati dal progetto Ibrido:

```bash
cp "../TRADING Ibrido/data/"*.csv data/
```

### 3. Avvia Dashboard Locale

```bash
"D:\Programmi2\Pyton\python.exe" -m streamlit run app.py
```

Dashboard apre su: http://localhost:8501

### 4. Verifica Funzionamento

Controlla che:
- [x] Dashboard si carica
- [x] Titoli visibili
- [x] Grafici funzionanti
- [x] Previsioni generate

Se tutto OK → Pronto per deploy! ✅

---

## 🚀 Deploy su Streamlit Cloud

### Setup Repository GitHub

```bash
cd "D:\Programmi2\Trading WEB"

# Init git
git init

# Add files
git add .
git commit -m "Initial commit - Trading Predictor Web"

# Link repository (scegli opzione A o B)

# OPZIONE A: Nuovo repository separato
git remote add origin https://github.com/valeriofaggi/TradingPredictor-Web.git

# OPZIONE B: Stesso repository esistente
git remote add origin https://github.com/valeriofaggi/TradingClaude.git

# Push
git branch -M main
git push -u origin main
```

### Deploy App

1. Vai su: https://streamlit.io/cloud
2. Sign up with GitHub
3. New app:
   - Repository: `valeriofaggi/TradingPredictor-Web` (o TradingClaude)
   - Branch: `main`
   - Main file: `app.py`
   - Python: `3.11`
4. Deploy!

**Tempo**: 3-5 minuti

---

## 🔄 Aggiornamenti

### Modifiche Locali → Deploy

```bash
# Fai modifiche ai file...

# Commit e push
git add .
git commit -m "Update features"
git push
```

Streamlit Cloud rileva automaticamente e ricarica!

---

## 📋 Checklist Pre-Deploy

- [ ] Test locale funziona
- [ ] File requirements.txt presente
- [ ] File app.py nella root
- [ ] Cartelle models/, utils/, config/ presenti
- [ ] GitHub repository creato
- [ ] Account Streamlit Cloud creato

---

## 🆘 Problemi Comuni

### ModuleNotFoundError locale

```bash
"D:\Programmi2\Pyton\python.exe" -m pip install -r requirements.txt --upgrade
```

### App crash su Streamlit Cloud

1. Controlla logs
2. Verifica Python version = 3.11
3. Riavvia app

### Dati mancanti

```bash
# Copia dati da progetto Ibrido
cp "../TRADING Ibrido/data/"*.csv data/
```

---

## 🔗 Link Utili

- **Guida Completa**: [DEPLOY_GUIDE.md](./DEPLOY_GUIDE.md)
- **README**: [README.md](./README.md)
- **Streamlit Cloud**: https://streamlit.io/cloud

---

**Ultimo aggiornamento**: 2025-11-12
