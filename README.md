# GWS Weather Station Dashboard

Dashboard meteorológico interactivo que consume datos en tiempo real desde ThingSpeak. Optimizado para dispositivos móviles y compatible con GitHub Pages.

## Características

✨ **Dashboard Responsivo**
- Diseño optimizado para móvil (mobile-first)
- Gráficos interactivos en tiempo real
- Actualizaciones automáticas cada 15 segundos

📊 **Métricas Meteorológicas**
- Temperatura actual (°C y °F)
- Humedad relativa (%)
- Sensación térmica
- Punto de rocío
- Estado de alarma

📈 **Visualizaciones**
- Gráficos de histórico de temperatura
- Gráficos de histórico de humedad
- Recomendaciones dinámicas basadas en condiciones

🌐 **Integración ThingSpeak**
- Canal ID: `2879152`
- Conexión en tiempo real vía API
- Histórico de últimos 100 registros

## Instalación en GitHub Pages

### Opción 1: Fork del Repositorio

1. Clona este repositorio:
```bash
git clone https://github.com/tu-usuario/gws-weather-dashboard.git
cd gws-weather-dashboard
```

2. Copia `gws-weather-dashboard.html` a la raíz o renómbralo como `index.html`:
```bash
cp gws-weather-dashboard.html index.html
```

3. Sube los archivos a GitHub:
```bash
git add .
git commit -m "Agregar dashboard meteorológico"
git push origin main
```

4. Habilita GitHub Pages en la configuración del repositorio:
   - Ve a Settings → Pages
   - Selecciona la rama `main` como fuente
   - Haz clic en Save

5. Tu dashboard estará disponible en:
   ```
   https://tu-usuario.github.io/gws-weather-dashboard
   ```

### Opción 2: Descarga Directa

1. Descarga `gws-weather-dashboard.html`
2. Renómbralo como `index.html`
3. Sube a GitHub Pages manualmente o usando git

## Estructura del Proyecto

```
gws-weather-dashboard/
├── index.html              # Dashboard principal
├── README.md              # Este archivo
└── assets/                # (Opcional) Imágenes, favicons, etc.
```

## Personalización

### Cambiar el Canal de ThingSpeak

Abre `index.html` en un editor de texto y busca:

```javascript
const CHANNEL_ID = '2879152';
```

Reemplaza `2879152` con tu Channel ID de ThingSpeak.

### Modificar Campos de Datos

Por defecto, el dashboard lee:
- `field1` → Temperatura
- `field2` → Humedad

Si tu configuración es diferente, edita las líneas:

```javascript
let temp = parseFloat(latestFeed.field1) || 24.8;
let humidity = parseFloat(latestFeed.field2) || 72;
```

### Personalizar Colores

El archivo usa CSS con gradientes y colores personalizables. Edita la sección `<style>` para cambiar:
- Colores de fondo
- Colores de tarjetas
- Gradientes de encabezado

## Configuración de ThingSpeak

Para que el dashboard funcione correctamente con ThingSpeak:

1. **Crea un canal** en ThingSpeak (https://thingspeak.com)
2. **Configura los campos:**
   - Field 1: Temperatura
   - Field 2: Humedad
3. **Obtén tu Channel ID** en Settings
4. **Asegúrate de que el canal sea público** (para lectura sin API Key)

## API Utilizada

- **ThingSpeak API**: Obtiene los últimos 100 registros
- **Chart.js**: Para gráficos interactivos
- **JavaScript Fetch API**: Comunicación con ThingSpeak

## Funcionalidades Técnicas

- ✅ Actualización automática cada 15 segundos
- ✅ Gráficos con datos históricos
- ✅ Cálculos de sensación térmica y punto de rocío
- ✅ Recomendaciones dinámicas
- ✅ Indicador de conexión en tiempo real
- ✅ Completamente responsive
- ✅ Funciona sin servidor
- ✅ Compatible con navegadores modernos

## Navegadores Soportados

- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Opera 76+

## Rendimiento

- **Tamaño**: ~15 KB (HTML + CSS + JS)
- **Velocidad de carga**: <2 segundos
- **Actualización**: Cada 15 segundos (configurable)
- **Sin dependencias externas** (excepto Chart.js via CDN)

## Solución de Problemas

### "Error de conexión"
- Verifica que el Channel ID sea correcto
- Asegúrate de que el canal en ThingSpeak sea público
- Revisa la consola del navegador (F12 → Console)

### Gráficos no se muestran
- Verifica que haya datos en ThingSpeak
- Espera a que se complete la carga inicial
- Recarga la página (Ctrl+F5)

### Datos no se actualizan
- Verifica que el intervalo de actualización sea menor al de escritura en ThingSpeak
- Abre la consola (F12) para ver errores

## Despliegue en otras plataformas

### Netlify
```bash
# Sube el archivo a Netlify drag-and-drop
# o conecta tu repositorio de GitHub
```

### Vercel
```bash
# Conecta tu repositorio a Vercel
# Despliegue automático en cada push
```

### Servidor propio
```bash
# Simplemente sirve el HTML en tu servidor
python3 -m http.server 8000
# o con Node.js
npx http-server
```

## Licencia

Este proyecto está disponible bajo la licencia MIT.

## Autor

Desarrollado para estaciones meteorológicas IoT.

## Contribuciones

Las contribuciones son bienvenidas. Por favor:
1. Fork el proyecto
2. Crea una rama para tu feature (`git checkout -b feature/AmazingFeature`)
3. Commit tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abre un Pull Request

## Soporte

Para reportar bugs o solicitar features, abre un issue en GitHub.

---

**Nota**: Este dashboard requiere una conexión a internet para funcionar correctamente, ya que obtiene datos en tiempo real de ThingSpeak API.
