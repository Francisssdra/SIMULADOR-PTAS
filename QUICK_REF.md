# ⚡ REFERENCIA RÁPIDA - GEMELO DIGITAL RTB/SALFA

## 📋 ACCESO RÁPIDO

```
┌─────────────────────────────────────────────────────────────┐
│  PASO 1: ABRIR                                              │
├─────────────────────────────────────────────────────────────┤
│  Doble-clic en: index.html                                  │
│  Se abre automáticamente en tu navegador                    │
└─────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────┐
│  PASO 2: CONFIGURAR (2 minutos)                             │
├─────────────────────────────────────────────────────────────┤
│  Panel Izquierdo - Ajusta:                                  │
│  1. Planta: RTB30 (por defecto)                             │
│  2. Caudal: 20 m³/día (típico)                              │
│  3. DBO₅: 200 mg/L (agua residual)                          │
│  4. DQO: 400 mg/L (2× DBO₅)                                 │
│  5. Time ON: 30 minutos                                     │
│  6. Time OFF: 10 minutos                                    │
└─────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────┐
│  PASO 3: SIMULAR (1 clic)                                   │
├─────────────────────────────────────────────────────────────┤
│  Haz clic en: ▶ Iniciar Simulación                          │
│                                                              │
│  Observa:                                                   │
│  • Burbujas subiendo en reactores 🫧🫧                       │
│  • Indicador: Verde (Aireando) o Ámbar (Reposo)             │
│  • Canvas central: Flujo de agua izq → derecha              │
│  • Panel derecho: Valores cambiando en tiempo real           │
└─────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────┐
│  PASO 4: ANALIZAR (Leer panel derecho)                      │
├─────────────────────────────────────────────────────────────┤
│  ✅ DBO₅ Salida ≤ 35 mg/L          → Verde ✓              │
│  ❌ DBO₅ Salida > 35 mg/L          → Rojo ✗               │
│                                                              │
│  ✅ DQO Salida ≤ 75 mg/L           → Verde ✓              │
│  ❌ DQO Salida > 75 mg/L           → Rojo ✗               │
│                                                              │
│  Meta: Eficiencia ≥ 85%                                     │
│  Meta: Carga Vol. < 0.5 kg/m³·día                           │
└─────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────┐
│  PASO 5: OPTIMIZAR (si no cumple)                           │
├─────────────────────────────────────────────────────────────┤
│  SI DBO₅ Salida > 35 (ROJO):                                │
│     → Aumenta Time ON (+5 min)                              │
│     → O reduce Caudal (-10%)                                │
│     → O cambia a planta mayor                               │
│                                                              │
│  SI Carga Volumétrica > 0.8:                                │
│     → ACCIÓN INMEDIATA: Reducir Caudal                      │
│     → O cambiar a RTB mayor                                 │
└─────────────────────────────────────────────────────────────┘
```

---

## 🎛️ CONTROLES DEL SIMULADOR

### Panel Izquierdo (Entrada)

```
┌──────────────────────────────┐
│   🎛️ CONFIGURACIÓN           │
├──────────────────────────────┤
│                              │
│ Modelo de Planta:            │
│ [RTB20] [RTB30] [RTB40]      │
│ [RTB60]                      │
│                              │
│ Caudal Entrada: ----○---- 20 │
│                 1        80   │
│                              │
│ DBO₅ Entrada:   ----○---- 200│
│                 50      1000  │
│                              │
│ DQO Entrada:    ----○---- 400│
│                 100     2000  │
│                              │
│ Tiempo ON:      ----○---- 30 │
│                 1        60   │
│                              │
│ Tiempo OFF:     ----○---- 10 │
│                 0        30   │
│                              │
│  ▶ Iniciar Simulación        │
│  🔄 Reiniciar                │
│                              │
└──────────────────────────────┘
```

### Canvas Central (Visualización)

```
  ACUMULACIÓN    REACTOR 1    REACTOR 2    REACTOR 3   CLARIFICADOR
  ┌─────────┐    ┌────────┐   ┌────────┐   ┌────────┐   ┌──────┐
  │ 🟢green │───→│🔴burst │──→│🔴burst │──→│🔴burst │──→│🔷blue│───→ SALIDA
  │ 7 m³    │    │3.3m³   │   │3.3m³   │   │3.3m³   │   │3 m³  │
  └─────────┘    └────────┘   └────────┘   └────────┘   └──────┘
    ENTRADA      ⬆️ Aireador  ⬆️ Aireador  ⬆️ Aireador
                 💨 Aire      💨 Aire      💨 Aire
```

### Panel Derecho (Salida)

```
┌──────────────────────────────┐
│   📊 RESULTADOS              │
├──────────────────────────────┤
│                              │
│ DBO₅ Salida:        18 mg/L  │
│ ████████░░░░░░░░░░░░░░░░░░  │
│ ✓ Cumple normativa           │
│                              │
│ DQO Salida:         35 mg/L  │
│ ███████░░░░░░░░░░░░░░░░░░░░ │
│ ✓ Cumple normativa           │
│                              │
│ Eficiencia Global:   91%     │
│ █████████████████░░░░░░░░░░  │
│                              │
│ Estado Reactor:              │
│ ● AIREANDO (Verde)           │
│ Ciclo: 75% | 7.5 min         │
│                              │
│ Carga Volumétrica:  0.27     │
│ kg DBO₅/m³·día (ÓPTIMO)      │
│                              │
└──────────────────────────────┘
```

---

## 🧮 FÓRMULAS RÁPIDAS

### Eficiencia
```
Eficiencia = (Entrada - Salida) / Entrada × 100%
```

### Tiempo de Retención
```
TRH (horas) = Volumen Reactor / (Caudal / 24)
```

### Carga Volumétrica
```
Carga = (Caudal × DBO₅) / (1000 × Capacidad)

  Óptimo: 0.2-0.5 kg/m³·día
  Máximo: < 0.8 kg/m³·día
```

### Degradación
```
C_salida = C_entrada × e^(-k × TRH)

  k = 0.15 (con aireación)
  k = 0.03 (sin aireación)
```

---

## 📊 NORMATIVA CHILE DS 90/2000

```
┌──────────────────────────────────┐
│  PARÁMETRO      LÍMITE     ESTADO │
├──────────────────────────────────┤
│  DBO₅           ≤ 35 mg/L  ✓ OK   │
│  DQO            ≤ 75 mg/L  ✓ OK   │
│  Sólidos Susp.  ≤ 30 mg/L  -      │
│  Nitrógeno Tot. ≤ 15 mg/L  -      │
│  Fósforo Tot.   ≤ 2 mg/L   -      │
└──────────────────────────────────┘

Nota: Simulador valida DBO₅ y DQO
```

---

## 🚨 TROUBLESHOOTING EXPRESS

```
❌ "No veo burbujas"
   → Haz clic en "Iniciar Simulación"
   → Verifica que Time ON > 0

❌ "DBO₅ Salida muy alto"
   → Aumenta Time ON (+5 min)
   → Reduce Caudal (-10%)

❌ "Carga Volumétrica > 0.8"
   → REDUCIR CAUDAL INMEDIATAMENTE
   → O cambiar a planta mayor

❌ "Simulador muy lento"
   → Cierra otras pestañas
   → Actualiza navegador (F5)

❌ "Canvas no aparece"
   → Abre Console (F12)
   → Verifica errores
   → Usa Chrome o Firefox
```

---

## 💾 PRESETS RÁPIDOS (Copiar valores)

### DOMÉSTICA (RTB30)
```
Planta: RTB30 | Caudal: 20 | DBO₅: 200 | DQO: 400
Tiempo ON: 30 | Tiempo OFF: 10
Resultado: DBO₅ Salida ≈ 18 mg/L ✓
```

### INDUSTRIAL LIGERO (RTB40)
```
Planta: RTB40 | Caudal: 30 | DBO₅: 400 | DQO: 900
Tiempo ON: 35 | Tiempo OFF: 8
Resultado: DBO₅ Salida ≈ 30 mg/L ✓
```

### INDUSTRIAL PESADO (RTB60)
```
Planta: RTB60 | Caudal: 40 | DBO₅: 600 | DQO: 1400
Tiempo ON: 45 | Tiempo OFF: 10
Resultado: DBO₅ Salida ≈ 35 mg/L ✓ (LÍMITE)
```

### SOBRECARGA (RTB20) ⚠️
```
Planta: RTB20 | Caudal: 35 | DBO₅: 300 | DQO: 600
Tiempo ON: 30 | Tiempo OFF: 10
Resultado: DBO₅ Salida ≈ 95 mg/L ✗ (NO CUMPLE)
Solución: Cambiar a RTB40 mínimo
```

---

## ⏱️ CICLOS RECOMENDADOS

```
┌──────────────┬────────┬────────┬──────────┐
│  Aplicación  │ ON     │ OFF    │ Ratio    │
├──────────────┼────────┼────────┼──────────┤
│  Doméstica   │ 25-35  │ 8-12   │ 3:1-4:1  │
│  Industrial  │ 35-45  │ 8-10   │ 3.5:1    │
│  Nitrif./Des │ 20-30  │ 15-20  │ 1.5:1    │
│  Alta carga  │ 40-60  │ 5-8    │ 5:1-8:1  │
└──────────────┴────────┴────────┴──────────┘

Recomendación: ON:OFF = 3:1 a 4:1 es óptimo
```

---

## 📈 INTERPRETACIÓN DE GAUGES

```
┌─────────────────────────────────────┐
│  GAUGE VALUE    ESTADO      ACCIÓN  │
├─────────────────────────────────────┤
│                                     │
│  DBO₅ Salida                        │
│  < 20 mg/L      Excelente   ✓ OK   │
│  20-35 mg/L     Bueno       ✓ OK   │
│  35-50 mg/L     Alerta      ⚠️ Act │
│  > 50 mg/L      Crítico     🔴 SOS │
│                                     │
│  Eficiencia                         │
│  > 90%          Excelente   ✓ OK   │
│  85-90%         Bueno       ✓ OK   │
│  75-85%         Alerta      ⚠️ Act │
│  < 75%          Crítico     🔴 SOS │
│                                     │
│  Carga Vol.                         │
│  < 0.3          Excelente   ✓ OK   │
│  0.3-0.5        Óptimo      ✓ OK   │
│  0.5-0.8        Aceptable   ✓ OK   │
│  > 0.8          Crítico     🔴 SOS │
│                                     │
└─────────────────────────────────────┘
```

---

## 🔄 CICLO DE AIREACIÓN

```
TIEMPO →

┌─────────────────────────────┐
│ Tiempo ON: 30 minutos       │  Aireación Activa (Aeróbico)
│ Sopladores: ◆◆◆◆◆◆◆◆       │  • Burbujas visibles
│ Estado: ● AIREANDO (Verde)  │  • DBO₅ decrece rápido
└─────────────────────────────┘
         ↓↓↓ (Transición)
┌─────────────────────────────┐
│ Tiempo OFF: 10 minutos      │  Reposo (Anóxico)
│ Sopladores: (apagados)      │  • Sin burbujas
│ Estado: ● EN REPOSO (Ámbar) │  • Procesos desnitrificación
└─────────────────────────────┘
         ↓↓↓ (Regresa a ON)
```

---

## 🎯 METAS DE CUMPLIMIENTO

```
PARA CUMPLIR NORMATIVA DS 90/2000:

Objetivo 1: DBO₅ Salida ≤ 35 mg/L
└─ Meta: < 20 mg/L (con holgura)
└─ Cómo: Aumentar ciclo ON o reducir caudal

Objetivo 2: DQO Salida ≤ 75 mg/L
└─ Meta: < 50 mg/L (con holgura)
└─ Cómo: Misma acción que DBO₅

Objetivo 3: Eficiencia ≥ 85%
└─ Meta: ≥ 90% (recomendado)
└─ Cómo: Optimizar ciclo ON/OFF

Objetivo 4: Carga Vol. < 0.5
└─ Meta: 0.2-0.4 kg/m³·día (óptimo)
└─ Cómo: Mantener caudal apropiado
```

---

## 📱 ATAJOS DE TECLADO

```
F12         Abrir consola (debugging)
Ctrl+F5     Limpiar caché + recargar
Ctrl+Shift+I  DevTools (Inspector)
Escape      Cerrar cualquier panel
Tab         Navegar entre sliders
```

---

## 🌐 NAVEGADORES RECOMENDADOS

```
✅ RECOMENDADOS (100% compatible)
   • Chrome 125+
   • Firefox 123+
   • Safari 17+
   • Edge 125+

⚠️ FUNCIONA (con limitaciones)
   • Opera 111+
   • Brave (basado Chrome)

❌ NO COMPATIBLE
   • Internet Explorer (obsoleto)
   • Navegadores móviles antiguos
```

---

## 💡 TIPS PROFESIONALES

```
TIP 1: Prueba incremental
  └─ Aumenta caudal 5 m³ cada vez
  └─ Observa cómo cambian resultados

TIP 2: Ciclo ON:OFF = 3:1 es oro
  └─ 30 ON / 10 OFF = excelente inicio
  └─ Ajusta desde ahí

TIP 3: Normativa primero
  └─ Cumple DBO₅ y DQO antes que optimizar
  └─ Energía es secundario

TIP 4: Documenta configuraciones
  └─ Anota ciclo ganador
  └─ Úsalo como baseline

TIP 5: Sensibilidad a caudal
  └─ Mayor impacto que tiempo ON
  └─ Ajusta caudal primero
```

---

## 📞 ¿NECESITAS AYUDA?

```
DOCUMENTACIÓN COMPLETA
  → Abre: DOCUMENTACION.md

INICIO RÁPIDO
  → Abre: INICIO_RAPIDO.md

CASOS DE ESTUDIO
  → Abre: PRESETS_CASOS.md

DIAGRAMA DEL SISTEMA
  → Abre: diagrama_flujo.html

ESPECIFICACIONES
  → Abre: RESUMEN.txt o README.md
```

---

## ✨ ¡DISFRUTA SIMULANDO!

```
╔═════════════════════════════════════╗
║                                     ║
║  GEMELO DIGITAL - RTB/SALFA        ║
║                                     ║
║  Simula → Aprende → Optimiza        ║
║                                     ║
║  v1.0 (Enero 2026)                  ║
║                                     ║
╚═════════════════════════════════════╝
```
