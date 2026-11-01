# Sistema de Agente Conversacional SCTR - Respaldo de Verificabilidad y Pruebas Estadísticas (2026)

Este repositorio contiene la implementación del orquestador RAG, el motor de guardrails, los registros auditables de interacciones y las pruebas estadísticas necesarias para respaldar de forma independiente los resultados expuestos en la tesis sobre la calidad del servicio en la difusión del **Seguro Complementario de Trabajo de Riesgo (SCTR)**.

---

## 📁 Estructura del Repositorio

```text
├── dataset/
│   ├── base_conocimiento_sctr.csv      # Corpus normativo (Ley N° 26790, D.S. N° 008-2022-SA)
│   ├── evaluacion_rag_180_consultas.csv # Registro auditable de las 180 interacciones evaluadas
│   └── datos_experimento_100_sesiones.csv # Datos del piloto (TPRC, CSAT, TCC, Tau-b Kendall)
├── src/
│   ├── rag_orchestrator.py            # Motor RAG con recuperación semántica y prompt engineering
│   └── guardrails.py                  # Capa de contención semántica y bloqueo de dominio
├── notebooks/
│   └── pruebas_estadisticas_sctr.ipynb# Cuaderno ejecutable con Wilcoxon, Chi-cuadrado y Tau-b Kendall
├── README.md                          # Documentación del proyecto
└── requirements.txt                   # Dependencias en Python
```

---

## 📊 Resumen de Resultados Verificables

| Componente / Métricas | Cifras Reportadas | Validación Estadística / Prueba |
| :--- | :---: | :---: |
| **Alta Fidelidad Legal (RAG)** | 169 de 180 consultas (93.89%) | Evaluación técnica en `evaluacion_rag_180_consultas.csv` |
| **Bloqueo de Dominio (Guardrails)** | 177 de 180 intentos (98.33%) | Filtro de inyecciones adversariales (`guardrails.py`) |
| **Reducción de Tiempo (TPRC)** | 18.52 min ➔ 1.41 min (-92.38%) | Prueba de Wilcoxon ($V = 5050, p < 0.001$) |
| **Conversión de Leads (TCC)** | 21.00% ➔ 72.50% (+51.50 pts) | Prueba Chi-cuadrado ($\chi^2 = 22.18, p < 0.001$) |
| **Correlación Hipótesis General** | $	au_b = 0.778$ | Tau-b de Kendall ($p < 0.001$) |

---

## 🚀 Instrucciones para Ejecutar las Pruebas Estadísticas

### 1. Clonar el repositorio e instalar dependencias
```bash
git clone https://github.com/TU_USUARIO/agente-conversacional-sctr.git
cd agente-conversacional-sctr
pip install -r requirements.txt
```

### 2. Ejecutar el Cuaderno Jupyter en Colab o Local
Abre el archivo `notebooks/pruebas_estadisticas_sctr.ipynb` en Jupyter Lab, VS Code o Google Colab y ejecuta todas las celdas para reproducir exactamente los valores estadísticos y gráficos reportados.

---

## 🛡️ Licencia y Ética
Este código forma parte del proyecto de investigación ejecutado bajo el **Código de Ética en Investigación de la Universidad César Vallejo (UCV)**. Todos los datos de las empresas y prospectos fueron anonimizados de conformidad con la Ley N° 29733 de Protección de Datos Personales en el Perú.
