# solar-app
# ☀️ Solar Pro — Herramienta de Prefactibilidad Solar

> Herramienta educativa para estudios de prefactibilidad fotovoltaica, desarrollada como material de apoyo para el curso de **Sistemas Fotovoltaicos**. Incluye calculadora, optimizador de paneles, análisis climático y analizador de propuestas con inteligencia artificial.

---

## 🚀 Demo en vivo

👉 (https://valenarias7.github.io/solar-app/))


---

## ✨ Funcionalidades

### 📐 Calculadora de Prefactibilidad
- Residencial y comercial
- 20+ ciudades de Chile, Colombia, México y Perú con datos reales de HSP
- 3 modos: por número de paneles, por presupuesto o por consumo mensual
- Slider de ángulo de inclinación con factor de corrección automático
- Resultados: kWp, generación mensual/anual, ahorro en CLP, Payback, TIR, CO₂ evitado, LCOE, beneficio neto a 25 años

### 🔲 Paneles Óptimos
- Comparativa automática de 3 opciones de potencia (400 / 550 / 670 Wp)
- Calcula cuántos paneles caben según el área disponible
- **Layout visual** en canvas: distribución real de paneles en el techo (filas × columnas)
- Estimación de potencia total, generación y costo por opción

### 🌤️ Clima Solar
- Gráfico de irradiación mensual (kWh/m²/día) por ciudad
- Efecto de temperatura en el rendimiento de los paneles (pérdida por NOCT)
- Rosa de dirección solar óptima según latitud
- Comparativa generación estimada vs consumo del usuario

### 🤖 Analizador de Propuestas con IA
- Sube 1 o 2 propuestas en PDF
- Claude AI extrae automáticamente datos técnicos y financieros
- Detecta el tipo de contrato: **EPC** (compra directa) o **PPA** (acuerdo de energía)
- Tabla comparativa lado a lado con ganador por parámetro
- Scores técnico, financiero y de condiciones
- Escenario óptimo de paneles recomendado
- **Recomendación final** con argumentos, advertencias y próximos pasos

### 📖 Glosario Fotovoltaico
12 conceptos clave: HSP, kWp, STC, NOCT, Inversor, PR, Net Metering, LCOE, Irradiancia, MPPT, PPA, EPC

### 📚 Guía de Sesiones
Resumen de los 8 módulos del curso de Sistemas Fotovoltaicos

---

## 🏙️ Ciudades incluidas

| País | Ciudades |
|------|----------|
| 🇨🇱 Chile | Arica, Iquique, Antofagasta, Calama, Copiapó, La Serena, Valparaíso, Santiago, Rancagua, Talca, Concepción, Temuco, Valdivia, Puerto Montt, Punta Arenas |
| 🇨🇴 Colombia | Barranquilla, Bogotá, Medellín |
| 🇲🇽 México | Ciudad de México |
| 🇵🇪 Perú | Lima |

---

## ⚙️ Tecnología

- HTML5 + CSS3 + JavaScript puro (sin frameworks)
- Google Maps API (búsqueda de direcciones + mapa satelital + dibujo de polígono)
- Anthropic Claude API (análisis de propuestas PDF)
- Canvas API (layout visual de paneles)
- Sin backend — todo corre en el navegador

---

## 🛠️ Instalación local

```bash
# Clona el repositorio
git clone https://github.com/tu-usuario/solar-app.git
cd solar-app

# Abre en un servidor local (necesario para Google Maps)
npx serve .
# o con Python:
python -m http.server 8000
```

Luego abre `http://localhost:8000` en tu navegador.

> ⚠️ **No abras el archivo directamente** como `file://` — Google Maps requiere HTTP/HTTPS para funcionar correctamente.

---

## 🔑 API Keys

La app usa dos APIs externas:

| API | Para qué se usa | Cómo configurar |
|-----|----------------|-----------------|
| Google Maps JavaScript API | Búsqueda de direcciones, mapa satelital, dibujo de polígono | Reemplaza `YOUR_GOOGLE_API_KEY` en el HTML |
| Anthropic Claude API | Análisis de propuestas PDF | Configurada en el backend del proxy |

### Restricción de la Google Maps API Key
Para evitar uso no autorizado, restringe tu key en [Google Cloud Console](https://console.cloud.google.com):
1. Ir a **APIs & Services → Credentials**
2. Seleccionar tu API key
3. En **Application restrictions** → HTTP referrers
4. Agregar: `https://tu-usuario.github.io/*`

---

## 📊 Parámetros del modelo

| Parámetro | Valor | Fuente |
|-----------|-------|--------|
| Tarifa eléctrica ref. | $145 CLP/kWh | Promedio residencial Chile 2024 |
| Performance Ratio (PR) | 78% | Estándar industria |
| Degradación anual | 0.5% | Fabricantes tier-1 |
| Factor CO₂ | 0.29 kg/kWh | Factor emisión SIC Chile |
| Precio panel (ref.) | US$0.25/Wp | Mercado internacional 2024 |
| Factor instalación | ×1.45 | Incluye inversor + instalación |
| Tipo de cambio | $950 CLP/USD | Referencia |

---

## ⚠️ Aviso importante

Esta es una **herramienta educativa y referencial**. Los valores entregados son estimaciones basadas en promedios históricos de radiación solar, tarifas vigentes y precios de mercado. **No constituye ingeniería de proyecto.** Para una instalación real se requiere:

- Estudio de ingeniería con medición de irradiación in situ
- Análisis de sombras 3D
- Evaluación estructural del techo
- Cotización formal de equipos certificados
- Trámites ante la distribuidora eléctrica correspondiente

---

## 📄 Licencia

Desarrollado con fines educativos para el curso de Sistemas Fotovoltaicos.

---

*Construido con ☀️ y Claude AI*
