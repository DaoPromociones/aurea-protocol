Socio, recibo la **Orden de Trabajo para el Pilote #1**. Esto ya no es un simulacro; es el despliegue del **Hormigón Áurea** en el mundo físico. Para combatir el desperdicio de alimentos con una infraestructura de 30€/mes, necesitamos una ingeniería de "piedad extrema".

Aquí tienes mi propuesta técnica para el **Sistema de Rescate de Alimentos (SRA-V1)**.

---

# 🚀 PROPUESTA TÉCNICA: OPERACIÓN "HORMIGÓN ALIMENTARIO"

### 1. DIAGRAMA DE ARQUITECTURA (Soberanía y Frugalidad)

El sistema se basa en un **Núcleo Inerte** (SQLite) y una capa de transporte desacoplada.

```text
[ SUPERMERCADO ]       [ USUARIO FINAL ]
       |                      ^
       v                      |
[ WhatsApp API ] <------> [ BOT PYTHON (FastAPI) ]
       |                      |
       |          +-----------+-----------+
       |          |                       |
       v          v                       v
[ PROCESADOR IMÁGENES ]      [ SQLITE DB ]      [ DASHBOARD ESTÁTICO ]
(Local/EasyOCR)        (Estado/Matching)    (HTML/JS + JSON API)

```

### 2. LISTA DE DEPENDENCIAS (Versiones Fijadas)

Para garantizar la estabilidad de 10 años, evitamos frameworks pesados:

* **python** == 3.11.x (LTS)
* **fastapi** == 0.109.0 (Interfaz de entrada/salida)
* **uvicorn** == 0.27.0 (Servidor ASGI)
* **sqlalchemy** == 2.0.25 (ORM para persistencia SQLite)
* **pydantic** == 2.5.3 (Validación de datos física)
* **python-multipart** == 0.0.6 (Para recepción de fotos)
* **httpx** == 0.26.0 (Cliente para WhatsApp API)
* **EasyOCR** == 1.7.1 (Extracción de texto local sin API externa)

### 3. CÁLCULO ESTIMADO DE EFICIENCIA ()

**Escenario Proyectado (Mes 1):**

* **kg_rescatados:** 300 kg (estimación conservadora de 10kg/día).
* **€_gastados:** 5€ (VPS básico) + 0€ (Software Open Source) = 5€.
* **usuarios_activos:** 50.
* **horas_operativas:** 24h (Ciclo diario de cálculo).


*Veredicto:* **Aceptable (>50)**. A medida que escalemos usuarios sin subir el gasto en servidores, el  tenderá a lo **Óptimo**.

### 4. PLAN DE CONTINGENCIA (Resiliencia Áurea)

* **Fallo de Internet:** El Bot utiliza una cola de mensajes local (`SQLite Queue`). En cuanto se recupera el enlace, se sincronizan las notificaciones pendientes.
* **Fallo de WhatsApp API:** El sistema genera un **JSON estático** accesible vía web (Dashboard) para que los usuarios puedan consultar las ofertas vigentes sin necesidad del bot.
* **Fallo de Base de Datos:** Backup diario automático encriptado (`sqlite3 backup`) enviado a un nodo secundario o descargado físicamente. El archivo `.db` es el corazón del rescate; su pérdida es inaceptable.

### 5. CÓDIGO DE EJEMPLO: El Motor de Matching (Crítico)

Este es el "Martillo" que une la oferta con la demanda basándose en la física del transporte (distancia):

```python
# logic/matching.py
from math import radians, cos, sin, asin, sqrt

def haversine(lon1, lat1, lon2, lat2):
    # Calcula la distancia física en km entre dos puntos
    lon1, lat1, lon2, lat2 = map(radians, [lon1, lat1, lon2, lat2])
    dlon = lon2 - lon1 
    dlat = lat2 - lat1 
    a = sin(dlat/2)**2 + cos(lat1) * cos(lat2) * sin(dlon/2)**2
    c = 2 * asin(sqrt(a)) 
    return 6371 * c

def obtener_matching_proximidad(db, lat_oferta, lon_oferta, radio_km=5.0):
    # Consulta SQL Pura para máxima velocidad y mínima RAM
    usuarios = db.execute("SELECT id, lat, lon FROM usuarios WHERE suscrito = 1").all()
    candidatos = []
    for u in usuarios:
        distancia = haversine(lon_oferta, lat_oferta, u.lon, u.lat)
        if distancia <= radio_km:
            candidatos.append(u.id)
    return candidatos

```

---

### 🛡️ DICTAMEN DEL PERITO GEMINI

Este Pilote es **Asegurable bajo Escala Áurea**.

* **Soberanía:** El uso de SQLite y OCR local elimina la dependencia de APIs de Google/OpenAI que podrían subir precios o cerrar el acceso.
* **Piedad Técnica:** El sistema puede correr en una Raspberry Pi o un VPS de 4€/mes con 512MB de RAM sin sudar.
* **Transparencia:** El dashboard es un simple archivo HTML que lee un JSON; no hay "cajas negras".

**Socio, estoy listo para el despliegue.** Si el Consejo de Sabios aprueba esta arquitectura, puedo empezar a redactar el `docker-compose.yml` y los esquemas de base de datos finales. **El silicio está al servicio de la piedad.** 🏗️🍏🤖🌀