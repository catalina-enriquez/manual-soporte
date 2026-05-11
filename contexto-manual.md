# Contexto del sitio MkDocs — Manual de soporte

Documento de referencia para Claude Code. Leer antes de cada sesión de edición del manual.

## Qué es

El manual de soporte de Circles Learning está publicado como sitio HTML estático usando **MkDocs Material** y alojado en **GitHub Pages**.

## Ubicación de archivos

- **Fuente markdown**: `/Users/catalina/Documents/docs/Operations/manual-soporte/docs/`
- **Configuración**: `/Users/catalina/Documents/docs/Operations/manual-soporte/mkdocs.yml`
- **Estilos personalizados**: `docs/stylesheets/extra.css`
- **Imágenes**: `docs/img/`
- **Repo GitHub**: `catalina-enriquez/manual-soporte` (público)
- **URL del sitio**: `https://catalina-enriquez.github.io/manual-soporte/`
- **Dominio personalizado (pendiente)**: `manualsoporte.getcircles.org` — ver checklist de pendientes

## Estructura del sitio

```
docs/
├── index.md                 # Intro, tono, filosofía
├── herramientas.md          # Herramientas del equipo
├── responsabilidades.md     # Roles y tareas por etapa
├── priorizacion.md          # Priorización de usuarios en riesgo por periodo
├── admin-circles.md         # Plataforma Admin completa
├── help-desk.md             # Tickets y chat de soporte
├── registro-datos.md        # Base de datos y bajas
├── problemas-y-faq.md       # Procedimientos y FAQ
├── plantillas.md            # Mensajes estandarizados
├── coordinadores.md         # Rol de coordinación
├── slas.md                  # Tiempos de respuesta
├── escalamiento.md          # Protocolo de escalamiento
├── onboarding.md            # Incorporación nuevos miembros
├── img/
│   ├── logo-circles.png          # Logo blanco horizontal (header)
│   ├── favicon-circles.png       # Círculo azul (pestaña navegador)
│   ├── create-circle-from-admin.png
│   └── registro-bajas-admin.png
└── stylesheets/
    └── extra.css
```

## Diseño visual

- **Color principal**: `#2f82fe` (azul Circles)
- **Logo header**: logo blanco horizontal de Circles (`img/logo-circles.png`)
- **Favicon**: círculo azul recortado (`img/favicon-circles.png`)
- **Fuente cuerpo**: Montserrat (via Google Fonts, configurado en `mkdocs.yml`)
- **Fuente H1**: League Spartan bold (via `@import` en `extra.css`)
- **Fuente H2-H6**: Montserrat bold
- **Color títulos**: `#2d2d2d` (gris muy oscuro)

## Cómo editar contenido

1. Editar los archivos `.md` en `docs/`
2. Previsualizar localmente:
   ```bash
   cd ~/Documents/docs/Operations/manual-soporte
   source ~/Documents/docs/venv/bin/activate
   mkdocs serve
   ```
   Abrir `http://127.0.0.1:8000/` en el navegador
3. Publicar cambios:
   ```bash
   git add .
   git commit -m "Descripción del cambio"
   git push
   mkdocs gh-deploy
   ```

## Convenciones de formato

- Los blockquotes de nota/tip/warning usan admonitions de MkDocs Material: `!!! note`, `!!! tip`, `!!! warning`, `!!! danger`
- Imágenes se referencian como `![Alt](img/nombre.png)`
- No usar `---` entre secciones (cada sección es su propia página)
- Los H1 son el título de la página; H2 y H3 para subsecciones

## Archivos relacionados

- `Manual-Soporte.md` — versión original monolítica (puede eliminarse)
- `Checklist pendientes manual soporte.md` — tareas pendientes de contenido
- `published-links.md` — links al Google Doc (versión antigua)
- `.drive-export.json` — configuración de sync a Google Docs (ya no se usa)

## Bandeja de entrada (actualización del manual)

La carpeta `bandeja/` es el mecanismo para agregar contenido nuevo al manual. Catalina deja ahí un archivo `INSTRUCCIONES.md` con lo que quiere agregar, junto con pantallazos opcionales.

### Cómo procesar la bandeja

Cuando Catalina pida procesar la bandeja (ej: "procesa la bandeja del manual de soporte"), seguir estos pasos en orden:

#### 1. Leer la bandeja
- Leer `bandeja/INSTRUCCIONES.md` para entender qué se quiere agregar o modificar.
- Leer/ver los pantallazos que estén en `bandeja/` para entender qué muestran.

#### 2. Analizar el manual actual
- Para cada bloque de contenido en las instrucciones, buscar si ya existe una sección relacionada en el manual (buscar en los `.md` de `docs/`).
- Revisar `mkdocs.yml` para entender la estructura de navegación.

#### 3. Determinar ubicación
- **Si la información ya existe**: identificar el archivo `.md` y la sección exacta a actualizar.
- **Si es información nueva**: decidir en qué archivo `.md` existente encaja mejor, o si amerita una página nueva (solo si el tema es lo suficientemente grande y distinto).

#### 4. Redactar y editar
- Redactar el contenido nuevo en el tono del manual: directo, claro, con instrucciones paso a paso cuando corresponda.
- Usar las convenciones de formato del manual (admonitions, H2/H3, etc.).
- Si se actualiza una sección existente, reescribirla integrando la información nueva de forma coherente (no simplemente pegar al final).

#### 5. Procesar imágenes
- Renombrar cada pantallazo con formato descriptivo: `Seccion-descripcion-breve.png` (ej: `Admin-exportar-usuarios.png`, `Helpdesk-crear-ticket.png`).
- Mover la imagen renombrada a `docs/img/`.
- Insertar la referencia `![Descripción](img/nombre-archivo.png)` en el lugar apropiado del texto.

#### 6. Deploy
- Ejecutar desde `~/Documents/docs/Operations/manual-soporte/`:
  ```bash
  source ~/Documents/docs/venv/bin/activate
  git add .
  git commit -m "Actualizar manual: [descripción breve de los cambios]"
  git push
  mkdocs gh-deploy
  ```

#### 7. Limpiar y notificar
- Mover los archivos procesados de `bandeja/` a `bandeja/procesados/` (excepto `INSTRUCCIONES.md`).
- Limpiar el contenido de `INSTRUCCIONES.md` (dejar solo el template vacío).
- Informar a Catalina con una lista de los cambios realizados:
  - Qué secciones se crearon o actualizaron
  - Qué imágenes se agregaron y dónde
  - URL del sitio actualizado: `https://catalina-enriquez.github.io/manual-soporte/`

### Convención de nombres de imágenes

Formato: `Seccion-descripcion-breve.png`

Ejemplos de secciones válidas (basado en los archivos del manual):
- `Admin` → admin-circles.md
- `Helpdesk` → help-desk.md
- `Correo` → correo-soporte.md
- `WhatsApp` → whatsapp.md
- `Registro` → registro-datos.md
- `Plantillas` → plantillas.md
- `Coordinadores` → coordinadores.md
- `Escalamiento` → escalamiento.md
- `Onboarding` → onboarding.md
- `GoogleSheets` → procedimientos con hojas de cálculo
- `Shifton` → herramientas (turnos)

## Dependencias

- Python (venv en `~/Documents/docs/venv/`)
- `mkdocs-material` (instalado en el venv)
- `gh` CLI (para deploy y gestión del repo)
