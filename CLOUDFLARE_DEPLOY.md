# Guía de Deploy en Cloudflare Pages

## Configuración Automática: GitHub → Cloudflare Pages

### Paso 1: Verificar que el código esté en GitHub
Tu repositorio: `PedroCarrilloChan/SmartPasses`

### Paso 2: Crear Proyecto en Cloudflare Pages

1. Ve a tu Dashboard de Cloudflare: https://dash.cloudflare.com/
2. Click en **"Workers & Pages"** en el menú lateral
3. Click en **"Create application"** → **"Pages"** → **"Connect to Git"**
4. Autoriza Cloudflare a acceder a tu GitHub si no lo has hecho
5. Selecciona el repositorio: **PedroCarrilloChan/SmartPasses**
6. Configura el build:

   ```
   Production branch: main (o la rama principal que uses)
   Build command: (dejar vacío o npm run build si tienes uno)
   Build output directory: / (raíz del proyecto)
   Root directory: / (raíz del proyecto)
   ```

7. Click en **"Save and Deploy"**

### Paso 3: Configurar el Dominio

1. Una vez deployado, ve a **"Custom domains"** en tu proyecto de Pages
2. Click en **"Set up a custom domain"**
3. Ingresa: **smartpasses.io**
4. Cloudflare detectará automáticamente tu dominio y configurará el DNS

**O actualiza manualmente el DNS:**
- Ve a **DNS** en tu dominio smartpasses.io
- Cambia los registros A actuales por un registro CNAME:
  ```
  Type: CNAME
  Name: @ (o smartpasses.io)
  Content: [tu-proyecto].pages.dev
  Proxy status: Proxied (naranja)
  ```

### Paso 4: Auto-Deploy Configurado ✅

Ahora cada vez que hagas push a GitHub desde Replit:
```bash
git add .
git commit -m "Update site"
git push origin main
```

Cloudflare Pages automáticamente:
- ✅ Detecta el push
- ✅ Descarga el código
- ✅ Hace el build
- ✅ Despliega la nueva versión
- ✅ Actualiza smartpasses.io

### Archivos importantes:
- `_redirects` - Configuración de rutas para Cloudflare Pages
- Este archivo solo sirve archivos estáticos, no ejecuta Node.js/Express

### Notas:
- El archivo `server.js` NO se ejecutará en Cloudflare Pages
- Las rutas se manejan con `_redirects`
- Si necesitas lógica de servidor, considera migrar a Cloudflare Workers

### Verificar Deploy:
1. URL de Pages: `https://[tu-proyecto].pages.dev`
2. Dominio custom: `https://smartpasses.io`
