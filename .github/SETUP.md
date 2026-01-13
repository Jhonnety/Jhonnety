# 🔧 Configuración de GitHub Actions

Este documento explica cómo configurar las animaciones y métricas automatizadas de tu perfil.

## 🐍 Snake Animation

La animación de la serpiente que come tus contribuciones se genera automáticamente mediante GitHub Actions.

### Cómo funciona:
- ✅ Ya está configurada y lista para usar
- ✅ Se ejecuta automáticamente cada 12 horas
- ✅ Se ejecuta en cada push a la rama `main`
- ✅ Puedes ejecutarla manualmente desde GitHub Actions

### Primera ejecución:
1. Ve a tu repositorio en GitHub
2. Click en **Actions** (pestaña superior)
3. Selecciona **"Generate GitHub Contribution Snake"**
4. Click en **"Run workflow"** → **"Run workflow"**
5. Espera 1-2 minutos y la animación aparecerá en tu README

## 📊 Métricas Avanzadas (Opcional)

Si quieres activar las métricas avanzadas de la segunda workflow (`metrics.yml`):

### Paso 1: Crear Token Personal
1. Ve a GitHub Settings → Developer settings → Personal access tokens → Tokens (classic)
2. Click en **"Generate new token (classic)"**
3. Nombre: `METRICS_TOKEN`
4. Selecciona los siguientes permisos:
   - ✅ `repo` (todos los sub-permisos)
   - ✅ `user` (todos los sub-permisos)
5. Click en **"Generate token"**
6. **Copia el token** (no podrás verlo de nuevo)

### Paso 2: Agregar el Token al Repositorio
1. Ve a tu repositorio → Settings → Secrets and variables → Actions
2. Click en **"New repository secret"**
3. Name: `METRICS_TOKEN`
4. Secret: Pega el token que copiaste
5. Click en **"Add secret"**

### Paso 3: Ejecutar la Workflow
1. Ve a Actions → "GitHub Profile Metrics"
2. Click en "Run workflow"
3. Espera 2-3 minutos
4. ¡Listo! Las métricas aparecerán en tu README

## 🎨 Personalización

### Cambiar colores del snake:
Edita `.github/workflows/snake.yml` y cambia el parámetro `palette`:
- `github-dark` (actual)
- `github-light`
- `github-dark-blue`
- Crea tu propia paleta personalizada

### Cambiar frecuencia de actualización:
En ambos archivos `.yml`, modifica el valor de `cron`:
- Cada 12 horas: `"0 */12 * * *"`
- Cada 6 horas: `"0 */6 * * *"`
- Cada 24 horas: `"0 0 * * *"`

## 🐛 Solución de Problemas

**El snake no aparece:**
- Verifica que la workflow se ejecutó correctamente en Actions
- Espera a que la rama `output` se cree automáticamente
- La primera vez puede tardar 5-10 minutos

**Error de permisos:**
- Asegúrate que el repositorio tenga permisos de escritura para Actions
- Ve a Settings → Actions → General → Workflow permissions
- Selecciona "Read and write permissions"

**Los stats no cargan:**
- Puede ser un problema temporal del servicio
- Espera unos minutos y recarga la página
- Verifica que tu username sea correcto en las URLs

---

**¿Necesitas ayuda?** Abre un issue en este repositorio.
