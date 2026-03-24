# ConnectaTel — Customer Behavior Analysis & Churn Segmentation

## Descripción del proyecto

Análisis de comportamiento de clientes para ConnectaTel, una empresa de telecomunicaciones en Latinoamérica. El proyecto exploró patrones de consumo, segmentación por edad y nivel de uso, y riesgo de churn entre los usuarios de los planes Básico y Premium. El objetivo fue traducir los datos de uso en recomendaciones accionables para retención, upsell y desarrollo de producto.

---

## Objetivo del análisis

Identificar segmentos de usuarios con comportamiento diferenciado para guiar decisiones comerciales orientadas a incrementar el ARPU, reducir el churn silencioso y mejorar el alineamiento entre la oferta de planes y el comportamiento real de los clientes.

---

## Datasets utilizados

| Archivo | Filas | Columnas | Descripción |
|---|---|---|---|
| `plans.csv` | 2 | 8 | Planes disponibles (Básico y Premium): precios, inclusiones y cargos por excedente |
| `users_latam.csv` | 4,000 | 8 | Registro de usuarios: datos demográficos, ciudad, fecha de alta y plan contratado |
| `usage.csv` | 40,000 | 6 | Historial de uso: llamadas, mensajes y datos con duración y extensión por registro |

---

## Stack y herramientas

- **Lenguaje:** Python 3
- **Entorno:** Google Colab / Jupyter Notebook
- **Librerías:** Pandas, NumPy, Matplotlib, Seaborn, SciPy

---

## Etapas del análisis

1. **Exploración inicial** — revisión de estructura, tipos de datos, valores únicos y estadísticas descriptivas de los tres datasets
2. **Limpieza de datos** — detección y tratamiento de valores sentinel, placeholders, nulos estructurales (MAR) y fechas futuras inválidas
3. **Ingeniería de variables** — construcción de segmentos etarios (Joven, Adulto, Adulto Mayor) y segmentos de uso (Bajo, Medio, Alto)
4. **Análisis descriptivo** — distribución de usuarios por plan, ciudad, edad y comportamiento de consumo
5. **Análisis cruzado** — cruce entre segmento de uso y plan contratado para identificar desalineación oferta-comportamiento
6. **Visualización** — gráficos de distribución, conteo por segmento y comparativas entre planes
7. **Análisis ejecutivo** — síntesis de hallazgos con metodología CFI (Context → Finding → Implication) y recomendaciones de negocio

---

## Hallazgos clave

- **Desalineación oferta-comportamiento:** Una proporción significativa de usuarios clasificados como Alto uso permanecía en plan Básico, pagando cargos por excedente superiores al costo mensual del plan Premium sin recibir sus beneficios.
- **Churn silencioso en Bajo uso:** Los usuarios de Bajo uso mantienen el plan activo sin interacción real con el servicio, representando el segmento de mayor riesgo de cancelación sin señales previas visibles.
- **La edad no predice la adopción del plan:** Ambos planes presentaron distribuciones de edad casi idénticas, descartando el perfil demográfico como variable de segmentación para campañas de upsell.
- **Patrón de uso diferenciado en usuarios Jóvenes (<30 años):** Este segmento mostró mayor proporción de mensajes y menor volumen de llamadas, un perfil que el plan Básico actual no atiende eficientemente.
- **El crecimiento está en la base existente:** ConnectaTel no enfrenta un problema de adquisición, sino de alineación. La oportunidad de ingresos se encuentra en migrar, retener y reactivar usuarios dentro de la base actual.

---

## Recomendaciones de negocio

1. **Campaña de upsell por consumo:** Dirigida a usuarios en plan Básico con minutos de llamada superiores al percentil 75, mostrando el ahorro real frente a sus cargos actuales por excedente.
2. **Programa de retención para Adultos de alto consumo:** Fidelización con descuentos o beneficios exclusivos para el segmento de 30–59 años de uso medio-alto, el de mayor impacto en ARPU.
3. **Producto para el segmento Joven:** Plan o add-on con mayor inclusión de mensajes y menor énfasis en minutos, alineado al comportamiento real de usuarios menores de 30 años.
4. **Reactivación de usuarios dormidos:** Campaña con beneficio temporal (minutos o mensajes gratuitos por 30 días) para usuarios de Bajo uso con más de 60 días de inactividad.

---

## Cómo reproducir el análisis

1. Clonar este repositorio:
   ```bash
   git clone https://github.com/tu-usuario/connectatel-churn-analysis.git
   ```
2. Abrir el notebook en Google Colab o Jupyter:
   - Desde Colab: `Archivo → Abrir notebook → GitHub` y pegar la URL del repo
   - Desde Jupyter: ejecutar `jupyter notebook` en la carpeta del proyecto
3. Verificar que los tres archivos `.csv` estén en la misma ruta que el notebook (o ajustar los `pd.read_csv()` según corresponda)
4. Ejecutar las celdas en orden secuencial

---

## Estructura del repositorio

```
connectatel-churn-analysis/
│
├── connectatel_analysis.ipynb   # Notebook principal con todo el análisis
├── plans.csv                    # Dataset de planes
├── users_latam.csv              # Dataset de usuarios
├── usage.csv                    # Dataset de uso
└── README.md                    # Este archivo
```

---

## Autor

**Gerardo Vázquez Cruz**  
Data Analyst
[GitHub](https://github.com/gerardovazquez-DataAnalyst) · [LinkedIn](https://linkedin.com/in/gerardo-vazquez-dataanalyst)
