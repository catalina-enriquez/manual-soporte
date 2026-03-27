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

## Dependencias

- Python (venv en `~/Documents/docs/venv/`)
- `mkdocs-material` (instalado en el venv)
- `gh` CLI (para deploy y gestión del repo)
