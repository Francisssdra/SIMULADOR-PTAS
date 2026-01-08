# 🚀 INICIO RÁPIDO - Gemelo Digital RTB/SALFA

## En 30 segundos...

### 1️⃣ Abrir
- Haz doble-clic en **`index.html`**
- Se abrirá en tu navegador por defecto

### 2️⃣ Configurar (2 minutos)
```
Panel Izquierdo:
├─ Planta: RTB30 (por defecto)
├─ Caudal: 20 m³/día (típico)
├─ DBO₅: 250 mg/L (aguas grises)
├─ DQO: 500 mg/L
├─ Time ON: 30 minutos
└─ Time OFF: 10 minutos
```

### 3️⃣ Simular
- Click en **▶ Iniciar Simulación**
- Observa las burbujas en los reactores ↑↑↑
- Los valores cambian en TIEMPO REAL

### 4️⃣ Analizar
Panel Derecho mostrará:
- ✅ DBO₅ Salida < 35 mg/L → CUMPLE NORMATIVA
- ✅ Eficiencia Global > 85% → EXCELENTE
- 🟢 Estado: AIREANDO (verde) o EN REPOSO (ámbar)

---

## 📊 CASOS DE USO TÍPICOS

### Caso 1: Agua Residual Doméstica (RTB30)
```javascript
Caudal: 20 m³/día
DBO₅: 200 mg/L
DQO: 400 mg/L
Ciclo: 30 min ON / 10 min OFF

RESULTADO ESPERADO:
✓ DBO₅ Salida: ~15 mg/L
✓ Eficiencia: ~92%
✓ Estado: CUMPLE
```

### Caso 2: Agua Residual Industrial (RTB40)
```javascript
Caudal: 35 m³/día
DBO₅: 500 mg/L
DQO: 1000 mg/L
Ciclo: 40 min ON / 8 min OFF

RESULTADO ESPERADO:
✓ DBO₅ Salida: ~35 mg/L (LÍMITE)
✓ Eficiencia: ~90%
✓ Estado: CUMPLE MARGINAL
```

### Caso 3: Sobrecarga (RTB20)
```javascript
Caudal: 35 m³/día (¡Mayor que capacidad!)
DBO₅: 300 mg/L
DQO: 600 mg/L
Ciclo: 30 min ON / 10 min OFF

RESULTADO ESPERADO:
❌ DBO₅ Salida: ~110 mg/L (EXCEDE)
❌ Eficiencia: ~60% (INSUFICIENTE)
⚠️ Estado: NO CUMPLE - AUMENTAR CAPACI DAD
```

---

## 🎮 CONTROLES INTERACTIVOS

| Control | Rango | Recomendación |
|---------|-------|---------------|
| **Planta** | RTB20–RTB60 | Elegir según caudal |
| **Caudal** | 1–80 m³/día | ≤ 80% capacidad |
| **DBO₅** | 50–1000 mg/L | 200–400 típico |
| **DQO** | 100–2000 mg/L | DQO ≈ 2×DBO₅ |
| **Time ON** | 1–60 min | 25–40 óptimo |
| **Time OFF** | 0–30 min | 5–15 óptimo |

---

## 🎯 OBJETIVOS DE NORMATIVA (Chile DS 90/2000)

Para que panel derecho muestre ✅ CUMPLE:

- **DBO₅ Salida** ≤ 35 mg/L ✓
- **DQO Salida** ≤ 75 mg/L ✓

Si alguno excede → aparece ✗ EXCEDE LÍMITE en ROJO

---

## 🔧 OPTIMIZACIÓN EN 3 PASOS

### Paso 1: Verificar Caudal
```
SI: Caudal > Capacidad × 1.5
ENTONCES: Eficiencia cae 70% (factor de penalización)
SOLUCIÓN: Reducir caudal o cambiar planta mayor
```

### Paso 2: Ajustar Ciclo ON/OFF
```
SI: Eficiencia < 85%
ENTONCES: Aumentar Time ON (máximo +60 min)
O: Aumentar Time ON y reducir Time OFF

Relación típica óptima: ON:OFF = 3:1 a 4:1
```

### Paso 3: Revisar Carga Volumétrica
```
Carga Volumétrica (kg DBO₅/m³·día) = 
  (Caudal × DBO₅_entrada) / (1000 × Capacidad)

ÓPTIMO: 0.2–0.5 kg/m³·día
LÍMITE: < 0.8 kg/m³·día
```

---

## 📈 MONITOREO EN TIEMPO REAL

Mientras la simulación corre:

1. **Canvas Central:** Verás burbujas subiendo 🫧 = aireación activa
2. **Indicador Estado:** Verde (Aireando) ↔ Ámbar (Reposo)
3. **Contador Ciclo:** "Ciclo: 65% | 12.5 min" = Progreso del ciclo
4. **Gauges Derechos:** Valores actualizándose cada 50ms

---

## ⚠️ ALERTAS IMPORTANTES

| Alerta | Causa | Acción |
|--------|-------|--------|
| 🔴 DBO₅ > 35 | Caudal ↑ o Ciclo ON ↓ | Aumentar ON o reducir Q |
| 🔴 DQO > 75 | Carga volumétrica alta | Reducir entrada o planta ↑ |
| 🟡 Eficiencia < 80% | Ciclo desbalanceado | Aumentar Time ON |
| 🟡 Carga Vol. > 0.8 | Sobrecarga | Cambiar a RTB mayor |

---

## 💡 TIPS PROFESIONALES

1. **Prueba incremental:** Aumenta caudal lentamente, observa cambios
2. **Benchmark:** Guarda la configuración de referencia (foto/notas)
3. **Validación:** Compara resultados con datos históricos reales
4. **Documentación:** Anota ciclo ON/OFF óptimo para tu planta
5. **Sensibilidad:** Prueba ±10% en parámetros para ver robustez

---

## 🌐 NAVEGADOR RECOMENDADO

✅ **Chrome 90+**  
✅ **Firefox 88+**  
✅ **Safari 14+**  
✅ **Edge 90+**  

(Canvas 2D + CSS moderno requerido)

---

## 📞 SOPORTE

¿El simulador no funciona?

1. ✓ Verifica que navegador sea moderno (Chrome/Firefox recomendado)
2. ✓ Abre Console (F12 → Console) y copia mensajes de error
3. ✓ Reinicia página (Ctrl+F5 limpia caché)
4. ✓ Verifica que archivo sea `index.html` (no comprimido)

---

**Versión 1.0 — Enero 2026**  
*Desarrollado para Ingenieería Ambiental Aplicada*
