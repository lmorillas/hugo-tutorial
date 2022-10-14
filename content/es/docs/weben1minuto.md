---
title: "Mi primera web con Hugo"
date: 2022-09-16
weight: 2

  
---

{{% pageinfo %}}
**Objetivo:** Construcción de una primera web

**Contenidos:** 
* Comando ```hugo```
* Configurar un sitio con hugo con temas y contenido
* Diseño de la estructura de un sitio basado en Hugo
* Pipeline de despliegue continuo
* Análisis de prestaciones y mantenimiento
{{% /pageinfo %}}

## Creación del sitio

**Requisito**: Instalar hugo

``` bash
$ hugo new site acme-corporation --format yaml

```

Estructura creada:

``` bash
archetypes
config.toml
content
data
layouts
static
themes
```
Aquí tienes una estructura más detallada: https://drek4537l1klr.cloudfront.net/jain/Figures/CH02_F03_Jain.png  (c) Libro *Hugo in Action*


## Creación del repositorio

``` bash
cd acme-corporation
git init .
git add *
git commit -m "Creación del esqueleto de la web"
```

## Añadir un tema

Podemos hacerlo de tres formas:
* Como un módulo de Hugo
* Con git submodules
* Copiando la carpeta del tema
  

Vamos a usar el último método.

> https://github.com/lmorillas/Eclectic

* Descargar a la carpeta themes. Renombrar la carpeta del tema a `Eclectic`

* Modificar `config.yaml`

```
theme: Eclectic
```

## Servidor de desarrollo

``` bash
hugo server
```

La primera vez optimiza los recursos y genera cachés para el sitio. Por eso tarda maś.

## Añadir contenido

### Configuración

``` yaml
baseURL: https://example.org/
languageCode: es-es 
title: Acme Corporation 
theme: Eclectic 
author: 
  facebook: "https://facebook.com/example" 
  twitter: "https://twitter.com/example" 
  email: "contact@example.org" 
  name: "Acme Corporation" 
  location: Zaragoza
  phone: (999) 999-9999 
  hours: "**Lunes-Viernes** 9:00AM - 6:00PM" 

menu:
  main: 
    - identifier: about 
      name: Acerca de 
      url: /about 
      weight: 100 
    - identifier: contact
      name: Contacto 
      url: /contacto 
      weight: 200 
params: 
  color: "#4f46e5"
  copyright: "Copyright &copy; 2022 Acme Corporation. Todos los derechos reservados."
  footer:
  - title: About
    content: >
      Acme Corporation is the world's leading
      manufacturer of digital shapes. From squares and
      circles to triangles and hexagons, we have it
      all. Browse through our collection of various
      forms with different thicknesses and line styles.
      We shape the world. You live in it.


  - title: Publicaciones recientes
    recents: blog
    recentCount: 7

  - title: Contact Us
    contact: true

```

### Página de inicio

Landing page

https://github.com/hugoinaction/hugoinaction/blob/chapter-02-resources/05/layouts/index.html

En una primera versión la editamos directamente. 

> layouts/index.html

Mira este ejemplo: https://github.com/hugoinaction/hugoinaction/blob/chapter-02-resources/05/layouts/index.html