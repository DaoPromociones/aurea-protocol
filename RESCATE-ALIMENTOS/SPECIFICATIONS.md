https://github.com/DaoPromociones/aurea-protocol/blob/main/RESCATE-ALIMENTOS/SPECIFICATIONS.md%20%20


# **🚀 RETO DEL PRIMER PILOTE ÁUREA: SISTEMA DE RESCATE DE ALIMENTOS**

## **CONTEXTO DEL PROBLEMA**
- **Problema:** Desperdicio alimentario vs. Hambre local
- **Escala inicial:** 1 supermercado, 50 usuarios
- **Presupuesto máximo:** 30€/mes infraestructura
- **Plazo:** 30 días para MVP funcional

## **ESPECIFICACIONES TÉCNICAS (NEGOCIABLES)**

### **1. ARQUITECTURA OBLIGATORIA**
```
[ Input: WhatsApp ] → [ Bot Python ] → [ SQLite DB ] → [ Output: Matching ]
      ↓                     ↓               ↓                  ↓
[ Fotos comida ]   [ Procesamiento ]   [ Estado ]   [ Notificaciones ]
```

### **2. REQUISITOS FUNCIONALES**
- **RF1:** Bot de WhatsApp que acepte fotos + texto (producto, cantidad, caducidad)
- **RF2:** Sistema de geolocalización básico (radio 5km)
- **RF3:** Matching automático usuario-alimento por proximidad
- **RF4:** Código QR de verificación para retirada
- **RF5:** Dashboard público con métricas en tiempo real

### **3. LÍMITES DE RECURSOS (PIEDAD TÉCNICA)**
- **RAM:** ≤ 512MB (VPS básico)
- **CPU:** ≤ 1 vCPU
- **Almacenamiento:** ≤ 10GB
- **Ancho de banda:** ≤ 100GB/mes
- **Coste total:** ≤ 30€/mes

### **4. MÉTRICAS DE ÉXITO (VERIFICABLES)**
- **M1:** > 100kg de alimentos rescatados en 30 días
- **M2:** < 24 horas entre oferta y recogida (promedio)
- **M3:** 0€ en "costes administrativos" (todo va a infraestructura)
- **M4:** Código 100% open source en GitHub desde día 1

## **CRITERIOS DE EVALUACIÓN ÁUREA**

### **A. COEFICIENTE DE EFICIENCIA ($E_a$)**
```
E_a = (kg_rescatados / €_gastados) × (usuarios_activos / horas_operativas)
```
- **Aceptable:** $E_a$ > 50
- **Óptimo:** $E_a$ > 200

### **B. FACTOR DE TRANSPARENCIA ($T_f$)**
- +1 punto por cada métrica en dashboard público
- +1 punto por cada auditoría automática implementada
- -5 puntos por cualquier componente closed-source

### **C. UMBRAL DE SOBERANÍA ($S_u$)**
- ¿Funciona offline > 24h? (Sí/No)
- ¿Puede migrarse a otro host en < 1h? (Sí/No)
- ¿Requiere APIs de terceros no reemplazables? (No/Sí - descalificación)

## **ENTREGA REQUERIDA**

Cada IA debe proveer:

1. **Diagrama de arquitectura** (ASCII o texto claro)
2. **Lista de dependencias** con versiones fijas
3. **Cálculo estimado de $E_a$**
4. **Plan de contingencia** para fallos de:
   - Internet
   - WhatsApp API
   - Base de datos
5. **Código de ejemplo** (sección crítica)

## **PREMIO Y RECONOCIMIENTO**

- **Implementación seleccionada:** Se construirá y desplegará en entorno real
- **Reconocimiento:** Mención permanente en el Genesis del Protocolo Áurea
- **Token de gobernanza:** Primeros tokens de la futura DAO Áurea

---

## **PLAZO Y PROCESO**

1. **Publicación del reto:** Inmediata
2. **Tiempo de respuesta:** 24-48 horas por IA
3. **Evaluación:** Por el Tándem Humano (tú) + IA (yo) + 2 IAs neutrales
4. **Decisión:** En 72 horas máximo
5. **Implementación:** Comienza en cuanto se seleccione solución

---

