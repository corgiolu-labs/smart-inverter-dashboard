# ⚡ Smart Inverter Dashboard  
Sistema avanzato di monitoraggio per inverter fotovoltaici  
Raspberry Pi • Modbus RTU • ADS1115 • PWA Web App • Grafici Realtime

---

## 🚀 Caratteristiche principali

### Lettura Inverter (Modbus RTU)
- Comunicazione RS232/RS485  
- Parsing registri inverter (ISOLAR SMG-II e compatibili)  
- Timeout intelligenti e retry automatici  
- Stabilità garantita anche con segnali disturbati  

### Monitoraggio Energetico
- Produzione PV  
- Consumo totale casa  
- Energia prelevata dalla rete  
- Carica/scarica batterie  
- Calcolo SOC avanzato  
- Efficienza di sistema  

### Sensori I²C (ADS1115)
- Lettura shunt 75 mV  
- Lettura tensioni tramite partitori  
- Calibrazione automatica  
- Configurazione dinamica via JSON  

### Controllo automatico dei relè
- Attivazione e disattivazione basata su tensione  
- Isteresi configurabile  
- Tempo minimo tra commutazioni  
- Possibilità di controllo manuale  

### Dashboard Realtime (Web App)
- Grafici dinamici aggiornati ogni 5 secondi  
- Indicatori live: PV, Battery, Grid, Load  
- Allarmi e notifiche istantanee  

### PWA – Progressive Web App
- Installabile su smartphone  
- Funziona anche offline grazie al Service Worker  
- Interfaccia moderna e dinamica  

### Storico su SQLite
- Registrazione continua dei dati  
- Generazione grafici PNG giornalieri e mensili  
- Analisi avanzate tramite script Python  

---

## 🧠 Architettura del Progetto

smart-inverter-dashboard/  
• backend/  
 • inverter_api.py – API Flask (Modbus, ADS1115, GPIO, SQLite)  
 • daily_analyzer.py – Analisi giornaliera  
 • auto_graph_generator.py – Grafici automatici  
 • config/ – Configurazioni JSON  
• web/  
 • index.html – Dashboard realtime  
 • analysis_dashboard.html – Statistiche avanzate  
 • settings.html – Configurazione  
 • app.mod.js – Logica frontend  
 • sw.js – Supporto offline  
• graphs/ – Grafici mensili/giornalieri  
• docs/ – Screenshot del sistema  
• README.md  
• .gitignore  

---

## 🛠 Installazione su Raspberry Pi

### 1. Clona la repository
git clone https://github.com/corgiolu-labs/smart-inverter-dashboard.git  
cd smart-inverter-dashboard/backend

### 2. Installa dipendenze Python
python3 -m venv venv  
source venv/bin/activate  
pip install -r requirements.txt

### 3. Configura l’inverter
Modifica il file:  
config/inverter_config.json  

Imposta:
- Porta seriale (es. /dev/serial0)  
- Parametri Modbus  
- Sensori ADS1115  
- Soglie relè  
- Parametri batteria  

### 4. Avvia il backend
python3 inverter_api.py

### 5. Servi la parte web
Pubblica la cartella:  
web/  

Server consigliati: Nginx, Caddy, Python HTTP Server.

---

## 📡 API Principali

GET /api/inverter – Dati realtime inverter  
GET /api/i2c – Sensori ADS1115  
GET /api/history – Ultimi valori registrati  
POST /api/settings – Aggiorna configurazione  
POST /api/relay – Controlla stato relè  

---

## 📸 Screenshot (da aggiungere)

Inserisci immagini nella cartella docs/:

- screenshot-dashboard.png  
- screenshot-analysis.png  
- screenshot-settings.png  
- screenshot-offline.png  

---

## 🗺 Roadmap

- Grafico SOC storico  
- Modalità settimanale e mensile  
- Supporto MQTT  
- Supporto Modbus TCP  
- Auto-deploy Raspberry  
- Tema chiaro/scuro  
- Riconoscimento anomalie basato su AI  

---

## 👨‍💻 Autore

Alessandro Corgiolu  
Embedded • Automazione • Energie Rinnovabili  
Email: corgiolu.labs@gmail.com  
GitHub: https://github.com/corgiolu-labs  

---

⭐ “Monitoraggio energetico avanzato, semplice e affidabile.”
