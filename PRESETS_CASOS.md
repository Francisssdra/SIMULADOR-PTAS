# 🎛️ PRESETS Y CASOS DE ESTUDIO

## Configuraciones Pre-definidas para Simulador RTB/SALFA

### 📋 Cómo usar los presets

1. Abre `index.html` en el navegador
2. Copia los valores de la tabla correspondiente a cada slider
3. Haz clic en **▶ Iniciar Simulación**
4. Compara resultados en el panel derecho

---

## 📌 PRESET 1: Agua Residual Doméstica (TÍPICA)

**Descripción:** Configuración estándar para efluente de viviendas/edificios

| Parámetro | Valor | Nota |
|-----------|-------|------|
| **Planta** | RTB30 | 30 m³ |
| **Caudal** | 20 m³/día | ~833 L/h |
| **DBO₅ Entrada** | 200 mg/L | Aguas grises típicas |
| **DQO Entrada** | 400 mg/L | Relación DQO/DBO₅ ≈ 2 |
| **Time ON** | 30 min | Aireación activa |
| **Time OFF** | 10 min | Fase anóxica |

**Resultados Esperados:**
```
✅ DBO₅ Salida: 12–18 mg/L (CUMPLE)
✅ DQO Salida: 30–45 mg/L (CUMPLE)
✅ Eficiencia: 91–94%
✅ Carga Volumétrica: 0.27 kg/m³·día (ÓPTIMO)
📊 Estado: EXCELENTE
```

**Análisis:**
- Planta bien dimensionada para caudal
- Ciclo equilibrado ON:OFF = 3:1
- Carga volumétrica en rango óptimo
- Cumple holgadamente normativa DS 90/2000

---

## 📌 PRESET 2: Agua Residual Industrial Ligera

**Descripción:** Efluentes de industrias de alimentos, bebidas, textiles

| Parámetro | Valor | Nota |
|-----------|-------|------|
| **Planta** | RTB40 | 40 m³ |
| **Caudal** | 30 m³/día | Carga moderada |
| **DBO₅ Entrada** | 400 mg/L | Industrial típica |
| **DQO Entrada** | 900 mg/L | DQO/DBO₅ ≈ 2.25 |
| **Time ON** | 35 min | Aireación extendida |
| **Time OFF** | 8 min | Fase corta |

**Resultados Esperados:**
```
✅ DBO₅ Salida: 28–35 mg/L (CUMPLE-LÍMITE)
✅ DQO Salida: 60–75 mg/L (CUMPLE-LÍMITE)
✅ Eficiencia: 87–91%
✅ Carga Volumétrica: 0.45 kg/m³·día (ACEPTABLE)
📊 Estado: CUMPLE (con margen reducido)
```

**Análisis:**
- Carga más exigente requiere ciclo ON más largo
- Eficiencia adecuada pero cercana a límite
- Monitor frecuentemente DBO₅ salida
- Considerar pre-tratamiento si DBO₅ entrada sube

---

## 📌 PRESET 3: Agua Residual Industrial Pesada

**Descripción:** Efluentes complejos (curtiembres, lecherías, mataderos)

| Parámetro | Valor | Nota |
|-----------|-------|------|
| **Planta** | RTB60 | 60 m³ (máxima capacidad) |
| **Caudal** | 40 m³/día | Carga significativa |
| **DBO₅ Entrada** | 600 mg/L | Industrial pesada |
| **DQO Entrada** | 1400 mg/L | DQO/DBO₅ ≈ 2.33 |
| **Time ON** | 45 min | Aireación máxima |
| **Time OFF** | 10 min | Mantenimiento anóxico |

**Resultados Esperados:**
```
✅ DBO₅ Salida: 32–40 mg/L (CUMPLE-MARGINAL)
✅ DQO Salida: 70–85 mg/L (CERCANO-LÍMITE)
✅ Eficiencia: 83–88%
✅ Carga Volumétrica: 0.67 kg/m³·día (MÁXIMO)
⚠️ Estado: CUMPLE (OPERACIÓN CRÍTICA)
```

**Análisis:**
- Planta trabajando a máxima capacidad
- Ciclo ON largo para degradar contaminantes
- Eficiencia menor por sobrecarga
- **RECOMENDACIÓN:** Pre-tratamiento obligatorio o segunda planta

---

## 📌 PRESET 4: Escenario de SOBRECARGA (Para Aprender)

**Descripción:** Demostración de planta sub-dimensionada

| Parámetro | Valor | Nota |
|-----------|-------|------|
| **Planta** | RTB20 | 20 m³ (PEQUEÑA) |
| **Caudal** | 35 m³/día | **¡EXCEDE 1.75×!** |
| **DBO₅ Entrada** | 300 mg/L | Normal |
| **DQO Entrada** | 600 mg/L | Normal |
| **Time ON** | 30 min | Insuficiente |
| **Time OFF** | 10 min | Insuficiente |

**Resultados Esperados:**
```
❌ DBO₅ Salida: 85–120 mg/L (EXCEDE 2–3×)
❌ DQO Salida: 180–250 mg/L (EXCEDE 2–3×)
❌ Eficiencia: 55–60% (INSUFICIENTE)
❌ Carga Volumétrica: 1.05 kg/m³·día (CRÍTICA)
🔴 Estado: NO CUMPLE - FALLO OPERACIONAL
```

**Análisis:**
- Factor de penalización activo (Q > 1.5 × Cap)
- Imposible cumplir normativa
- Incluso aumentando Time ON (máx 60 min) no cumplirá
- **SOLUCIÓN:** Cambiar a RTB40 o RTB60

---

## 📌 PRESET 5: Optimización de Ciclo ON/OFF

**Descripción:** Encontrar relación ON:OFF óptima

### Variante A: ON:OFF = 5:1 (muy aeróbico)

| Parámetro | Valor |
|-----------|-------|
| **Planta** | RTB30 |
| **Caudal** | 20 m³/día |
| **DBO₅ Entrada** | 200 mg/L |
| **DQO Entrada** | 400 mg/L |
| **Time ON** | 40 min |
| **Time OFF** | 8 min |

**Resultado:** Eficiencia ↑ 95–96% (MÁX)  
**Costo energético:** ↑ (más soplador)

### Variante B: ON:OFF = 3:1 (ÓPTIMO)

| Parámetro | Valor |
|-----------|-------|
| **Planta** | RTB30 |
| **Caudal** | 20 m³/día |
| **DBO₅ Entrada** | 200 mg/L |
| **DQO Entrada** | 400 mg/L |
| **Time ON** | 30 min |
| **Time OFF** | 10 min |

**Resultado:** Eficiencia ≈ 91% (EQUILIBRIO)  
**Costo energético:** ≈ Medio (RECOMENDADO)

### Variante C: ON:OFF = 2:1 (más anóxico)

| Parámetro | Valor |
|-----------|-------|
| **Planta** | RTB30 |
| **Caudal** | 20 m³/día |
| **DBO₅ Entrada** | 200 mg/L |
| **DQO Entrada** | 400 mg/L |
| **Time ON** | 20 min |
| **Time OFF** | 10 min |

**Resultado:** Eficiencia ↓ 82–85%  
**Costo energético:** ↓ (menos soplador)  
**Nitrógeno:** Mejor remoción (desnitrificación)

**Conclusión:** Preset B (3:1) es mejor relación eficiencia/energía

---

## 📌 PRESET 6: Estudio de Sensibilidad - DBO₅ Entrada

**Mantener:** RTB30, 20 m³/día, Ciclo 30:10

| DBO₅ Entrada | DBO₅ Salida | Eficiencia |
|--------------|------------|-----------|
| 50 mg/L | 5 mg/L | 90% |
| 200 mg/L | 18 mg/L | 91% |
| 400 mg/L | 35 mg/L | 91% |
| 800 mg/L | 72 mg/L | 91% |

**Conclusión:**  
- Modelo exponencial: eficiencia es **independiente** de concentración entrada
- DBO₅ salida **escala linealmente** con DBO₅ entrada
- Mismo ciclo funciona para rangos amplios

---

## 📌 PRESET 7: Estudio de Sensibilidad - Caudal

**Mantener:** RTB30, DBO₅=200, Ciclo 30:10

| Caudal (m³/día) | DBO₅ Salida | TRH (h) | Factor |
|-----------------|------------|---------|--------|
| 10 | 8 mg/L | 36 | Normal |
| 15 | 12 mg/L | 24 | Normal |
| 20 | 18 mg/L | 18 | Normal |
| 30 | 28 mg/L | 12 | Normal |
| 45 (sobrecarga) | 85 mg/L | 8 | **×0.3** |

**Conclusión:**
- TRH ↓ cuando caudal ↑
- A partir de Q > 1.5 × Capacidad: eficiencia cae 70%
- RTB30 soporta hasta ~33 m³/día (con margen)

---

## 📌 PRESET 8: Recuperación de Falla

**Escenario:** Planta llegó a sobrecarga, ahora la normalizamos

### Fase 1: CRISIS (RTB30 con 35 m³/día)
```
DBO₅ Salida: 95 mg/L ❌
Acción: REDUCIR caudal inmediatamente
```

### Fase 2: RECUPERACIÓN (RTB30 con 25 m³/día)
```
DBO₅ Salida: 25 mg/L ✅
Acción: Esperar 48 h para estabilización biomasa
```

### Fase 3: NORMAL (RTB30 con 20 m³/día)
```
DBO₅ Salida: 18 mg/L ✅
Acción: Monitorear y mantener ciclo 30:10
```

---

## 📊 TABLA RESUMEN: CAPACIDADES RECOMENDADAS

| Caudal (m³/día) | RTB Recomendada | Margen | Eficiencia Esperada |
|-----------------|-----------------|--------|-------------------|
| 10–15 | RTB20 | Alto | 92–94% |
| 15–25 | RTB30 | Medio | 90–92% |
| 25–35 | RTB40 | Medio | 89–91% |
| 35–55 | RTB60 | Medio | 88–90% |
| > 55 | RTB60 + 2da Planta | - | 88–90% cada una |

---

## 🧪 EXPERIMENTOS SUGERIDOS

### Experimento 1: Efecto del Ciclo de Aireación
1. RTB30, 20 m³/día, DBO₅=200
2. Varía Time ON: 20 → 30 → 40 → 50 min (Time OFF = 10)
3. Gráfico: Eficiencia vs. Time ON
4. Observación: Eficiencia sube pero con rendimientos decrecientes

### Experimento 2: Máximo Caudal Seguro
1. RTB30, DBO₅=200, DQO=400, Ciclo 30:10
2. Aumenta Caudal: 10 → 20 → 30 → 40 m³/día
3. Registra cuándo DBO₅ Salida > 35 mg/L
4. Conclusión: Límite seguro ≈ 30 m³/día

### Experimento 3: Compromiso Energía vs. Eficiencia
1. RTB30, 20 m³/día, DBO₅=200
2. Ciclo A: 20 ON / 10 OFF (baja energía)
3. Ciclo B: 30 ON / 10 OFF (media energía)
4. Ciclo C: 40 ON / 10 OFF (alta energía)
5. Análisis: ¿Vale la pena?

---

## 📝 NOTAS IMPORTANTES

**Nota 1:** DQO Salida ≈ 2 × DBO₅ Salida (relación lineal)

**Nota 2:** Si DBO₅ salida está ROJA (> 35):
- Aumenta Time ON primero
- Si no funciona, reduce Caudal
- Como último recurso, cambiar planta mayor

**Nota 3:** Carga Volumétrica = (Q × DBO₅_in) / (1000 × Capacidad)
- Óptimo: 0.2–0.5
- Máximo soportable: < 0.8
- Crítico: > 0.8

**Nota 4:** Normativa Chilena DS 90/2000 (MOP):
- DBO₅ ≤ 35 mg/L (OBLIGATORIO)
- DQO ≤ 75 mg/L (OBLIGATORIO)
- Este simulador usa estos límites

**Nota 5:** Ciclo ON:OFF típico:
- Aeróbico: 3–4 horas de aire
- Anóxico: 1–1.5 horas sin aire
- En horas = mantener proporción 3:1 a 4:1

---

**Última actualización:** Enero 2026  
**Versión:** 1.0 — Presets y Casos de Estudio
