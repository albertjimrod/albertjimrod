# Dashboard Mercado Laboral Data Science
## Proyecto Looker Studio

---

## 1. OBJETIVO

Proporcionar insights accionables sobre el mercado laboral de Data Science, enfocado en España, para ayudar a profesionales a tomar decisiones de carrera informadas.

**Audiencia:** Profesionales de datos buscando empleo o negociando salario.

---

## 2. PREGUNTAS DE NEGOCIO

| ID | Pregunta | Métrica clave | Visualización |
|----|----------|---------------|---------------|
| P1 | ¿Cuál es el salario promedio en España vs otros países? | AVG(salary_in_usd) | Barras horizontales |
| P2 | ¿Cómo evolucionan los salarios 2020-2024? | AVG(salary_in_usd) por año | Línea temporal |
| P3 | ¿Qué nivel de experiencia paga mejor? | AVG(salary_in_usd) por experience_level | Barras + % diferencia |
| P4 | ¿Remoto vs presencial afecta salario? | AVG(salary_in_usd) por work_models | Barras comparativas |
| P5 | ¿Qué roles pagan más? | AVG(salary_in_usd) por job_title | Top 10 barras |
| P6 | ¿Tamaño empresa influye? | AVG(salary_in_usd) por company_size | Barras S/M/L |

---

## 3. ESTRUCTURA DEL DASHBOARD

### PÁGINA 1: Executive Summary
```
┌────────────────────────────────────────────────────────────┐
│ TÍTULO: Mercado Laboral Data Science 2020-2024             │
│ SUBTÍTULO: Análisis de 6,600 ofertas globales              │
├──────────────┬──────────────┬──────────────┬───────────────┤
│  KPI 1       │  KPI 2       │  KPI 3       │  KPI 4        │
│  Salario     │  Total       │  España      │  Crecimiento  │
│  Mediano     │  Registros   │  Registros   │  Anual        │
│  $XXX,XXX    │  6,600       │  XX          │  +XX%         │
├──────────────┴──────────────┴──────────────┴───────────────┤
│                                                            │
│  [P2] GRÁFICO LÍNEAS: Evolución salarios por año           │
│                                                            │
├────────────────────────────┬───────────────────────────────┤
│  [P5] BARRAS: Top 10 roles │  [P3] DONUT: Por experiencia  │
│       mejor pagados        │       Entry/Mid/Senior        │
└────────────────────────────┴───────────────────────────────┘
```

### PÁGINA 2: Análisis por Experiencia y Modalidad
```
┌────────────────────────────────────────────────────────────┐
│ FILTROS: [Año] [País] [Rol]                                │
├────────────────────────────────────────────────────────────┤
│                                                            │
│  [P3] BARRAS: Salario por nivel experiencia                │
│       Entry-level | Mid-level | Senior | Executive         │
│                                                            │
├────────────────────────────────────────────────────────────┤
│                                                            │
│  [P4] BARRAS: Salario por modalidad trabajo                │
│       Remote | Hybrid | On-site                            │
│                                                            │
├────────────────────────────────────────────────────────────┤
│  [P6] BARRAS: Salario por tamaño empresa (S/M/L)           │
└────────────────────────────────────────────────────────────┘
```

### PÁGINA 3: España Focus
```
┌────────────────────────────────────────────────────────────┐
│ 🇪🇸 FOCO ESPAÑA                                            │
├──────────────┬──────────────┬──────────────────────────────┤
│  Salario     │  Registros   │  Comparativa vs media global │
│  Promedio ES │  España      │  -XX% vs Global              │
├──────────────┴──────────────┴──────────────────────────────┤
│                                                            │
│  [P1] BARRAS: España vs Top 10 países                      │
│                                                            │
├────────────────────────────────────────────────────────────┤
│  [TABLA] Detalle roles en España con salarios              │
│  job_title | experience | salary_usd | work_model          │
└────────────────────────────────────────────────────────────┘
```

---

## 4. CONFIGURACIÓN LOOKER STUDIO

### 4.1 Estilo Visual (coherente con tu marca)
- **Fondo:** #020024 (azul oscuro)
- **Acento:** #fdbf05 (dorado)
- **Texto:** #ffffff (blanco)
- **Secundario:** #rgba(255,255,255,0.7)

### 4.2 Fuente de Datos
- Archivo: `data_science_salaries.csv`
- Registros: 6,600
- Período: 2020-2024

### 4.3 Campos a usar
| Campo | Tipo | Uso |
|-------|------|-----|
| job_title | Dimensión | Roles |
| experience_level | Dimensión | Nivel experiencia |
| employment_type | Dimensión | Tipo contrato |
| work_models | Dimensión | Remoto/Presencial |
| work_year | Dimensión | Año |
| company_location | Dimensión | País empresa |
| employee_residence | Dimensión | País empleado |
| salary_in_usd | Métrica | Salario (usar AVG) |
| company_size | Dimensión | Tamaño empresa |

---

## 5. PASO A PASO CONSTRUCCIÓN

### Día 1: Setup + KPIs
- [ ] Configurar tema/colores del informe
- [ ] Crear 4 scorecards (KPIs principales)
- [ ] Añadir título y subtítulo

### Día 2: Página 1 - Gráficos principales
- [ ] Gráfico líneas: evolución temporal
- [ ] Barras: top 10 roles
- [ ] Donut: distribución experiencia

### Día 3: Página 2 - Análisis detallado
- [ ] Barras: salario por experiencia
- [ ] Barras: salario por modalidad
- [ ] Barras: salario por tamaño empresa
- [ ] Añadir filtros interactivos

### Día 4: Página 3 - España
- [ ] Filtro fijo: company_location = Spain
- [ ] Comparativa países
- [ ] Tabla detalle España

### Día 5: Pulido
- [ ] Revisar alineación
- [ ] Tooltips descriptivos
- [ ] Verificar responsive
- [ ] Publicar y obtener URL

---

## 6. INSIGHTS ESPERADOS (hipótesis a validar)

1. USA paga significativamente más que España (~2x)
2. Senior gana ~50% más que Entry-level
3. Remoto paga similar o más que presencial
4. Empresas grandes (L) pagan más que pequeñas (S)
5. Salarios han crecido año a año
6. Data Engineer/ML Engineer pagan más que Data Analyst

---

## 7. ENTREGABLES FINALES

- [ ] Dashboard público en Looker Studio
- [ ] URL compartible
- [ ] Capturas para GitHub README
- [ ] Notebook EDA complementario
- [ ] Post LinkedIn presentando el proyecto

---

## 8. ENLACES

- **Dataset:** Kaggle Data Science Salaries
- **Dashboard:** [URL pendiente]
- **GitHub:** github.com/albertjimrod/[repo]
- **Portfolio:** datablogcafe.com

