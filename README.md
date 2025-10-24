# 🏀 Rotowire NBA ROY Odds Archive

Este repositorio **recopila y archiva automáticamente las cuotas diarias del Rookie of the Year (ROY)** de la NBA publicadas por [RotoWire](https://www.rotowire.com/betting/nba/rookie-odds.php).  
Los datos se almacenan en formato CSV mediante un flujo automatizado de **GitHub Actions**.

---

## 📋 Qué hace este repositorio

- Ejecuta un script en R (`get_roy_odds.R`) que extrae las cuotas del ROY desde RotoWire.  
- Añade una **marca temporal** para saber cuándo se obtuvieron los datos.  
- Guarda los resultados como un **archivo CSV con fecha** dentro de la carpeta `data/`.  
- Se ejecuta **a diario** y también **bajo demanda** mediante GitHub Actions.  
- Realiza commit y push automáticos de los nuevos archivos, creando un **archivo histórico** de cuotas del ROY a lo largo del tiempo.

---

## ⚙️ Cómo funciona

1. El flujo de trabajo de **GitHub Actions** se activa:
   - Automáticamente cada día a las **08:30 AM UTC**.  
   - Manualmente desde el botón **“Run workflow”** en la pestaña *Actions*.
2. Configura un entorno **R** en un runner Linux.  
3. Instala los paquetes necesarios (`jsonlite`, `dplyr`) y dependencias del sistema.  
4. Ejecuta el script `get_roy_odds.R`, que descarga y guarda los datos actualizados.  
5. Hace commit y push de los nuevos CSV al repositorio, manteniendo un registro completo de la evolución de las cuotas.

---

## 📂 Estructura del repositorio

├── get_roy_odds.R # Script R que obtiene y guarda los datos
├── data/ # CSVs diarios (roy_odds_YYYY_MM_DD.csv)
└── .github/
└── workflows/ # Archivo YAML con la configuración de GitHub Actions

---

## 🗓️ Ejemplo de archivo generado

data/roy_odds_2025_10_24.csv

Cada archivo contiene las cuotas del ROY en el momento en que fueron extraídas, junto con la fecha y hora correspondientes.

