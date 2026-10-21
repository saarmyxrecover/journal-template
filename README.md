# Journal Template

![License](https://img.shields.io/badge/license-Apache--2.0-8b5e3c)

Plantilla modular para crear un diario digital a partir de archivos Markdown. Cada clon representa **un solo diario**: configura sus datos, agrega paginas y personaliza su portada. Para hacer otro diario, crea otro repositorio desde este template.

## Funciones

- Libro a doble pagina en escritorio y navegacion tactil en movil.
- Paginas Markdown que se cargan automaticamente al agregarlas.
- Hojas faltantes representadas como paginas arrancadas.
- Tinta invisible con linterna UV y comentarios revelables con luz roja.
- Imagenes tipo polaroid, bloques de codigo, estilos Markdown y ajuste automatico del texto.
- Vista en caliente durante el desarrollo.

## Empezar

```bash
git clone <url-de-tu-copia> mi-diario
cd mi-diario
npm install
npm run dev
```

Crea tu repositorio desde la plantilla `journal-template` y clona ese nuevo repositorio. Cada repositorio conserva un solo diario y su propio contenido.

## Personalizar el diario

Edita `src/config.js`:

```js
export const journalConfig = {
  id: 'mi-diario',
  title: 'Mi diario',
  author: 'Tu nombre',
  description: 'Un diario personal.',
  contentDirectory: 'pages',
  cover: '/cover.svg',
  coverAlt: 'Portada de Mi diario',
  storageKey: 'journal-current-page',
}
```

Pon la portada y las imagenes en `public/`. Usa la ruta publica desde Markdown, por ejemplo `![Apunte](/imagenes/apunte.jpg)`. El archivo `src/content/pages/000.md` determina la portada; comienza las paginas escritas en `001.md`.

## Escribir paginas

Crea `src/content/pages/001.md`, `002.md` y asi sucesivamente. Cada pagina puede incluir titulo y fecha en frontmatter:

```md
---
title: Mi primera nota
date: 21 de octubre
---

Escribe aqui. Admite **negrita**, *cursiva*, ~~tachado~~, listas, imagenes y bloques de codigo.
```

Para una nota invisible, crea `001-invisible.md`; la luz UV la revela sobre la misma hoja. Los comentarios HTML `<!-- asi -->` se muestran con luz roja. `final-before.md` y `final.md` son paginas especiales opcionales. `final-before-wait.md` se ignora.

## Comandos

```bash
npm run dev
npm run build
npm run preview
```

## Estructura

```text
public/                 Portada, favicon e imagenes del diario
src/config.js           Identidad y opciones de este unico diario
src/content/pages/      Paginas Markdown
src/journal/            Carga, renderizado y navegacion del libro
src/styles/global.css   Estilos y adaptacion responsive
```

## Licencia

El codigo de la plantilla se distribuye bajo [Apache-2.0](LICENSE). Los textos, fotografias y otros recursos que agregue cada autor son suyos y no forman parte de la licencia del codigo. Consulta [NOTICE](NOTICE).
