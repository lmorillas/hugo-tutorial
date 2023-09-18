---
title: "Mejoras del sitio"
date: 2017-01-05
weight: 50
description: 
  Mejoras del sitio a partir  de la plantilla básica 

ayudas:
  https://www.enricotips.com/post/multilingual-dates-in-hugo/

---

{{% pageinfo %}}
* Vamos a aprovechar algunos recursos de nuestro tema: https://github.com/theNewDynamic/gohugo-theme-ananke

{{% /pageinfo %}}

## Añadir menú de navegación
Crea las páginas `acerca-de.md` y `contacto.md` con información sobre tu página.

Añade en el frontmatter:

```yaml
menu:
  main:
    weight: 10
```
Podemos poner más información:
  
```yaml
menu:
  main:
    name: Acerca de
    title: Acerca de
    weight: 10
```

Crea un archivo `_index.md` en la carpeta post. Añade en el `frontmatter`:

```yaml
menu:
  main:
    weight: 20
```

> Puedes ver cómo está construido el [sitio de ejemplo](https://gohugo-ananke-theme-demo.netlify.app/) [aquí](https://github.com/theNewDynamic/gohugo-theme-ananke/tree/master/exampleSite)

## Modifica el `hero background`

Instrucciones: https://github.com/theNewDynamic/gohugo-theme-ananke#change-the-hero-background

## Formulario de contacto

https://github.com/theNewDynamic/gohugo-theme-ananke#activate-the-contact-form

## Leer más 
https://github.com/theNewDynamic/gohugo-theme-ananke#read-more-link

## Social links y compartir
https://github.com/theNewDynamic/gohugo-theme-ananke#social-follow--share

## Tiempo de lectura y número de palabras
https://github.com/theNewDynamic/gohugo-theme-ananke#show-reading-time-and-word-count

## Formato de la fecha

## Logo

