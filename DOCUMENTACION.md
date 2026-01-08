# 📊 Gemelo Digital - Simulador de Planta RTB/SALFA

## Guía Técnica y de Uso Completa

### 📋 Índice
1. [Introducción](#introducción)
2. [Características](#características)
3. [Guía de Usuario](#guía-de-usuario)
4. [Modelo Matemático](#modelo-matemático)
5. [Configuración Técnica](#configuración-técnica)
6. [Normativa de Referencia](#normativa-de-referencia)

---

## Introducción

El **Gemelo Digital - Simulador RTB/SALFA** es una herramienta educativa e industrial que replica el comportamiento de plantas de tratamiento de aguas servidas (TAS) de tipo lecho reactivo biológico (LRB) o sistemas secuenciales como RTB20, RTB30, RTB40 y RTB60.

**Objetivo:** Permitir a ingenieros ambientales, operadores de plantas y estudiantes simular en tiempo real el comportamiento de sistemas de tratamiento bajo diferentes condiciones operacionales y cargas contaminantes.

---

## Características

### 🎨 Interfaz Visual

#### Panel Izquierdo - Configuración
- **Selector de Planta:** Cambio dinámico entre 4 modelos (RTB20, RTB30, RTB40, RTB60)
- **Sliders Interactivos:**
  - Caudal de entrada: 1–80 m³/día
  - DBO₅ entrada: 50–1000 mg/L
  - DQO entrada: 100–2000 mg/L
  - Tiempo ON (aireación): 1–60 minutos
  - Tiempo OFF (reposo): 0–30 minutos

#### Canvas Central - Visualización 3D
- Tanques con textura acanalada (ribbed texture)
- Color verde militar (#2d5016) para reactores
- Animación de burbujas durante aireación
- Tuberías celeste/naranja conectadas
- Aireadores (sopladores) dibujados sobre reactores
- Flujo de agua con flechas direccionales

#### Panel Derecho - Resultados
- **Medidores Circulares (Gauges):**
  - DBO₅ Salida (mg/L)
  - DQO Salida (mg/L)
  - % Eficiencia Global
  - Estado del Reactor (Verde=Aireando, Ámbar=Reposo)
  - Carga Volumétrica (kg DBO₅/m³·día)
- **Badges de Normativa:**
  - ✓ Cumple si DBO₅ ≤ 35 mg/L y DQO ≤ 75 mg/L
  - ✗ Excede si supera límites

### ⚡ Funcionalidades Avanzadas

1. **Ciclo de Aireación Automático:**
   - Alterna entre ON (aeróbico) y OFF (anóxico)
   - Visualización en tiempo real del estado

2. **Modelo Matemático Dinámico:**
   - Degradación exponencial de contaminantes
   - Constantes de reacción variables según aireación
   - Factor de sobrecarga si Q > Capacidad × 1.5

3. **Responsividad:**
   - Adaptable a pantallas grandes (desktop) y medianas
   - Glassmorphism + Dark Mode profesional
   - Animaciones suaves y transiciones

---

## Guía de Usuario

### Paso 1: Seleccionar Planta
1. Abre el archivo `index.html` en navegador (Chrome, Firefox, Safari, Edge)
2. En el panel izquierdo, elige la capacidad deseada
3. El canvas central se actualizará dinámicamente con tanques

### Paso 2: Configurar Parámetros
1. **Caudal:** Desliza hasta el valor esperado de entrada (m³/día)
   - RTB20: recomendado 15–20 m³/día
   - RTB30: recomendado 20–30 m³/día
2. **DBO₅ Entrada:** Ajusta según efluente esperado
   - Agua residual doméstica: 200–400 mg/L
   - Agua residual industrial: 400–1000 mg/L
3. **DQO Entrada:** Generalmente DQO ≈ 2 × DBO₅

### Paso 3: Configurar Ciclo de Aireación
1. **Tiempo ON:** Duración de aireación (recomendado 20–40 min)
2. **Tiempo OFF:** Duración de reposo anóxico (recomendado 5–15 min)
3. Relación típica ON:OFF = 3:1 a 4:1

### Paso 4: Ejecutar Simulación
1. Haz clic en **▶ Iniciar Simulación**
2. El botón cambiará a **⏹ Detener**
3. Observa:
   - Animación de burbujas en reactores
   - Cambio de color del indicador (Verde→Ámbar)
   - Actualización en tiempo real de valores

### Paso 5: Analizar Resultados
- **Eficiencia Global:** Meta > 85% para cumplir normativa
- **DBO₅ Salida:** Debe estar < 35 mg/L
- **DQO Salida:** Debe estar < 75 mg/L
- **Carga Volumétrica:** < 0.5 kg/m³·día es óptimo

### Paso 6: Optimizar Operación
Ajusta los sliders para encontrar configuración óptima:
- Aumenta Tiempo ON si eficiencia < 85%
- Reduce Caudal si planta está sobrecargada
- Disminuye Tiempo OFF si hay problemas de anoxia

---

## Modelo Matemático

### Ecuación Base: Cinética de Primer Orden

```
C_salida = C_entrada × e^(-k × TRH)
```

Donde:
- **C_entrada:** Concentración de contaminante (DBO₅, DQO) en mg/L
- **C_salida:** Concentración a la salida en mg/L
- **k:** Constante de degradación (día⁻¹)
- **TRH:** Tiempo de Retención Hidráulica (horas)

### Eficiencia de Remoción

```
Eficiencia = (C_entrada - C_salida) / C_entrada × 100%
```

### Tiempo de Retención Hidráulica (TRH)

```
TRH (horas) = Volumen_Reactor (m³) / [Caudal (m³/día) / 24]
```

### Constantes de Degradación

| Condición | k (día⁻¹) | Descripción |
|-----------|-----------|-------------|
| **Aireando (Aeróbico)** | 0.15 | Alta degradación, microorganismos activos |
| **Reposo (Anóxico)** | 0.03 | Baja degradación, procesos anaerobios |

### Factor de Sobrecarga

Si `Caudal > Capacidad × 1.5`:
```
Eficiencia_real = Eficiencia_calculada × 0.3
```
(Penalización del 70% en eficiencia)

---

## Configuración Técnica

### Estructura HTML

```html
<header>              <!-- Título y estado -->
<main-container>      <!-- Grid: Control + Canvas + Resultados -->
  ├─ control-panel    <!-- Sliders y botones -->
  ├─ visualization    <!-- Canvas 2D -->
  └─ results-panel    <!-- Gauges y normativa -->
</main-container>
```

### Componentes Canvas

1. **Tanques:**
   - Rectángulo redondeado con textura (líneas acanaladas)
   - Relleno translúcido azul (nivel de agua)
   - Brillo especular para efecto 3D

2. **Aireadores:**
   - Círculo naranja (#ff8c00)
   - Aspas giratorias (rotación proporcional al tiempo)
   - Tuberías de aire hacia tanque

3. **Burbujas:**
   - Partículas azules que suben dinámicamente
   - Opacidad decreciente
   - Seno para movimiento lateral

4. **Tuberías:**
   - Línea celeste punteada con curvatura Bézier
   - Acoples naranjas en conexiones

### JavaScript - Lógica Principal

```javascript
// Ciclo de simulación
requestAnimationFrame(simulate) {
  1. Actualizar cycleTime
  2. Determinar si isAerating (cycleTime < timeOn)
  3. Calcular efficiency con modelo exponencial
  4. Suavizar cambios (filtro de primer orden)
  5. Actualizar UI y redibujar canvas
}
```

---

## Normativa de Referencia

### Estándares Chilenos (DS 90/2000 - MOP)

| Parámetro | Límite | Estado |
|-----------|--------|--------|
| **DBO₅** | ≤ 35 mg/L | Obligatorio |
| **DQO** | ≤ 75 mg/L | Obligatorio |
| **SST** | ≤ 30 mg/L | Obligatorio |
| **Nitrógeno Total** | ≤ 15 mg/L | Recomendado |
| **Fósforo Total** | ≤ 2 mg/L | Recomendado |

### Criterios de Diseño Típicos

| Parámetro | Valor | Referencia |
|-----------|-------|-----------|
| **TRH Reactor** | 16–24 h | Estándar LRB |
| **Carga Volumétrica** | 0.3–0.6 kg DBO₅/m³·día | Óptimo |
| **Ciclo Aireación** | ON:OFF = 3–4:1 | Recomendado |
| **Velocidad Aire** | 0.2–0.4 m/min | Eficiente |

---

## Troubleshooting

### ❌ Problema: Eficiencia muy baja (< 50%)

**Soluciones:**
1. Aumentar Tiempo ON (más aireación)
2. Reducir Caudal (menos sobrecarga)
3. Verificar que Caudal ≤ Capacidad × 1.2

### ❌ Problema: DBO₅ Salida excede 35 mg/L

**Soluciones:**
1. Alargar ciclo de aireación (↑ Time ON)
2. Disminuir DBO₅ entrada (pre-tratamiento)
3. Cambiar a planta de mayor capacidad

### ❌ Problema: Carga Volumétrica > 0.8 kg/m³·día

**Soluciones:**
1. Reducir Caudal
2. Seleccionar RTB de mayor capacidad
3. Aumentar Tiempo ON (metabolismo más activo)

---

## Extensiones Futuras

1. **Modelo Avanzado:**
   - Incluir nitrificación/desnitrificación
   - Parámetros de biomasa activa
   - Cálculo de lodos generados

2. **Exportación de Datos:**
   - Gráficas históricas (Chart.js)
   - CSV con resultados de ciclos
   - Reportes PDF

3. **Integración IoT:**
   - Conexión a sensores reales
   - MQTT para telemetría
   - Almacenamiento en base de datos

4. **Optimización Automática:**
   - Algoritmo genético para ciclo óptimo
   - Machine Learning para predicción
   - Recomendaciones de operación

---

## Autores y Licencia

**Desarrollo:** Ingeniero Ambiental + Full-Stack Developer  
**Versión:** 1.0 (Enero 2026)  
**Licencia:** Uso educativo e industrial libre  
**Basado en:** Esquemas RTB/SALFA (Salfa Group)

---

## Contacto y Soporte

Para reportar bugs, sugerencias o consultorías:
- 📧 soporte@gemelo-digital.cl
- 🔗 GitHub: https://github.com/gemelo-digital-tas

---

**Última actualización:** 08 de Enero, 2026

*Herramienta desarrollada para profesionales de ingeniería ambiental, operadores de plantas y estudiantes.*
