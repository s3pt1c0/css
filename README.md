# 🎨 LOGOS PARA CÓDIGO BLE - GUÍA RÁPIDA

---

## ✅ PASOS SIMPLES:

### PASO 1: Subir CSS a GitHub

**Opción A: GitHub normal**
```
1. Ve a GitHub.com
2. Crea repo público (o usa uno existente)
3. Sube el archivo: victron-custom.css
4. Abre el archivo en GitHub
5. Click botón "Raw"
6. Copia la URL completa
```

**Opción B: GitHub Gist (más rápido)**
```
1. Ve a https://gist.github.com
2. Pega el contenido de victron-custom.css
3. Nombre: victron-custom.css
4. Click "Create public gist"
5. Click "Raw"
6. Copia la URL
```

**Ejemplo de URL que obtendrás:**
```
https://raw.githubusercontent.com/tu-usuario/repo/main/victron-custom.css

o

https://gist.githubusercontent.com/tu-usuario/abc123/raw/victron-custom.css
```

---

### PASO 2: Editar YAML

**Abre:** `maria-victron-ble-v1.3.yaml`

**Busca la línea 36-37:**
```yaml
# TEMPORAL: Deja vacío hasta que subas el CSS
css_url: ""
```

**Cámbiala por:**
```yaml
css_url: "https://raw.githubusercontent.com/TU-USUARIO/TU-REPO/main/victron-custom.css"
```

**IMPORTANTE:** Reemplaza con TU URL que copiaste en el paso 1.

---

### PASO 3: Compilar y Subir

```bash
# Compilar
esphome compile maria-victron-ble-v1.3.yaml

# Subir al ESP32
esphome upload maria-victron-ble-v1.3.yaml --device 192.168.75.11

# O todo junto
esphome run maria-victron-ble-v1.3.yaml --device 192.168.75.11
```

---

### PASO 4: Ver Resultado

**Abre en navegador:**
```
http://192.168.75.11
```

**Deberías ver:**
```
┌────────────────────────────────────────┐
│ [Victron Logo]      [Espressif Logo]  │
├────────────────────────────────────────┤
│ Victron ESP32 BLE MSOIR                │
│                                        │
│ Battery Voltage: 13.79 V               │
│ PV Power: 850 W                        │
│ PV Voltage (Estimated): 80.0 V         │
│ ...                                    │
└────────────────────────────────────────┘
```

---

## 🎯 ARCHIVO CSS (victron-custom.css)

**Usa el mismo CSS que te di antes:**
- Logo Victron (izquierda)
- Logo Espressif (derecha)
- Responsive design
- Colores por estado

**Archivo:** `victron-custom.css` (ya lo tienes descargado)

---

## 📋 EJEMPLO COMPLETO:

### 1. URL de tu CSS en GitHub:
```
https://raw.githubusercontent.com/franky-solar/esphome/main/victron-custom.css
```

### 2. Tu YAML actualizado:
```yaml
web_server:
  port: 80
  css_url: "https://raw.githubusercontent.com/franky-solar/esphome/main/victron-custom.css"
```

### 3. Resultado en navegador:
```
http://192.168.75.11
→ Logos aparecen ✅
→ Sensores BLE funcionando ✅
```

---

## 🔧 DIFERENCIAS BLE vs VE.Direct:

| Aspecto | BLE (este código) | VE.Direct |
|---------|-------------------|-----------|
| **Conexión** | Bluetooth | Cable serial |
| **Sensores** | ~11 | ~30+ |
| **Panel Voltage** | Estimado (80V) | REAL (varía) |
| **Logos CSS** | ✅ Sí | ✅ Sí |
| **Web server** | ✅ Sí | ✅ Sí |

**Los logos funcionan en AMBOS** ✅

---

## 💡 VENTAJAS DE TENER AMBOS:

### BLE (actual):
```
✅ Sin cables
✅ Fácil de instalar
✅ Monitoreo móvil (VictronConnect)
✅ Ahora con logos bonitos
```

### VE.Direct (futuro):
```
✅ Datos completos
✅ Panel Voltage REAL
✅ Más sensores
✅ También con logos
```

**Puedes tener ambos ESP32 funcionando simultáneamente** 👍

---

## ✅ CHECKLIST:

```
Pre-instalación:
□ victron-custom.css descargado
□ Cuenta de GitHub (o Gist)

Paso 1 - Subir CSS:
□ CSS subido a GitHub/Gist
□ URL "Raw" obtenida y copiada
□ URL probada en navegador

Paso 2 - Editar YAML:
□ maria-victron-ble-v1.3.yaml abierto
□ Línea ~37 encontrada
□ css_url actualizado con tu URL
□ Archivo guardado

Paso 3 - Compilar:
□ ESPHome instalado
□ Compilación exitosa
□ Upload completado

Paso 4 - Verificar:
□ http://192.168.75.11 accesible
□ Logo Victron visible (izquierda)
□ Logo Espressif visible (derecha)
□ Sensores BLE funcionando
```

---

## 🎨 RESULTADO FINAL:

**BLE + Logos = Web server profesional** ✨

```
http://192.168.75.11

Características:
✅ Logo Victron Energy (izquierda)
✅ Logo Espressif ESP32 (derecha)
✅ Monitoreo BLE inalámbrico
✅ Sensores de batería y paneles
✅ Uptime formateado
✅ Diseño responsive
✅ Fácil de actualizar CSS
```

---

## 📞 SIGUIENTE PASO:

**¿Ya tienes el CSS subido a GitHub?**

Si sí:
```yaml
css_url: "TU-URL-AQUI"
```

Si no:
```
1. Ve a gist.github.com
2. Pega victron-custom.css
3. Crea gist público
4. Copia URL "Raw"
5. Pégala en css_url
```

---

**Versión BLE:** v1.3 (con logos)  
**CSS:** Mismo que VE.Direct  
**Compatible:** ESP32 + BLE Victron  
**Tiempo instalación:** 5-10 minutos

🎉 **¡Logos también para BLE!** ✨
