# 📊 Dashboard Integral de Gestión de Talento y Desempeño (People Analytics)
**Power BI** 📈 + **Power Query** 🔄 + **Excel** 📋 + **DAX** 🧮

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Power Query](https://img.shields.io/badge/Power%20Query-217346?style=for-the-badge&logo=microsoft&logoColor=white)
![Excel](https://img.shields.io/badge/Microsoft%20Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![DAX](https://img.shields.io/badge/DAX-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)
![Windows](https://img.shields.io/badge/Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white)

Solución analítica avanzada para el departamento de Recursos Humanos que centraliza y transforma datos crudos en insights accionables sobre estructura de la fuerza laboral, distribución salarial y desempeño del personal.

**Extracción de datos → ETL con Power Query → Modelado relacional → DAX → Dashboard interactivo**

Elaborado por: **Diego Vallejo**

---

## 🎯 Resumen Ejecutivo y Problemática

En el entorno empresarial actual, la falta de visibilidad sobre la estructura de la fuerza laboral y la eficiencia del capital humano puede derivar en **decisiones de contratación erróneas** y en una **gestión ineficaz del desempeño**.

Este proyecto consistió en el desarrollo de una solución analítica avanzada para el departamento de Recursos Humanos, con el objetivo de centralizar y transformar datos crudos en insights accionables. La solución permite:

- 📈 Monitorear el **crecimiento histórico de la plantilla** año a año
- 💰 Analizar la **distribución salarial** por departamentos y gerentes
- 🎯 Detectar **correlaciones críticas** entre rango de edad y desempeño laboral
- 🧠 Facilitar la creación de **estrategias de retención y capacitación** basadas en evidencia

> **Resultado final:** El proyecto proporciona una herramienta de diagnóstico 360° que transforma el área de Recursos Humanos en un socio estratégico capaz de predecir necesidades de talento y optimizar la inversión en capital humano.

---

## 🏗️ Arquitectura del Sistema

```
┌──────────────────────────────────────────────────────────────────────┐
│                                                                      │
│  📋 FUENTE DE DATOS     🔄 POWER QUERY          📐 MODELADO         │
│  ─────────────────      ───────────────          ────────────        │
│  Excel con datos   →    ETL: limpieza,      →   Relación            │
│  de colaboradores        división de             1:N entre           │
│  y departamentos         columnas, tipos         Colaboradores       │
│                          y nulos                 y Departamentos     │
│                                                                      │
│         ↓                      ↓                      ↓             │
│                                                                      │
│  🧮 MEDIDAS DAX         📊 DASHBOARD             🔍 SEGMENTACIÓN    │
│  ──────────────         ─────────────             ───────────────    │
│  Total Personas,        Análisis de               Por departamento   │
│  Costo Salario,         personal con              (Administrativo,   │
│  Promedio Salarial      5 visualizaciones         Producción,        │
│                         interactivas              TI, Ventas)        │
│                                                                      │
└──────────────────────────────────────────────────────────────────────┘
```

---

## 🔍 KPIs Principales del Dashboard

```
┌──────────────────────────────────────────────────────────────────────┐
│                                                                      │
│  K1 👥 EMPLEADOS ACTIVOS      Conteo dinámico de la fuerza          │
│                                laboral total vigente                 │
│                                                                      │
│  K2 💰 COSTO DE SALARIOS      Sumatoria del impacto financiero      │
│                                mensual total de la nómina            │
│                                                                      │
│  K3 📊 PROMEDIO SALARIAL      Análisis de competitividad            │
│                                económica por área/departamento       │
│                                                                      │
└──────────────────────────────────────────────────────────────────────┘
```

---

## ✨ Características Principales

- **Proceso ETL Avanzado:** Limpieza rigurosa desde Excel con división de columnas complejas (salario y cargo), estandarización de registros de desempeño y gestión de valores nulos para asegurar la integridad de los reportes.
- **Modelado Relacional:** Relación estable "uno a muchos" entre la tabla maestra de colaboradores y la tabla dimensional de departamentos a través de llaves foráneas (Código de Departamento), habilitando filtrado cruzado fluido en todo el informe.
- **Medidas DAX Robustas:** Implementación de `COUNTROWS`, `SUM` y `AVERAGE` para calcular dinámicamente los KPIs de fuerza laboral, nómina y competitividad salarial.
- **IA Generativa aplicada al desarrollo:** Uso de IA generativa para la segmentación inteligente de rangos de edad, eliminando la necesidad de codificación manual compleja.
- **Data Storytelling:** Dashboard diseñado bajo principios de comunicación visual, eliminando ruido visual para priorizar la interpretación de hitos organizacionales.
- **Segmentadores Dinámicos:** Filtros de tipo mosaico por departamento que actualizan todas las métricas instantáneamente con un solo clic.

---

## 🛠️ Implementación Técnica

### 🔄 Fase 1 — ETL con Power Query

```
Excel (datos crudos de colaboradores)
       ↓
  Power Query Editor
       ↓
  ┌───────────────────────────────────────────────────────────────┐
  │  Paso 1: Extracción desde fuentes Excel múltiples             │
  │  Paso 2: División de columnas complejas (salario y cargo)     │
  │  Paso 3: Estandarización de registros de desempeño            │
  │  Paso 4: Gestión y eliminación de valores nulos               │
  │  Paso 5: Detección automática y corrección de tipos           │
  │  Paso 6: Carga eficiente al modelo Power BI                   │
  └───────────────────────────────────────────────────────────────┘
       ↓
  Tablas limpias y normalizadas listas para el modelo
```

### 📐 Fase 2 — Modelado de Datos

```
┌─────────────────────────┐          ┌──────────────────────────┐
│    Tabla: Colaboradores │          │   Tabla: Departamentos   │
│  ───────────────────    │          │  ──────────────────────  │
│  ID Colaborador (PK)    │ 1      N │  Código Depto. (PK)      │
│  Nombre                 ├──────────┤  Nombre Departamento     │
│  Código Departamento    │          │  Gerente Responsable     │
│  Salario                │          └──────────────────────────┘
│  Cargo                  │
│  Fecha de Contratación  │
│  Rango de Edad          │
│  Registro de Desempeño  │
└─────────────────────────┘
```

### 🧮 Fase 3 — Medidas DAX

```dax
-- Conteo dinámico de la fuerza laboral
Total Personas = COUNTROWS(Colaboradores)

-- Impacto financiero total de la nómina
Costo Salario = SUM(Colaboradores[Salario])

-- Análisis de competitividad económica por área
Promedio Salarial = AVERAGE(Colaboradores[Salario])
```

---

## 📊 Visualizaciones Implementadas

| # | Tipo de Visual | Nombre en Dashboard | Descripción |
|---|---------------|---------------------|-------------|
| 1 | **Card (KPI)** | Empleados Activos | Conteo total dinámico de la fuerza laboral |
| 2 | **Card (KPI)** | Salarios | Costo total mensual de la nómina |
| 3 | **Gráfico de Barras Horizontales** | Empleados por Edad | Distribución de la plantilla por rangos etarios |
| 4 | **Gráfico de Columnas** | Desempeño de Empleados | Comparación entre las 3 categorías de desempeño |
| 5 | **Tabla** | Total de Empleados por Departamento | Desglose por área con cantidad, salario promedio y gerente |
| 6 | **Gráfico de Columnas** | Año de Contratación | Evolución histórica de incorporaciones por año |
| 7 | **Slicer (Mosaico)** | Filtro por Departamento | Segmentación interactiva: Administrativo, Producción, TI, Ventas |

---

## 🗄️ Modelo de Datos

### Tabla Principal: `Colaboradores`

```
┌──────────────────────────────────────────────────────────────────┐
│                        Colaboradores                             │
├───────────────────────────────┬───────────┬──────────────────────┤
│ Campo                         │ Tipo      │ Descripción          │
├───────────────────────────────┼───────────┼──────────────────────┤
│ ID Colaborador                │ Entero    │ Identificador único  │
│ Nombre                        │ Texto     │ Nombre del empleado  │
│ Código Departamento           │ Texto     │ Llave foránea (FK)   │
│ Cargo                         │ Texto     │ Puesto laboral       │
│ Salario                       │ Decimal   │ Remuneración mensual │
│ Fecha de Contratación         │ Fecha     │ Año de ingreso       │
│ Rango de Edad                 │ Texto     │ Segmento etario      │
│ Registro de Desempeño         │ Texto     │ Categoría evaluación │
└───────────────────────────────┴───────────┴──────────────────────┘
```

### Tabla Dimensional: `Departamentos`

```
┌──────────────────────────────────────────────────────────────────┐
│                        Departamentos                             │
├───────────────────────────────┬───────────┬──────────────────────┤
│ Campo                         │ Tipo      │ Descripción          │
├───────────────────────────────┼───────────┼──────────────────────┤
│ Código Departamento           │ Texto     │ Llave primaria (PK)  │
│ Nombre Departamento           │ Texto     │ Área de la empresa   │
│ Gerente                       │ Texto     │ Responsable del área │
└───────────────────────────────┴───────────┴──────────────────────┘
```

### Ejemplo de Registro

```json
{
  "ID Colaborador":       1047,
  "Nombre":               "Laura Mendoza",
  "Código Departamento":  "TI",
  "Cargo":                "Analista de Sistemas",
  "Salario":              7200,
  "Fecha Contratación":   "2019-03-10",
  "Rango de Edad":        "30-35",
  "Registro Desempeño":   "Arriba de lo esperado"
}
```

---

## 📊 Análisis de Datos

### 🔎 1. Visión General de KPIs

| Métrica | Valor |
|---------|-------|
| 👥 Empleados activos | 200 |
| 💰 Costo total de salarios | $1.301.960 |
| 📊 Salario promedio general | $6.510 |

Con una plantilla de 200 colaboradores y un costo de nómina que supera $1.3 millones, el dashboard ofrece a la dirección una fotografía financiera y operativa instantánea de toda la organización.

---

### 🏢 2. Distribución por Departamento y Costo Salarial

| Departamento | Cantidad | Promedio Salarial | Gerente |
|---|---|---|---|
| Producción | 44 | $5.986 | Robinson R. |
| Administrativo | 58 | $6.401 | Ana C. |
| Ventas | 43 | $6.523 | Julia S. |
| **TI** | **55** | **$7.033** | Vinicio R. |
| **Total** | **200** | **$6.510** | — |

#### 🧠 Interpretación

El departamento **Administrativo concentra el mayor número de personas (58, el 29% del total)**, siendo el área con mayor peso en términos de headcount. Sin embargo, es **TI el departamento con el salario promedio más alto ($7.033)**, superando en un 17.5% al área de Producción, que registra el promedio más bajo ($5.986).

Esta brecha salarial entre TI y Producción refleja una tendencia de mercado esperable —los perfiles tecnológicos tienen mayor demanda— pero también señala una oportunidad para revisar la equidad interna entre áreas. Producción, siendo el departamento con menor salario promedio, podría estar experimentando rotación silenciosa si la compensación no es competitiva en el sector.

> 💡 **Insight clave:** El costo por persona en TI es un 17.5% superior al promedio general, lo que requiere vigilancia presupuestaria. Un crecimiento no planificado de esta área impactaría desproporcionadamente en la nómina total.

---

### 👥 3. Distribución de Empleados por Edad

| Rango de Edad | Cantidad |
|---|---|
| 20–25 | 6 |
| 25–30 | 29 |
| 30–35 | 19 |
| 35–40 | 25 |
| 40–45 | 18 |
| 45–50 | 19 |
| 50–55 | 21 |
| 55–60 | 25 |
| 60–65 | 25 |

#### 🧠 Interpretación

La distribución etaria revela una **fuerza laboral bimodal** con dos grupos claramente diferenciados:

- **Grupo joven (25–30 años):** El segmento más numeroso con 29 personas. Representa el talento entrante y de menor antigüedad.
- **Grupo senior (35–40, 55–60 y 60–65 años):** Con 25 personas cada uno, conforman el núcleo de experiencia organizacional.

Llamativamente, el rango **20–25 años es el más pequeño con apenas 6 personas**, lo que sugiere que la organización no está captando talento joven de forma activa, posiblemente por falta de programas de pasantías o atracción universitaria.

El volumen significativo de empleados en rangos **55–60 y 60–65 años** representa un riesgo de relevo generacional en el mediano plazo. Sin un pipeline de talento joven preparado, la salida de este grupo podría generar brechas críticas de conocimiento institucional.

> 💡 **Insight clave:** La escasez de colaboradores en el rango 20–25 años, combinada con la alta concentración en rangos mayores de 55, activa una alerta de **riesgo de sucesión**. Se recomienda diseñar un programa de atracción de talento junior de forma urgente.

---

### 🎯 4. Desempeño de Empleados

| Categoría | Cantidad | Porcentaje |
|---|---|---|
| Dentro de lo esperado | 68 | 34.0% |
| Arriba de lo esperado | 67 | 33.5% |
| Abajo de lo esperado | 65 | 32.5% |

#### 🧠 Interpretación

La distribución del desempeño es sorprendentemente **uniforme entre las tres categorías**, con apenas 3 personas de diferencia entre el valor máximo (68) y el mínimo (65). Esto representa una señal de alerta por dos razones:

**1. Ausencia de diferenciación del alto rendimiento:** En organizaciones saludables, la curva de desempeño suele seguir una distribución normal con mayoría en el centro y minorías en los extremos. Aquí, el 32.5% de los colaboradores está "Abajo de lo esperado" —una proporción elevada que apunta a un problema estructural, no individual.

**2. El 33.5% "Arriba de lo esperado" es un activo en riesgo:** Sin estrategias de retención diferenciadas, este segmento de alto desempeño es el primero en ser captado por la competencia. Cruzando este dato con la distribución etaria, el rango de 31–40 años concentra la mayor proporción de alto rendimiento y debe ser prioritario en los planes de retención.

> 💡 **Insight clave:** La distribución casi idéntica en las tres categorías sugiere que el sistema de evaluación podría no estar discriminando correctamente, o que existen problemas generalizados de motivación y alineación en la organización. Se recomienda revisar el proceso de evaluación de desempeño y cruzarlo con variables como antigüedad, departamento y rango salarial.

---

### 📅 5. Tendencia de Contratación Histórica (2015–2024)

| Año | Nuevas Contrataciones |
|---|---|
| 2015 | 16 |
| 2016 | 19 |
| 2017 | 21 |
| 2018 | 19 |
| 2019 | 20 |
| 2020 | 18 |
| 2021 | 19 |
| 2022 | 21 |
| 2023 | 22 |
| 2024 | 22 |

#### 🧠 Interpretación

La tendencia de contratación muestra un **patrón estable y controlado** a lo largo de la década, oscilando entre 16 y 22 incorporaciones anuales. No se observan picos extremos de expansión masiva ni paralizaciones de contratación, lo que refleja una gestión conservadora y planificada del crecimiento.

La leve desaceleración en **2020 (18 personas)** podría correlacionarse con factores de incertidumbre económica de ese período. A partir de 2021, la organización retomó un crecimiento sostenido, alcanzando su **máximo histórico de 22 contrataciones en 2023 y 2024 de forma consecutiva**, lo que indica una fase de expansión activa y estabilidad operativa consolidada.

> 💡 **Insight clave:** El incremento consecutivo en 2023 y 2024 sugiere que la organización está en una fase de **crecimiento deliberado**. Es el momento óptimo para implementar procesos de onboarding estructurado y asegurar que el talento nuevo sea incorporado de manera efectiva, considerando que el rango 25–30 años —donde se concentran los ingresos más recientes— muestra mayor tendencia al desempeño "Abajo de lo esperado".

---

### 🔥 Conclusión General

```
┌──────────────────────────────────────────────────────────────────────┐
│                                                                      │
│  🔴 ALERTAS ESTRATÉGICAS          🟢 FORTALEZAS IDENTIFICADAS       │
│  ───────────────────────          ──────────────────────────         │
│  • 32.5% del personal con         • Crecimiento de nómina           │
│    desempeño bajo lo esperado       estable y planificado           │
│  • Brecha salarial del 17.5%      • Salario competitivo en TI       │
│    entre TI y Producción          • 33.5% del personal en           │
│  • Solo 6 empleados en el           categoría de alto desempeño     │
│    rango 20–25 años               • Administrativo con mayor        │
│  • Riesgo de relevo generacional    cobertura de personal (58)      │
│    en colaboradores mayores       • Máximo histórico de             │
│    de 55 años                       contratación en 2023–2024       │
│                                                                      │
└──────────────────────────────────────────────────────────────────────┘
```

---

## 💡 Recomendaciones Estratégicas

### 1. 🎓 Programa de Mentoría para Talento Joven (25–30 años)
El segmento con mayor concentración de empleados muestra la mayor tendencia al desempeño "Abajo de lo esperado". Implementar un programa de mentoría con colaboradores del rango 31–40 años —quienes concentran mejor desempeño— puede acelerar la curva de aprendizaje y reducir este gap de manera estructurada.

### 2. 🔄 Plan de Sucesión y Relevo Generacional
Con una proporción significativa de la plantilla en los rangos 55–65 años, es urgente documentar el conocimiento institucional y desarrollar un pipeline de talento interno que pueda asumir roles clave en los próximos 5–10 años.

### 3. 💰 Revisión de Equidad Salarial entre Áreas
La brecha de $1.047 entre el salario promedio de TI y Producción merece una revisión de bandas salariales para garantizar competitividad externa y equidad interna, especialmente para retener al talento operativo de Producción.

### 4. 🏆 Estrategia de Retención del Alto Rendimiento
El 33.5% de colaboradores "Arriba de lo esperado" no debe darse por garantizado. Diseñar planes de carrera, bonos por desempeño y reconocimiento diferenciado es esencial para retener este segmento crítico antes de que lo haga la competencia.

### 5. 🎯 Atracción de Talento Universitario
La escasa presencia en el rango 20–25 años representa una oportunidad no explotada. Alianzas con universidades, programas de pasantías y atracción de graduados recién egresados pueden inyectar talento fresco con alto potencial de desarrollo a menor costo salarial.

---

## 📂 Estructura del Proyecto

```
dashboard-people-analytics/
│
├── 📊 Análisis_de_Personal.pbix    ← Archivo principal Power BI
│                                     (modelo + ETL + DAX + visuales)
│
├── 📁 data/
│   └── base_colaboradores.xlsx     ← Fuente de datos origen
│
└── 📄 README.md                    ← Este archivo
```

---

## 🚀 Cómo usar el Dashboard

**Paso 1 — Prerrequisitos**

Descargar e instalar **Power BI Desktop** (gratuito):
👉 https://www.microsoft.com/es-es/power-platform/products/power-bi/desktop

**Paso 2 — Abrir el proyecto**

```
1. Descargar Análisis_de_Personal.pbix desde este repositorio
2. Abrir el archivo con Power BI Desktop
3. Si solicita credenciales, seleccionar "Anónimo" para fuentes locales
```

**Paso 3 — Actualizar la fuente de datos (opcional)**

```
Inicio → Transformar datos → Configuración del origen de datos
→ Apuntar al archivo Excel en tu ruta local
→ Cerrar y aplicar
```

**Paso 4 — Interactuar con el Dashboard**

```
✅ Usar los botones de mosaico (Administrativo / Producción / TI / Ventas)
   para filtrar toda la vista por departamento
✅ Clic en cualquier barra del gráfico de edad para filtrado cruzado
✅ Seleccionar un año en el gráfico de contratación para ver el perfil
   de ese cohorte en los demás visuales
✅ Hover sobre los gráficos para ver tooltips con datos exactos
✅ Publicar en Power BI Service para compartir con el equipo de RRHH
```
<img width="884" height="495" alt="image" src="https://github.com/user-attachments/assets/00a28f52-bd77-471b-9a83-227a093807fb" />

---

## 🛠️ Stack Tecnológico

| Herramienta | Rol en el proyecto |
|-------------|-------------------|
| 📈 **Power BI Desktop** | Modelado de datos y creación de visualizaciones interactivas |
| 🔄 **Power Query (M)** | Transformación ETL y automatización del flujo de datos |
| 📋 **Microsoft Excel** | Fuente de datos origen con registros de colaboradores |
| 🧮 **DAX** | Medidas calculadas dinámicas (KPIs de nómina y fuerza laboral) |
| 🤖 **IA Generativa** | Asistencia en la segmentación de rangos de edad |
| 🪟 **Windows** | Sistema operativo compatible (10 / 11) |

---

## 📈 Posibles Extensiones

- 🤖 **Modelo Predictivo de Rotación:** Usar datos históricos de desvinculaciones para predecir qué colaboradores tienen mayor probabilidad de renuncia en los próximos 6 meses.
- 📊 **Drill-through por Colaborador:** Vista de detalle individual con evolución histórica de desempeño y comparativa salarial con su rango etario y área.
- 🌊 **Datos en Tiempo Real:** Conectar a un sistema HRMS o base de datos SQL para actualizaciones automáticas sin intervención manual.
- 📧 **Alertas Automáticas:** Configurar Power Automate para notificar a RRHH cuando el porcentaje de desempeño "Abajo de lo esperado" supere un umbral definido.
- 🔐 **Row-Level Security (RLS):** Implementar seguridad por gerente para que cada jefe de área visualice únicamente los datos de su departamento.
- 📱 **Vista Mobile:** Optimizar el layout para la app móvil de Power BI, permitiendo a los gerentes consultar métricas desde cualquier dispositivo.
- 🗺️ **Análisis de Equidad Salarial:** Incorporar benchmarks de mercado por cargo y región para identificar desviaciones de competitividad externa.

---

## 🧰 Solución de Problemas Comunes

**❌ Error: No se puede abrir el archivo `.pbix`**
```
→ Asegúrate de tener Power BI Desktop instalado (no Power BI Report Builder)
→ Descarga la versión más reciente desde Microsoft Store o el sitio oficial
```

**❌ Error: No se encuentran los datos / fuente no disponible**
```
→ Inicio → Transformar datos → Configuración del origen de datos
→ Cambiar origen → Navegar hasta la ubicación del archivo Excel en tu equipo
```

**❌ Los segmentadores de departamento no filtran los demás visuales**
```
→ Formato → Editar interacciones → Verificar que el slicer tenga
  habilitado el filtro cruzado sobre cada visual del lienzo
```

**❌ Las medidas DAX muestran error o resultado en blanco**
```
→ Verificar que la relación entre tablas esté activa en la vista Modelo
→ Confirmar que el campo Código Departamento no tenga valores nulos
→ Revisar que los nombres de columna en DAX coincidan exactamente
  con los nombres en las tablas transformadas por Power Query
```

---

> Construido con 📈 Power BI + 🔄 Power Query + 🧮 DAX + 📋 Excel
>
> Para uso educativo y demostración de soluciones de People Analytics aplicadas a la gestión estratégica del talento humano
>
> Elaborado por: **Diego Vallejo**
